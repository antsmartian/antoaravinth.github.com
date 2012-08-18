---
layout: post
title: "Its Time To Relax My-Self"
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hi all, this is my second blog post. I hope you know the conventions used in my blog, if not you can always read it from
[here](http://antoaravinth.github.com/2012/07/31/hello-world/). 

In this blog post I will explain you how do I relax myself with the help of Ubuntu.

Oki I need to finish up writing this blog post in half an hour(the reason of it, will be clear at end of this post).

I'm a guy who can maximum concentrate on a single subject at most half an hour. Say I'm reading Physics, I can fully concentrate on Physics only for half an hour and after that I can't. I need some refrehsing after that-- something like hearing to song.

One of my favourite songs out this in year is [here](http://www.youtube.com/watch?v=Er3epSUp6UE). 

So after reading Physics for half an hour, I want to hear this song. Oki that doesn't seem to be very intersting! Right? I can go to the song location and double click and hear to it. Ah! More work is needed. I was thinking how to *automate* this process.That is, somehow I say to my system that, after half an hour of time (from my work being started i.e reading Physics in this case) go and play this particular song. And that's what exactly I'm going to explain in remaining post. 

Alright! Again, if this doesn't seems interesting to you, you can skip reading my post. 

Came here? Interested reading? Cool. Lets start. So there are plenty of ways to *automate* this process. For example, I can write a java program which starts a thread and sleeps for half an hour and goes to the music location and plays it with the help of [music api](http://docs.oracle.com/javase/7/docs/api/javax/sound/sampled/package-summary.html). But again that requires lot of work. So let me show you how I solved this problem with single line of code! (strictly speaking, it should be one line of *commands*.)


So let me open up my terminal in Ubuntu. Will try running the following command `songs`. I will get this error: 

	No command 'songs' found, did you mean:
	Command 'sng' from package 'sng' (universe)
	songs: command not found

Yes, there are is no command called `songs` in Ubuntu. So let us create one! So what we need is to play a particular song after half an hour time. In ubuntu, there is a command called `play`, which lets you to hear song from command line like this:

	 play ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3

That is I'm passing the location of Oh Baby Girl song to `play` command. 

####Note: `play` command is not available default in Ubuntu. You need to install this package:
	sudo apt-get install sox libsox-fmt-mp3

So doing so: 
	
	play ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3

Will play the song and will get the output as:

	 File Size: 7.38M     Bit Rate: 260k
	 Encoding: MPEG audio    Info: 2012
	 Channels: 2 @ 16-bit   Track: 01/09
	 Samplerate: 44100Hz      Album: Maalai Pozhudhin Mayakathilaey :::tunesinn.blogspot.com:::
	 Replaygain: off         Artist: Hemachandra, Achu
	 Duration: 00:03:46.98  Title: Oh Baby Girl
	 In:4.71% 00:00:10.68 [00:03:36.30] Out:471k  [   ===|=-    ] Hd:0.0 Clip:0  

That is pretty cool. Now we have found a way to play a song from command line. Now we need to look for half an hour waiting part before calling the `play` command. That is very simple as well. 

There is a command called `sleep` in Ubuntu, which allows your system to sleep for certain time:

	sleep 30000

Allows your system to sleep for `30` minutes. Bingo! So our pseudocode will look like: 

	sleep 30000
	play ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3

That looks super cool. Oh oki, I can figure out what your thinking right now; I promised to solve this problem in one line of code. Isn't? I'm not a cheater in anyway!( :D ). So let us *prove* that now; In ubuntu, you can terminate a command with `;` as with other languages. So 
our code will become:

	sleep 30000; play -q ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3

Cool. So now we need to do simply like this:
	
	echo 'sleep 30000; play -q ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3' > songs

####WatchOut: This is a single line of command, due to spacing reason it might be rendered as double line!

This line will open up the `songs` file(if any or will create a new one). And put the line `sleep 30000; play ~/Desktop/SONGS/01\ -\ Oh\ Baby\ Girl.mp3` into that file and save it!

So we have our `songs` shell script! Now we need to make it executable :

	chmod +x songs

That's it. Now you can run your shell script as:

	./songs

And after half an hour time, your song will be played. Now the question is you cannot run `./songs` from the folder where `songs` file is not present. To solve this problem, you need to move `songs` to `/bin`:
	
	sudo mv songs /bin

Thats it! Now you have command called `songs` which you can run as normal command from anywhere. And go and do your work. After the time have passed away. The song will be automatically played. 

Oh guys, its been half an hour since I wrote this post. My song (Oh ho oh ho. . . ) has been started to play. So 

###Its Time To Relax My-Self

I just simply wrote this blog post in a text editor(gedit). So there can be splling mistke, may would has gramatical flaws badly. If that is the case leave a comment.

Thanks for reading my post. If you have any doubts, feel free to post the comment. Comments are welcome!

And as always:

###Thats all folks!

#####Note: I could have made the `songs` command to recieve the song location from command line. But it requries some more work. And I want to keep this post as simple as I would. I hope I did that. And once the song has been started to play and if you wish to stop it, you can do `killall play`, from terminal. 

