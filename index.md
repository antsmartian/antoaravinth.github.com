---
layout: page
title: Blog on what I love!
tagline: Supporting tagline
---
{% include JB/setup %}


## HI ALL. 


### About me:
Nothing much about me. I'm a guy who have just finished my Engineering (B.E) and working as an intern in [Juspay](http://juspay.in/).
I certainly love doing some stuffs with programming languages like Java, Groovy , C#. Recently fallen in love with bash scrip-
-ing. Love to solve programatic problems. Always eager to learn new things in current software field. Ah! Thats much enough about me.


###About this blog:
I will be trying to blog on what I seems to be very interesting. Probably I will cover some of the nice techniques and inner workings of
certain languages in my posts. After its a blog on what I love and what I hunger for! Apart from it this blog runs on Jekyll.



## My all posts..

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


## To-Do:

This theme is still unfinished. If you'd like to be added as a contributor, [please fork](http://github.com/plusjade/jekyll-bootstrap)!
We need to clean up the themes, make theme usage guides with theme-specific markup examples.


