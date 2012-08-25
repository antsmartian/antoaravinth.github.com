---
layout: post
title: "sshhh!!!! Your hand watch can show you a wrong time! Belive me!"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hello all. I hope your doing great. 

Its been very tough for me to maintain my *time* in the past couple of weak. Lots of work under my name and I had to complete
all these within the given *time*. I need to get up on *time*, catch my train on *time*, reach my office on *time*! Yes really its difficult to maintain my *timings*.

So probably reading the above para you would have thinked, "Am I wasting my *time*, by reading this blog??". Really your not! 
Give me some *time* to prove that your *time* spent on this blog is worthwhile. 

Ahh!! Thats lots of topic revolving around the word *time*. Ya if you have predicted, I'm writing this post on uses of *time* So if a kid asks you a question: "Can you define what is called *time*?". What will be your answer? 

There can be plenty of answers. But will stick to what wikipedia says :

>Time is a dimension in which events can be ordered from the past through the present into the future, and also the measure of durations of events and the intervals between them.

(This is even harder definition, than you might have expected.)


So everyone knows how important to maintain their own time. This is not the post where I'm going to explain of how I maintain my time. Rather how important to maintain a proper time for your pc!. So having set the stage for upcoming para's, will quickly dive into it.


So have you wondered, "If time are important to us ( human being ), will it be important for computers too?". I will wait here, untill you come up with an answer. Certainly it is, time are very much important for computers. 

So let us consider a case; Your running a server to provide a dynamic wepage to say some 10k users. You been very happy about the things that are going in your way. At some bad day your site goes down! What will you do? Certainly you need to debug. 

If this happens to me, I will be opening up my server log files and see **what were going before the time my site goes down**.
So if it sounds hard to you, log will be *something* like this :

		10:43--SSl connection created - - - - - -
		10:43--Mod_sec is up - - - - - - - -
		10:46--ERROR: "something went wrong . . . "


So you can clearly sees that at time 10:46 your site goes down. So looking before that time, can give you a pinch of hint what would have made your site to go down! 

Now I'm not going to show how I will actually debug this problem, rather than show how time plays important in this context.

Computer times are set by us--humans, they are battery based; if battery have some problems then your pc's time wont be running correctly. Now going back to the example, consider that time on the affected machine ( the one where your site is down ) isn't correct. 

That is the site is actually down by 11:46 rather than 10:46 as your systems time wasn't running properly. Looking at this time and calculating what would have went wrong wont help you. Really!

So as I said before, time can go wrong in computers as they are simply battery based. Right?. So what we should do in this case?


---

####Introduction to NTP:

So the simple solution is to use [NTP](http://en.wikipedia.org/wiki/Network_Time_Protocol). This is the protocol that will allow your systems in the netwwork to follow the standard time. The way it works is pretty simple:

+ You will be having a clock that is running in your main system, which is used to be correct. Check [here](http://en.wikipedia.org/wiki/Atomic_clock).

+ And that machine will be connected to your *own* network. 

(There are plenty of other steps requried but I didn't mention it here, because I don't want to bore you with network concepts. Check out other sites if you really want to understand how NTP works deeply)

So pictorially, this should look something like:

	
	I was say correct time (Machine 1)
	         |
	         |
	         |		
	       |			   
	----------------------
	|                    |
	| Your Network 1     |
	|                    |
	----------------------	   	


Now we have second problem, who will maitain the Machine 1? The answer is pretty simlpe as well: "Some one".

There are plenty of servers up and running called as [NTP pool](http://en.wikipedia.org/wiki/NTP_pool). So what it basically will do is :

>The NTP pool is a dynamic collection of networked computers that volunteer to provide highly accurate time via the Network Time Protocol to clients worldwide.

So that is what we want. One of such service is [here](http://www.pool.ntp.org/en/). So to maintain a server which is up and running exactly with proper time, then you need to do :

+ Install NTP in your server.

+ Config it to follow the NTP pool project via internet. 

So now our system will look something like :



	      NTP POOL
	      ^  |
	      ^  |
	      ^  |		
	    ^  |			   
	----------------------
	|                    |
	| Your Network 1     |
	|                    |
	----------------------	 

The `^` symbol in the above diagram is your network system are asking the correct to NTP pool via Internet. And in turn the NTP pool will synchronize your network with the current standard time according to your server location. Ya current time in India is not exactly same as the current time in America. So NTP pool will synchronize the time based on your server location. 


>For Geeks: Actually NTP can fail! Think simply, what will happen if there is a problem in internet which makes the time packets to arrive late than the correct time? Think about it. I shown one of the methods to get the correct time. Setting up NTP server is simple to explain and I choose it. There are other aways too. But I dont have *time* to explain it here. 

And its time to close my editor and leave to my friends place! See you, next *time* take care! 


I just simply wrote this blog post in a text editor(gedit). So there can be splling mistke, may would has gramatical flaws badly. If that is the case leave a comment.

Thanks for reading my post. If you have any doubts, feel free to post the comment. Comments are welcome! Suggestions welcome. 


###That's all folks!

