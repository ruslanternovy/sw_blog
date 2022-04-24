---
layout: post
title:  "Jekyll gh-repo package dependency troubleshooting"
date:   2022-04-24 1:11:15 -0500
categories: Jekyll
---
Jekyll is a tool that provides pretty convinient and safe way of publishing articles in gh-pages.

At the same time it's been awhilw since I posted on gh pages. Some of the package versions were obsolete. So I had to take some steps to update them. The second problem was that I reinstalled operating system on my computer. That removed all packages on my laptop. While there is a procedure for how to install Jekyll and it's dependencies I didn't find the way to update the outdated packages the configs of which were already in the repo. This article provides commands that helped me to resove and commit those dependencies.

To have a local repo of my gh-pages I cloned the repo and had to execute the next commands:

1. Install Jekyll dependency:

{% highlight bash %}
sudo gem install "jekyll"
{% endhighlight %}

2. Check jekyll version.

{% highlight bash %}
jekyll -v
{% endhighlight %}

The execution of this command may provide additional command(s) that may be necessary to fix dependencies:

{% highlight bash %}
bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java
{% endhighlight %}

Note: that this command isn't mandatory to execute as it was a suggestion to execute in order to lock dependencies.

3. Install bundle command to run the site locally:
{% highlight bash %}
bundle install
{% endhighlight %}

After this I was successfully able to commit into gh-repo.
