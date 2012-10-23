---
layout: post
title: "I doesn't want to satifsy you any more. I have another pair for me"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hello all :D I hope you people are doing great. This post will speak about java and its related technologies, why I love them and why I hate them. 

If any one come and ask me why I love to code in Groovy. I would first say these : "Groovy is a dynamic language, it can be called as a fully oop language
, it can be used as functional language, it has several nice features of what Javascript has, we can do operator overloading, we can write down dsl's, and blah
blah blah blah. . . . ". The list goes on and on. But I can understand your feeling, that is too techy and its boring you. 


Look lets take another approach and say you why Groovy or other dynamic programming languages like Scala rocks ( in the world of Jvm ). Before I do that, you need to be sure why I dislike Java in some cases. Lets look at that first.

#####Note: The upcoming text is just my imagination of explaning things. In no way I'm hurting or teasing any girls out there. 


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

Note that I have written the code without `;`. And Java is not **satifised**, it wont allow you to compile this program. You need to add `;` for no reason. That is there is no usefulness for us by adding it.
Do you think so?

If we give this code to Java/Jessi they wont accept it : 

![trisha3][3]
[3]: http://i.imgur.com/vfFeQ.jpg



It is something like "Sorry Karthick I need `;` . . . . ".The problem was not with `;` colon alone. But with many other things. Just rewind some steps and look at the hello world program and think about it.

The code for doing it is here: 

    class HelloWorldApp {
        public static void main(String[] args) {
            System.out.println("Hello World!");
        }
    }

Ok that doesn't seems to be very hard at all. But lets stop for a moment and rethink what I said before. I want to write out hello world program, which essentially prints out the text `Hello World!`. But look at the java code for a moment. My aim is to print, just print, then why do I need a `class`? why do I need a command line args( `String[] args` )? Why do I need those `public` keywords? Ah! Thats too more java is excepting from us. 

Our job is to print , so it should have been something like this in Java : 

    println("Hello World")

but it isn't available in Java. The problem was with the design of the Java language. But eventually the code : 

    println("Hello World")

Is a valid Groovy code. This will do what exactly what Java did before. Groovy is some one like Naan Ee's heroine : 

![samantha][4]
[4]: http://i.imgur.com/otCBe.jpg

Pretty new when considered to Java and more beautiful. Groovy has some nice feature's like : 

    
    //no need to know the data type
    def string = "string"

    //closures
    def closures = {  }

The coolest thing in Groovy is that you no need to say the data type. Groovy can *infer* for you. That is in the above code `string` is of type `String`. But we haven't specified it in our code. Groovy can find that for us. The closures in Groovy are very powerful in nature and they are similar to the delegate concept of C# (I'm not sure of whom I need to compare C# with, I haven't used it much) . 

To be more precise, what you do if you want to do open a file in Java? You should do something like this:


    new BufferedReader(new FileReader("file"));

You have opened up the files but you should close it after using it. Usually people will wrap the above code with `try-finally` block. In `finally`  block they call `close()`. But what happen if in `finally` block the code throws an exception? You need to catch them too. Oops! More things to remember ah? 

Lets look how Samantha helps us. The code for opening and printing each line in groovy is :

    new File('myfile.txt').eachLine { println it }

Thats it. The above code will open the file named `myfile.txt` and close them properly once it has been finished processing. The `{`,`}` block are called as closures which is taking care of opening and closing our file properly. Closures does also have other powerful properties, which I haven't spoken here in this blog.

The reason why I choose Samantha pic of Naan Ee has two reasons. 1. To make guys stick to the post and 2. Was to . . . . . 

As in case of Naan Ee, being we as housefly we are just saying the compiler to do useful things but asking our compiler or samantha to do the rest hard work.

What I mean by this is, when I do : 

    new File('myfile.txt').eachLine { println it }

This looks really great in the eyes of devoloper. But note how much work Groovy is needed to do in order to open the files and close them behind the scenes? 

