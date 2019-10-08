---
layout: post
title:  "Frequently used docker commands"
date:   2019-10-07 1:11:15 -0500
categories: docker
---
Docker. Finally I got my hands on working with docker. In this article I am going to briefly go through the main commands that I use in my practice with docker software. Later I am going to describe each command in details with examples.

Let's start with run!
{% highlight bash %}
docker run
{% endhighlight %}
These commands specifies an image to derive a docker container from using options followed by commands and arguments.
{% highlight bash %}
docker run [OPTIONS] IMAGE[TAG] [COMMAND] [ARGUMENTS]
{% endhighlight %}
