---
layout: post
title: ". . . learning from my mistakes . . . "
description: ""
category: 
tags: []
---
{% include JB/setup %}

Hi all, I hope you people are doing good as like me. Its been long since I wrote a blog [post][1]. 
[1]:http://antoaravinth.github.com/2012/11/12/latency-check-tool/

On wednesday 13/02/13 night, I was looking into my system and was downloading some books. All of a sudden my system got frozen. 
Not sure why did it happen, but it happened. 

I have no other option rather then hitting my CPU's restart button. The system reboots and I waited. I waited for few min. . .
Time went away . . . I waited for some 20 min or so. . . Nothing appeared on my system screen (apart from the message
detecting the IDE drivers) ! Something went seriously wrong! :/ I was like WTH I did wrong!

Luckily I had a Ubuntu Live Cd on my desktop. I used that too boot so that I can atleast search google to find out solution.

But wait a min, how do I search? Can I search "I rebooted my system and it didn't booted up again". That looks vague. Nethier google
doesn't give any interesting results. 

But I guessed my [file system][2] would have been crashed. I guessed this because I have "restarted" the system when it was downloading 
some file which might left the system file state in inconsistent.
[2]:http://en.wikipedia.org/wiki/File_system

That was a guess. But how do I recover from it? The only way was to learn how Ubuntu uses its own file system.


Learning from my mistake
--------------------------------------

It was almost 11.30 pm and I hooked deep into the implementation of the Ubuntu file system and I started to get some interesting information. 

More informally this is what Ubuntu does behind the scenes. To store a file it splits each file into pieces and stores it in what is called
Blocks. Wiki says the use of block:

    In classical file systems, a single block might contain only a part of a single file. 

which means a single file is splitted and stored in different blocks. Note that here the Operating System manages a list of free blocks, 
which can be used when new datas/files are been saved. Also keep in mind the OS uses some algorithms for defining the size of the blocks initially.
Keep in mind this free list concept which I will come to that later.


So obviously some of the blocks which are main in terms of booting the system would have got corrupted. Again that was a guess.

Googling out I found that they are called as "bad blocks". But I made a wrong guess, bad blocks are caused my what is called as 
[bad sectors][3]. And bad sectors are bad. They are permanent damage to my hard disk. So the root of the problem should be bad sectors. 
But why did a disk sector goes bad sector in my case?
[3]:http://en.wikipedia.org/wiki/Bad_sector

Wiki says the bad sectors can be :

    1)physical damage to the disk surface 
    2)sometimes sectors being stuck in a magnetic
    3)digital state that cannot be reversed 
    4)failed flash memory transistors

not sure what would have caused for my case. Blogs that are results in my google search doesn't show how to solve the issue. 

Keep in mind that bad sectors cause bad blocks. So the interesting info here is how to get out the bad blocks from my disk. 

Luckily ubuntu has what is called `e2fsck` which is used to check a Linux ext2/ext3/ext4 file system.

I ran the commands that are given in some blogs and rebooted my system. Whola! The system rebooted without any problem. But I was
not satifised. This tricky genius `e2fsck` command does something interesting under the hood. Whats that?


As going deeper in how OS boots, I found that when an operating system reads a bad block/bad sector its bad. It can't get any info out of it
and it waits ( this is my guess ). I guess probably this was the reason I was waiting for 20 long min when my system get crahsed!!

`e2fsck` command is quite genius this is what it does:
    
    1) Finds the bad block (how it finds it is even more intersting
        which I wont share in this blog)
    2) And sets up a BIT if a particular block is a bad block.

As its sets up the BIT, the OS knows that "Oh!, this sector is bad, so I shouldn't try reading/accessing it" and it skips.

I said earlier about the free list that OS will maintain which are the links to the next free blocks the OS can search into when users create 
new files. If no free blocks available then your hard disk is out of storage.

The beauty of `e2fsck` is that, it even removes the bad sectors from those free list; Making sure that any other files aren't been 
stored at this bad block. 

Cool. It was nice to get deeper into OS and solve my issue. Cool that I learned so much on that day. 

Shutting down my system, I said internally "bad block made my day!" 


####Thats all folks!





