---
layout: post
title: AWS, foundation of a foundation
mathjax: true
categories: [AWS]
---

I need to get started with the AWS certifications. While not mandatory(from what I read and heard)
the [AWS Cloud Practitioner][1] certification seems to be the ideal starting point. After all, it's the 
tier 1 in the AWS Certifications world, duh. 

In this post I will enumerate the resources that I found promising to prepare for the exam. I may
edit this post in the future to comment my experience so far with each of them. But first, let's get
some context.

## Cloud, AWS... what?

The cloud movement is here to stay. It's a very exciting opportunity to see your resources and 
designs from another point of view. I've had the incomplete idea -at the beginning of my 
cloud journey- that this "cloud" thing was just a convenient way of getting rid of the physical 
company data center. Pay other people(AWS, Azure, GCP, etc.) to take care of all that hardware. 

You know, I'll manually launch the servers, databases and every other monster that I need 
to get the job done and that's it, behold the full power of the cloud. Practical. Cheaper. Cool. Not that 
much fun. The hardware is no longer near me but my work habits doesn't change that much. Silly me. 

Fast forward some months and... boom! S3, Dynamodb, 
Lambda, Glue, to name a few, exploded in my face and fundamentally changed my approach to software 
building. It even teached me a new word: serverless. This is serious fun. I can't even tell you
how much Cloudformation improved my life. I'm a better human being thanks to stuff like Cloudformation
and the IaC concept.

What I'm trying to say is that the cloud offers unlimited potential to a curious group of people
that wants to build things with it. You can replace your old infrastructure with their cloud
equivalent and that's it. Sure, if such an approach solves the problem and you are happy with it, you
got all my support but you are missing a world of wonders.

AWS, being the serious institution ~~that governs the world with an iron glove~~ that it is, offers
a set of official certifications that validates your cloud experience. They are not mandatory at all
but, after thinking about it for some time, I see them as a way to motivate myself to learn more 
about the cloud resources that AWS have to offer, as an opportunity to gamify the process of learning 
new stuff(or going deeper) that my normal,
day to day routine won't neccesarily offer to me. It's also a nice way of doing some team bonding while
building stronger cloud foundations in the process. 

## Resources

Let's begin with the official recomendation by AWS:

* AWS technical documentation:
  * [Overview of AWS whitepaper][2]
  * [How AWS pricing works][3]
  * [AWS support guide][4]

* Exam review:
  * [Exam guide][5]
  * [Sample questions][6]

* [AWS cloud practitioner essentials course][7]
* [Exam readiness webinar list][8]

Not from AWS but incredibly useful:

* Udemy
  * [AWS Cloud Practitioner Certification Practice Test/Mock Test][9], thanks Puca.

* Youtube:
  * [AWS Certified Cloud Practitioner Training 2020 - Full Course][10]

* Books:
  * [AWS Certified Cloud Practitioner Practice Tests][11], thanks Camilo.

That's it. I' ll try to keep the list as minimal and essencial as possible, the next few weeks
will tell if I kept my word or not. 

Happy cloud adventures!

[1]: https://aws.amazon.com/certification/certified-cloud-practitioner/?ch=cta&cta=header&p=2
[2]: https://d1.awsstatic.com/whitepapers/aws-overview.pdf
[3]: https://docs.aws.amazon.com/whitepapers/latest/how-aws-pricing-works/how-aws-pricing-works.pdf#welcome
[4]: https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html
[5]: https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf
[6]: https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Sample-Questions.pdf
[7]: https://www.aws.training/Details/eLearning?id=60697
[8]: https://aws.amazon.com/training/events/?get-certified-vilt-courses-cards.sort-by=item.additionalFields.startDateSort&get-certified-vilt-courses-cards.sort-order=asc&awsf.get-certified-vilt-courses-type=*all&awsf.get-certified-vilt-courses-series=series%23aws-certification-exam-readiness&awsf.get-certified-vilt-audience=*all&awsf.get-certified-vilt-locations=*all&awsf.get-certified-vilt-countries=*all&awsf.get-certified-vilt-languages=*all&awsf.get-certified-vilt-courses-level=level%23100&awsf.get-certified-vilt-courses-tech-category=*all&cp=sec&sec=prep
[9]: https://www.udemy.com/share/1050Pg2@Pm5KV1xcSF0KdE5CEmJNVBRu/
[10]: https://youtu.be/3hLmDS179YE
[11]: https://www.amazon.com/Certified-Cloud-Practitioner-Practice-Tests/dp/B08F6LDVD3/ref=sr_1_2?dchild=1&keywords=neal+davis+aws+cloud+practitioner&qid=1629140983&sr=8-2