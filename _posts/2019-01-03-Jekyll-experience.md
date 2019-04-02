---
layout: post
title:  "Jekyll experience"
date:   2019-01-02 17:01:45 -0500
categories: web
permalink: /:categories/:year/:month/:day/:title.html
---
Using Jekyll is fun. You have to follow certain steps to make it work properly. In this post I am going to write about my experience of working with Jekyll and periodically update this post while learning.

0. To set up a Jekyll blog on your computer locally go to this link and follow the instructions. A documentation about creating a Jekyll website you can find at the official [Jekyll website](https://jekyllrb.com/docs/)

1. [Jekyll step-by-step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) was a very useful resource for me to set up the initial layout of my blog. Just follow every step they describe in the menu.

2. Jekyll uses the Liquid templating language to process templates. Liquid parses all instances of {{, }}, {%, %} as Liquid constructs. To tell Liquid not to parse such instances, wrap the code inside Liquid's raw blocks: {% raw %}<code/>{% endraw %}
