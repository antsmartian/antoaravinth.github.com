---
layout: post
title: "<3 Siblings Dhisoom! <3"
description: ""
category: programming,Groovy
tags: [Groovy,DSL,Sisters]
---
{% include JB/setup %}

Hi all, probably this is my first blog post on my new blog. The title **Siblings Dhisoom!** might be misleading. Ok well this is the 
blog post that I write for my sisters. It has something related to programming languages, i.e I'm gonna explain you how I got a idea of 
wishing my sisters via **Groovy** code!

If that doesn't sound interesting to you, you can go skip reading my post.

I request you to read (this)[http://antoaravinth.github.com/2012/07/31/hello-world/] post before you move on. I will wait here. Done reading? So all set, lets move on quickly.

I certainly love doing certain things in my fav language **Groovy**. So I was thinking how I can use this 
language to wish my sister. This idea might seem pretty odd, but thats oki. Actually I need some ways to do this :

	rakiWishes "anto" "ramya"
	
It looks direct english language, but I need this code to run this in Groovy with out any error's. Am I crazy? No this is possible, this what the subject of Domain Specification language (DSL) deals with. Mind you, Domain specification language are topics on its own, I'm not going to explain them in my blog. 

But what basically DSL means? In very simple terms DSL is used to solve a problem on a particular domain. So SQL is an DSL
to solve query related problems against DB's. And as HTML. Do you wondering Java/C# is for? Well that is not a DSL, they are 
*General purpose programming language* not DSL's. That is Java can be used to create "Hello World Programs", GUI applications, scientific apps, created a multithread dead app, appplet...Ah! Thats lot more you can do with Java. But where as in SQL you can solve only DB related queries! Did you see how SQL solves a particular *domain*(Database) problem and how Java used to solve the problem. Now I guess you got the understanding of what DSL's are. Thats enough for you to follow this post. Lets move on.


The power of SQL lies  in how one can read it. Lets take this syntax : 

	select from DB where username = "someone";
	
Did you notice the magic of SQL? The person without any programming language can read this, it is just like English sentence.
So taking SQL as an example, I'm going to create a DSL(which I hope it read it as normal english).

So in my blog post, I'm going to explain how I created a small DSL of brother sister relationship check.


So looking back at the code : 

	rakiWishes "anto" "ramya"
	
It say that `anto` is wishing here sister `ramya`. It looks like english (I have worked on it to look like that). And I can say
this as DSL for brother-sister relation! (Ok, I accpet this can't be 100% DSL for brother-sister relation but atleast 60% :P).
DSL languages need to be given some name, oki I call this small pretty DSL as Siblings Dilemma! :D 

	>Technically: To be in terms of Groovy *semantics*, the `rakiWishes` is a method that accepts a method pointer
	with the paramaters `anto` and `ramya`. Note that there are two parameters, but I haven't specified `,` in between
	them to separate them. Somehow in my implementation I found that `ramya` is my second paramater. If that sound's
	hard for you, leave a comment. 


So what I need basically is that when I call or do something like this in my Groovy code :

	rakiWishes "anto" "ramya"
	
My Sibling Dilemma(SD) need to make sure that there is a brother-sister relationship between `anto` and `ramya`(This should be
100% true because `ramya` is my sister.)

So if that relation is there, I need to get output as :

	'Happy Raksha Bandhan ramya'
	
That is I'm wishing my sister. So this is what I'm expecting my code to do so:

	rakiWishes "anto" "ramya" //if anto is a bro of ramya then wish my sister
	'Happy Raksha Bandhan ramya'
	
So here are the wishes for all sisters(my own siblings, cousins, and the one who tied raki in my coll life :( )

	rakiWishes 'anto' 'jenni'
	'Happy Raksha Bandhan jenni'
	

	rakiWishes 'anto' 'bianca'
	'Happy Raksha Bandhan bianca'
	
	
	rakiWishes 'anto' 'shiny'
	'Happy Raksha Bandhan shiny'


	rakiWishes 'anto' 'lalitha'
	'Happy Raksha Bandhan lalitha'
	

	rakiWishes 'anto' 'bakiya'
	'Happy Raksha Bandhan bakiya'
	

I tested all that is working fine. I'm getting the output as expected. But what happen if someone tries to do 
something like this :


	rakiWishes 'anto' 'samantha' //I shoudln't return this.
	'Happy Raksha Bandhan samantha'
	
I shouldn't return `'Happy Raksha Bandhan samantha'` as `samantha` can't be my(`anto`) sister. If this is the case then I should
return:

	rakiWishes 'anto' 'samantha' 
	"no brother sister relation is specified"
	
That is pretty cool. Thats what I need. And also :

	rakiWishes 'anto' "antosUpComingWifeName" //this need to return this!
	"no brother sister relation is specified"
	
The code is fully tested with `assert` checks. You can see the full implementation [here](http://ideone.com/D11qP)


You can clearly see there is no error's in my program and it is executing without any output's as it should be.

The coolest part is how I'm calling a method `rakiWishes` like a normal english terms with paramaters passing to it :

	rakiWishes "anto" "ramya"
	
That is super cool! 

So apart from Groovy wishing my sister, let me wish myself "Happy raksha bandhan" to my sisters :D 


**Note1**: The code that I have written is not fully by me. 40% of the code is based on Groovy's utility scripts.
But the idea is fully mine! And the title **Siblings Dhisoom!** is taken from Twitter trend (2/Aug/2012).

**Note2**: DSL's are getting famous these days. I want you to know about it. My program can't be called fully as DSL. But I used
the terms here, because I will be writing several post on this topic in near feature.
	
I just simply wrote the blog in a text editor. So there can be splling mistke, may would has gramatical flaws badly. If that is the case leave a comment.

Thanks for reading my post. If you have any doubts, feel free to post the comment. Comments are welcome!

###That's all folks!
	
	 



