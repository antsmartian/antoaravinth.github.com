---
layout: post
title: "Happy Diwali"
description: ""
category: 
tags: []
---
{% include JB/setup %}

//TODO Arun link

Hi all, hope everyone is doing good. It was a busy weak end. Myself and Arun attended the [Grails48](http://www.grails48.com/) event and where we created the tool for network monitoring. 

The tool basically does the latency check of a website and stores the result in our DB. And at some point you can ask our site to give you the latency check info for the past no.of.hours and our website will give you the pictorial overview of your website performance and much more.

In this post I will describe what we did. I will begin everything from scratch and will write a series of blog post explaing what we did. Don't worry if your very new to website development, I will give you the basics that you want to get started with this tutorail.

Before we get started, I have uploaded the whole code here. Download it. Its a zip file which contains the whole project (sorry it was 9.7 MB).

I will be explaining this blog using the code you downloaded. 

So kindly unzip the file. You will find a file named `index.groovy` inside the folder :`your-folder/grails-app/views/index.groovy`. For reference I will put the partial code here:

    
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







Did you find that code? You can read this post now?


    ##########################################################################
    ##########################################################################