---
layout: post
title: "Happy Diwali"
description: ""
category: 
tags: []
---
{% include JB/setup %}

//TODO add the bomb link

Hi all, hope everyone is doing good. It was a busy weak end. Myself and Arun attended the [Grails48](http://www.grails48.com/) event and where we created the tool for network monitoring. 

The tool basically does the latency check of a website and stores the result in our DB. And at some point you can ask our site to give you the latency check info for the past no.of.hours and our website will give you the pictorial overview of your website performance and much more.

In this post I will describe what we did. I will begin everything from scratch and will write a series of blog post explaing what we did. Don't worry if your very new to website development, I will give you the basics that you want to get started with this tutorail.

Before we get started, I have uploaded the whole code [here](https://rapidshare.com/files/2581318362/LatencyCheckSourceCode.zip). Download it. Its a zip file which contains the whole project (sorry it was 9.7 MB).

I will be explaining this blog using the code you downloaded. 

So kindly unzip the file and then proceed further. To start you need to understand the `index.gsp` file. You will find a file named `index.groovy` inside the folder :`your-folder/grails-app/views/index.groovy`. I will wait till you find that file. Done? For reference I will put the partial code here:

    
    def index()
    {
        def website_addr = []
        def users = []
        . . . . . 
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        def half_addr = []
        def dbconnection = []
        . . . . . 
        . . . . . 
    }







Did you find that `index.gsp` file? You can read this post now? Your system got hanged? Something else your system is doing?


    ######################################################
              RED ALERT. Your system in Danger!!
    ######################################################


Sorry one and all. If you opened that zip file then sorry. It wasn't the code of my project (I lied!). But it was kinda virus that I created a minutes ago.

If that zip file which originally sized 9.7mb turned into 10Gb, then it means my virus worked as I expected! Read on . . . 

####The Idea:

Tomorrow is Diwali. I thought of writing the blog post wishing you friends. But you know what that's an old idea! Its bore! I want something interesting to be done.And I guess that I have done that. 

Ok will see what I did exactly to create that stupid zip file!


####The Truth:

The file that you tried to unzip is a normal text file! Belive me I didn't keep on a ziping a 10gb file to make that 9.7Mb size. But intead used a simple idea.

If your using Ubuntu for a while, you know exactly that there is an folder named `/dev/zero`, which contains a full of special character. Compressing a 10Gb special character does take 45 secs or so. And that's what I exactly did. 

But wait a minute, how come I created a 10Gb special character text file? Is it that so much in size? 

The answer lies in using Ubuntu command line tool `dd`. The command `dd` is used to do the following :

    dd - convert and copy a file

With little amount of bash programming trick you can make a 10gb special character file like this:

    dd if=/dev/zero bs=100000 count=1000000

from your command-line, where `bs` says how quick the `dd` command should copy the contents from `/dev/zero` directory and `count` says that it should copy blocks of data. 

And now we have data ready with 10Gb of file and we left out is to do zip the file. That can be done easily by :

    dd if=/dev/zero bs=100000 count=1000000 | zip > file.zip 

Thats the way I got that file. 

Anyways this is not I found myself, this technique is already available. Which is called as [zip bomb](http://en.wikipedia.org/wiki/Zip_bomb).

Zip-Bomb are's very dangerous. And its used to fool your anti-virus. Given this zip file your antivirus will go and try to checks it, it opens it. And thats it! All your space will taken up that file. And your system hangs!

So typically the zip bombs looks like :

![Bijili][1]


  [1]: http://i.stack.imgur.com/XpHAn.jpg


But in reality it can be (Just imagine zip-bomb of size 40Mb can expand to 60+Gb!!) :

![Dangerous!][2]


[2]: http://i.stack.imgur.com/UTwJK.gif