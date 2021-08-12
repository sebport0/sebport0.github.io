---
layout: post
title:  En los pagos del debugger
mathjax: true
categories: [Python]
lang: es
ref: pydebugger
---

Nunca usé el debugger de python en este año y siete meses que 
llevo viendo el lenguaje en mi pantalla todos los días -laborales- unas ocho horas como 
mínimo. Es más, la idea de tener que incorporar una herramienta similar nunca me atrajo 
demasiado. ¿Para qué si el buen y viejo `print()` siempre estuvo a la altura? Correr el
código otra vez para ver ese print esclarecedor siempre fue barato y fácil. ¿Qué sentido
tiene hacerse más problemas? Cualquier cosa un break o un return de acompañante para parar
la ejecución y listo. ¿No? Bah, puedo recordar algunas ocasiones donde me faltaron
prints y tuve que volver a ejecutar todo desde el comienzo, ¿no?

La cosa empezó a cambiar hace unas dos semanas cuando un compañero del trabajo(gracias 
Carlos) me acercó los usos y bondades de pdb. Un nuevo caso de *no sabía que lo necesitaba
hasta que me lo mostraron.* En lo que sigue, una breve exploración casera de pdb - The 
Python Debugger.

Empecemos por algo que siempre es un plus: pdb es un módulo built-in, es decir, ni bien
terminamos de instalar python(de una forma que no viole algún derecho humano fundamental)
ya está disponible para ser usado. Viene con la cajita feliz. 

Claramente es una herramienta que hace cosas varias pero por ahora 
solamente necesitamos una funcionalidad que sea superior al `print()` para cuando estamos
buscando causas y demostraciones de fallos.  Afortunadamente es re-contra-mega fácil
obtener un comportamiento similar, solamente necesitamos presionar algunas teclas 
más(de hecho, puede que hasta algunas menos). Veamos un ejemplo.

## Ejemplo: vectores y sus longitudes

Supongamos que queremos empezar a implementar una librería que maneja datos geográficos.
Como somos personas prácticas decidimos empezar por la unidad más básica posible.
Decidimos que un vector en $\mathbb{R}^3$ y un método asociado que nos devuelva la 
longitud del vector cumplen el requerimiento.

```python
from dataclasses import dataclass
from math import sqrt


@dataclass
class Vector:
    x: float = 0.0
    y: float = 0.0
    z: float = 0.0

    def length(self):
        return sqrt(self.x**2 + self.y**2 + self.z**3)


if __name__ == "__main__":
    X = Vector(5, 0, 0)
    print(X.length)
```

Lo probamos y este es el resultado

```python
5.0
```

Excelente. Todo va según lo esperado, ahora probamos con `X = Vector(0, 5, 0)`, obtenemos
el mismo resultado, como esperábamos. Bien, bien, evaluemos la tercer coordenada: 
`Vector(0, 0, 5)`. Ups. ¿Qué pasó?

```python
11.180339887498949
```

¡Qué buena ocasión para usar pdb! Bueno, tal vez no, esto es demasiado sencillo pero 
es la idea. ¡Bah! Llamando a la función `breakpoint()` en la última línea invocamos a pdb,
siempre y cuando estemos usando python >= 3.7, caso contrario tenemos que reemplazarla por: 
`import pdb; pdb.set_trace()`.

```python
if __name__ == "__main__":
    X = Vector(0, 0, 5)
    print(X)
    print(X.length)
    breakpoint()
```

Cuando ejecutamos el programa vamos a ver algo similar a lo que sigue

```
Vector(x=0, y=0, z=5)
11.180339887498949
--Return--
> <path_al_script>(20)<module>()->None
-> breakpoint()
(Pdb) 
```

¿Qué significa esto?

* `> <path_al_script>(20)<module>()->None` nos da el contexto en el que se mueve pdb.

* `-> breakpoint()` dice cuál es la próxima línea a ejecutar.

En este estado somos capaces de realizar un montón de acciones para resolver nuestro 
problema. Se puede pensar como todos los `prints()` que queramos y, mejor aún, podemos
definir y probar las cosas que necesitemos(prestarle atención al scope de pdb). Observemos 
que pdb tiene sus propios comandos, uno que vamos a usar mucho es `p` para hacer un print
de lo que queremos ver. Si bien no siempre es necesario, es recomendable usarlo.
Por ejemplo, para X

```
-> breakpoint()
(Pdb) p X
Vector(x=0, y=0, z=5)
```

Podemos ejecutar casi todo el python que se nos antoje, solamente tenemos que prestar 
atención a que si necesitamos algún objeto definido dentro del código este tiene que 
figurar en el contexto de pdb.

Con `n` continuamos la ejecución y avanzamos a la siguiente línea: en este caso finalizamos
la ejecución del programa. Otros dos comandos interesantes son `l` para listar y `ll` 
para hacer lo mismo para todo el script.

```
-> breakpoint()
(Pdb) l
 15  
 16     if __name__ == "__main__":
 17         X = Vector(0, 0, 5)
 18         print(X)
 19         print(X.length)
 20  ->     breakpoint()
[EOF]
```

Pdb tiene varias utiliades como las anteriores y, encima, está muy bien documentado. No 
hace falta memorizar ninguna de ellas, es suficiente con hacer `h` para ver el listado 
completo de comandos. Bueno, sí, les mentí: hace falta memorizar al menos una de ellas.

```
-> breakpoint()
(Pdb) h

Documented commands (type help <topic>):
========================================
EOF    c          d        h         list      q        rv       undisplay
a      cl         debug    help      ll        quit     s        unt      
alias  clear      disable  ignore    longlist  r        source   until    
args   commands   display  interact  n         restart  step     up       
b      condition  down     j         next      return   tbreak   w        
break  cont       enable   jump      p         retval   u        whatis   
bt     continue   exit     l         pp        run      unalias  where    

Miscellaneous help topics:
==========================
exec  pdb
```
Además, con `h <alguna de las de arriba>` podemos ver una ayuda más detallada

```
(Pdb) h q
q(uit)
exit
        Quit from the debugger. The program being executed is aborted.
(Pdb)
```
 
O bien con `h pdb` accedemos a la documentación completa de pdb. ¡Tremendo!

Cerremos este breve comentario diciendo que:

* Es más que posible colocar más de un `breakpoint()` a lo largo de nuestro código. 
  Con un `c` podemos saltar de un breakpoint a otro, ejecutando todo el código que se encuentre en el medio.

* Pdb es una clase como cualquier otra por lo que podemos modificarla según nos plazca. 

* Una manera de ir al código de pdb
  
  ```
  (Pdb) import pdb
  (Pdb) pdb.__file__
  '/usr/lib/python3.8/pdb.py'
  ```

Recomiendo encarecidamente darle una ojeada a la documentación oficial y al tutorial de
Real Python(ver bibliografía).

¡Hasta la próxima!

## Bibliografía
- [Docs oficiales](https://docs.python.org/3.8/library/pdb.html)
- [Python Debugging With Pdb](https://realpython.com/python-debugging-pdb/)
