---
layout: post
title: ""
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hello all :D I hope you people are doing great. This post will speak about java and its related technologies, why I love them and why I hate them. 

If any one come and ask me why I love to code in Groovy. I would say first say these : "Groovy is a dynamic language, it can be called as a fully oop language
, it can be used as functional language, it has several nice features of what Javascript has, we can do operator overloading, we can write down dsl's, and blah
blah blah blah. . . . ". The list goes on and on. But I can understand your feeling, that is too techy and its boring you. 


Look lets take another approach and say you why Groovy or other dynamic programming languages like Scala rocks ( in the world of Jvm ). Before I do that, you need to be sure why I dislike Java in some cases. Lets look at that first.

#####Note: The upcoming text is meant to be fun. When I said its "fun", it is "fun". In no way I'm hurting or teasing any girls out there. 


Java is more are like the character of "Jessi" in VTV film.


![vtv][1] 
[1]: http://i.imgur.com/JUJzq.jpg


The moment you introduced to java you will be lost by its beauty. Really I did had the feeling when I saw the first java program like this :

    class HelloWorldApp {
        public static void main(String[] args) {
            System.out.println("Hello World!");
        }
    }



I was like "wow nice and cool hello world program". After days passed away I loved Java deeply. I loved to write code in java and we were like : 

![trisha][2]
[2]: http://i.imgur.com/xWBZv.jpg


But there was a problem with Java and also with Jessi. The problem is :

#####We need to satifsy "them" for no reason.

What I mean by this is, lets take a example, lets say I write a code in java like this:

    System.out.println("Hello World!")

Note that I have written the code without `;`. And Java is not **satifised**. You need to add `;` for no reason. That is there is no usefulness for us by adding it.
Do you think so?

If we give this code to Java/Jessi they wont accept it : 

![trisha3][3]
[3]: http://i.imgur.com/vfFeQ.jpg



The problem was not with `;` colon alone. But with many other things. Just rewind some steps and look at the hello world program and think about it.

The code for doing it is here: 

    class HelloWorldApp {
        public static void main(String[] args) {
            System.out.println("Hello World!");
        }
    }

Ok that doesn't seems to be very hard at all. But lets stop for a moment and rethink what I said before. I want to write out hello world program, which essentially prints out the text `Hello World!`. But look at the java code for a moment. My aim is to print, just print, then why do I need a `class`? why do I need a command line args( `String[] args` )? Why do I need those `public` keywords? Ah! Thats too more java is excepting from us. 

Our job is to print , so it should have been something like this in Java : 

    println("Hello World")

but it isn't. The problem was with the design of the Java language. But eventually the code : 

    println("Hello World")

Is a valid Groovy code. This will do what exactly what Java did before. Groovy is some one like : 

![samantha][4]
[4]: http://i.imgur.com/Lorjz.jpg