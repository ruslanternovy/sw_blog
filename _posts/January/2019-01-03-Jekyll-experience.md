---
layout: post
title:  "Jekyll experience"
date:   2019-01-02 17:01:45 -0500
categories: web
permalink: /:categories/:year/:month/:day/:title.html
---
Using Jekyll is fun. You have to follow certain steps to make it work properly. In this post I am going to write about my experience of working with Jekyll.

1. Working with Jekyll will be a bit tricky if you publish your Jekyll website/blog on GitHub. In particular working with _config.yml where you have to put "baseurl" setting.
For testing purposes on local host there should be nothing. When you publish a website with the updates, make sure you add "baseurl" setting. In my case it is:
baseurl: "sw_blog"
