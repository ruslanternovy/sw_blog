---
layout: post
title:  "Jekyll experience"
date:   2019-01-02 17:01:45 -0500
categories: web
---
Using Jekyll is fun. You have to follow certain steps to make it work properly. In this post I am going to write about my experience of working with Jekyll and periodically update this post while learning.

0. To set up a Jekyll blog on your computer locally go to this link and follow the instructions. A documentation about creating a Jekyll website you can find at the official [Jekyll website](https://jekyllrb.com/docs/)

1. [Jekyll step-by-step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) was a very useful resource for me to set up the initial layout of my blog. Just follow every step they describe in the menu.

2. Jekyll uses the Liquid templating language to process templates. Liquid parses all instances of {% raw %}{{, }}{% endraw %}, {% raw %}{%, %}{% endraw %} as Liquid constructs. To tell Liquid not to parse such instances, wrap the code inside Liquid's raw blocks: {% raw %}<{{<your code is here>}}>{% endraw %}

3. [2019-04-04] I have bumped into a little issue that was causing an error message in the Jekyll log file:
{% highlight bash %}
[2019-04-04 13:05:44] ERROR '/favicon.ico' not found.
{% endhighlight %}
[The solution to this problem](https://github.com/jekyll/jekyll/issues/7329#issuecomment-431699560) was to just generate a new file with name 'favicon.ico' in the root directory of the local Jekyll website:
{% highlight console %}
$ touch favicon.ico
{% endhighlight %}