>#####No lunch is called as "Free lunch"

In file example Groovy is taking care of opening and closing the files. And also it creates a class for us behind the scenes ( this is because JVM has certain conditions on which only the code will be allowed to execute ). All these are done by Groovy for us, creating the class , opening the files and many other things make Groovy to work slower than Java. Groovy code will run slower than Java code ( keep this in mind, I will come back later to this point ). Performance problem is someone like :

![villan][5]
[5]: http://i.imgur.com/Kyfqq.jpg

We need to takle him in order to make Samantha/Groovy works faster. The introduction of Java 7 has a new type of bytecode called as `invokedynamice`.
Let us consider a simple java code:

    String anto = "someone"
    anto.length()

Nothing fancy here. The `anto` is type of `String` which is known by the compiler. With this known information when I do `anto.length()` Java know's I'm calling the `length()` method of `String` class. But consider the case in Groovy:

    def anto = "someone"
    anto.size()

    anto = 123
    //after some code
    anto.callSomeMethod() 

Ok with your naked eye can you say what is the type of `anto` in the above code? The types are changing. Can you be sure that `anto` can be only `String` and `Integer` in this case? `callSomeMethod()` will be belonging to which class ( tricky eh ) ?. This is what I mean by dynmaic nature of the Groovy language. The java is a statically typed language meaning that, when it creates the class byte-code ( once you doing `javac your-file-name` ) all things are known and stored in the class byte-code. That is the caller of the method knows which class it belongs to, so and on and on. The case is not true in Groovy. So Groovy need's to find the type at "run time". There is some one who need to help out Samantha. Luckily we have one :D 

That someone is : 

![ee][6]
[6]: http://i.imgur.com/4fi1m.jpg



#####Intro to InvokeDynmaic:

The `inovkedynmaic` is a new bytecode operation that is introduced in Java 7. The `invokedynamic` instruction allows **dynamic** linkage between a call site and the receiver of the call. All these things happen at run time. With the help of `invokedynamic` now Groovy can make decisions at run-time. Thanks to Java 7. 

From version Groovy 2.0 , Groovy uses `invokedynamic` byte-code to increase it performance. With out `invokedynamic` groovy works. But Groovy compiler will somehow do the job of `invokedynamic` which are slow. Since `invokedynamic` are at byte-code level, using it in Groovy compilers will increase the performance and in fact it does. 

Having used to Groovy is not meant that I forget Trisha or Java. They are still beautiful. The code that I used in java to open the files :

	new BufferedReader(new FileReader("file"));

Can be written as :

	try ( ObjectInputStream in = new ObjectInputStream(new
	FileInputStream("someFile.bin")) ) {
		...
	}

from Java 7. This does the same thing of what Groovy clousres did. They will open the file and close the automatically. These are called as Try with Resources in Java 7. But these are not the closures in Java. Closures in Java will be in Java 8. The whole world is waiting for it. Java changes, even though it is old, it is still the beautiful. So I wait for next Java version :

![trisha][7]
[7]: http://i.imgur.com/NPgZx.jpg


Since the concept of `invokedynamic` is not fully supported in Groovy the upcoming version will do them. Will wait for them. 

![nee][8]
[8]: http://i.imgur.com/KB1PJ.jpg

I conclude that both languages has its trade-offs. Its how you write them up. Most of the time we use Groovy code but in our current project we use both Java and Groovy. We use Java where it shines and use Groovy where it rocks. We call groovy code from Java and java packages from Groovy. Both work seamlessely well. All in all, both trisha and samantha are the most beautiful. 

I just simply wrote this blog post in a text editor(gedit). So there can be splling mistke, may would has gramatical flaws badly. If that is the case leave a comment.

####That's All Folks!

######Note: The concept of `invokedynamic` is huge. I have just defined them. There are more things that are going behind the scenes when you use `invokedynamic` which I didn't explain them here. 

