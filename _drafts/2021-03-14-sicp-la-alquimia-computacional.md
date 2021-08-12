---
layout: post
title:  SICP. La alquimia computacional nunca se sintió tan bien. Primeros pasos.
mathjax: true
categories: [cs]
---

Estos días(y si todo sigue bien, los próximos meses) me encuentro atravesando mi segundo
intento con uno de esos clásicos, esos que te hacen sentir que le soplaste
el polvo a un tomo de secretos y alquimia. Nada más ni nada menos que Structure and 
Interpretation of Computer Programs(SICP o Wizard Book o Purple Book).

Tiempo atrás lo había empezado pero su rareza poco "práctica" me hizo dejarlo. Una
lástima porque ahí reside su magia. Lo recomiendo, si se me permite el atrevimiento, como
una lectura por y para el placer. Si te gusta sentir la magia por la magia misma, este es 
el libro, caso contrario mejor dejarlo a un costado, tal vez para más tarde, tal vez para
nunca jamás.

No es mi intención hablar de los ejercicios, para ello hay recursos infinitamente mejores
(por ejemplo: [sicp-solutions][1]). Mi idea es comentar mis experiencias, hablar de temas
periféricos que trae la aventura. Empecemos por el principio: conseguir el texto y ejecutar
los programas.  

## ¿De dónde saco el material?

No os preocupeís, estimadas personas, porque todos los recursos necesarios están disponibles
en la web oficial por gracia divina. Yendo a [MITPressSICP][5] vamos a encontrar el texto
completo en HTML, junto con material adicional, el código del libro, una implementación de
Scheme, etc. 

También tenemos a nuestro alcance las clases del 2008 de la Universidad de Berkeley(en inglés) de 
forma gratuita: [Computer Science 61A - Spring 2008][6]. 

¡Completito!

## ¿Cómo correr el código?

SICP usa Scheme(un dialecto de [LISP][2]), esto no es para nada usual pero tampoco es azar que los
autores hayan elegido una cosa que parece salida del Área 51 para ilustrar sus ideas. Si la
fortuna acompaña en el futuro hablaremos del paradigma funcional, la metaprogramación y esos
yuyos. Volviendo al post, ¿cómo hacemos para arrancar esta cosa? Bueno, mi respuesta es:
usemos [DrRacket][3]. Una vez instalado(junto con su IDE), tenemos que descargar los paquetes
que implementan la versión de Scheme que usa el libro. Basta con seguir las instrucciones
yendo a [SICP Collections][3].

¡Listo! Con eso debería ser suficiente para correr todo el código del libro. Si bien
existe una extensión para editores modernos como VSCode(ver [MagicRacket][4]) no puedo 
recomendarla. Tuve problemas con el servidor que levanta, al punto tal de que al crear
un nuevo archivo .rkt(que es la extensión que tenemos que usar ;-)) deja de funcionar.

*¡Hasta la próxima!*


[1]: http://community.schemewiki.org/?sicp-solutions
[2]: https://es.wikipedia.org/wiki/Lisp
[3]: https://docs.racket-lang.org/sicp-manual/index.html
[4]: https://marketplace.visualstudio.com/items?itemName=evzen-wybitul.magic-racket
[5]: https://mitpress.mit.edu/sites/default/files/sicp/index.html
[6]: https://archive.org/details/ucberkeley-webcast-PL6879A8466C44A5D5