---
layout: post
title: "Oh! Really I was wondering . . . Until I find this use case!. . ."
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hi all; I hope everyone is doing good. I wish to share something that I currently learned. The topic that I'm going to 
speak today with you may or may not be known to you. But still I wanted to share with you. 


Oki, let me ask you a simple and quick question. What is the square root of 1? That is very simple right. So what is the square root 
of 36? 6 right? 

So how we know that? I mean how come we came to conclusion that 6 is a square root of 36. So from wikipedia, the square root of a
number is defined as :

>In mathematics, a square root of a number a is a number y such that y^2 = a . . . 

So square root of a number 36 will be 6 because 6 X 6 = 36. All with me? Cool.

Now to make your brain work harder, what is the square root of 1694? Well, I myself don't know that. Using google calculator I get
the answer as 41.1582312545. 

So as a CS guy, I have written plenty of programs in Java to find squre root of a given number, during my engg time. So in java, the
code requied to find the square root of a give number 1694 is :

	Math.sqrt(1694)

Which will give you the output of `41.15823125451335`. Pretty much nicer than Google result (I'm not comparing Google with Java in anyway).


So given the definition of square root as (again from wikipedia) :

>In mathematics, a square root of a number a is a number y such that y^2 = a . . . 

The `sqrt` method in the `Math` class need to keep on *guess* untill it finds and satisfies with the condition :

>. . . . y^2 = a 

So to cross check : `41.15823125451335` X `41.15823125451335` = `1694` . 

This is perfect and clean answer! But wait a moment! Finding a sqrt of a number is like a *guessing* game, but how come java *guessed* it correctly??
(i.e `Math.sqrt` method).

Oki, will see the code of `sqrt` function and what it does:

		public static double sqrt(double a) {
     	   return StrictMath.sqrt(a); 
          }
 
Alright it seems, `Math` doesn't know how to calculate the `sqrt`;its calling `StrictMath` for doing this process. So let us see, how this `StrictMath` guessing
it correctly:

		public static native double sqrt(double a);


Oh man! Even `StrictMath` doesn't do the job. Its executing a **native** code! So looking at the doc's of `StrictMath`, it says:


>To help ensure portability of Java programs, the definitions of some of the numeric functions in this package require that they produce the same results as certain published algorithms. These algorithms are available from the well-known network library netlib as the package "Freely Distributable Math Library," fdlibm. These algorithms, which are written in the C programming language, are then to be understood as executed with all floating-point operations following the rules of Java floating-point arithmetic.

So it means that, Java doesn't calculate a sqrt function for us! Its someone named fdlibm is doing that job. So this fdlibm lib will execute the code according to 
your system hardware and makes sure it doesn't suffer from floating point errors and lots more. ( Have a look at CA book, if you want to know more about floating
point errors and similar effects). 

Wow, now you know how the daily usage of `Math.sqrt` is been working under the hood. Cool. That doesn't mean I'm going to finish this post **now**. Sorry adjust with me.

So fdlibm is somehow working for us and doing the guessing game. Now what if we need to write a code for finding the sqrt of a given number?

Alright, to be honest, I tried to come with up some algorithm, but I didn't (more precisely I can't!). The most difficult part is the number in which we need to 
start guessing. Say we need to find the sqrt of `34615`, we know we can start at above `150` and keep on **guess** to find the right answer as something around `186`.But how come computer can do this? If we initilly set `150` as a guessing number for our algorithm and give the number as `34615`, we can keep on increasing the guess number(`150`) and check whether our guess works (i.e `guess number X guess number ~= given number`) and return the result. Well and good. But what happen if a user is giving the input as `1`. We failed! We will be starting at `150` and keep on guessing!!! It wont work, as simple as that.


I always keep on wondering why as a CS guy/girl should read NM (I mean numberical method). Our Mam says: "That is the paper you can score more marks". Ya that is true. But what is the use? 

I went on searching in google to find the solution for our case. I was shocked. I got an algorithm on web, which solves our problem. I was happy. I went to see how the algorithm works. After some time I realized that that is the algorithm I used to solve in my NM class note and people called it as [Newton Method](http://en.wikipedia.org/wiki/Newton%27s_method#Square%5Froot%5Fof%5Fa%5Fnumber).


And if you remember Newton Method, it will take a number for guessing, do some approx on it and goes further. You can see this [here](http://en.wikipedia.org/wiki/Newton%27s_method#Square%5Froot%5Fof%5Fa%5Fnumber). I can even remember my mam saying, Newton method is much faster than other methods!


So as we have the algorithm in our hand, we can write the code easily. So in Groovy the whole code looks like this( I just followed the pseudo code of Newton method and looked at other langugaes of how they implement their Newton method and converted into Groovy):


		def newtonMethod(guess,x){
		    if((good(guess,x)))
          		return guess
    		newtonMethod((improve(guess,x)),x)
		}
		 
		improve = { guess, x -> 
        		def temp = x/guess
        		average(guess,temp)
		}
	 
		average = { x,y ->
	    	(x + y)/2
		}
	 
		square = { it * it  }
		 
		def good(guess,x) {
	    	def temp = Math.abs(square(guess) - x)
	    	(temp < 0.001)
		}
	 
		def sqrt = {
		    newtonMethod(1.0,it)
		}
	 
	println "The sqrt of a given no 34615 is ${sqrt(34615)}"


Prints `186.051068360336` as the answer. You can see the execution of this program [here](http://ideone.com/Ypmwn). Comparing this with `Math.sqrt` function answer which is `186.05106825815324`, we can take a deep breath and say its almost **close**. And as always,

###That's all folks!

I just simply wrote this blog post in a text editor(gedit). So there can be splling mistke, may would has gramatical flaws badly. If that is the case leave a comment.

Thanks for reading my post. If you have any doubts, feel free to post the comment. Comments are welcome!


#####Note: I didn't claim that fdlibm lib would have used Newton method. I don't know about that. But I want to show you how java works internally in this case; and Newton methods and other things which we learned in NM are quite useful in real world and not for getting marks in Anna Univ exams, as our coll would have said! Comments, suggestions, error spotting are welcome as always! Keep *guessing* on my next post. . . :D :D  See yo!! 




		



