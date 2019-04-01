---
layout: post
title:  "Installing boost libraries on Mac"
date:   2019-04-01 1:11:15 -0500
categories: boost
permalink: pretty
---
This post is a reminder for how to get and install [boost libraries](http://www.boost.org) on Mac computer using brew.

1. Press Command+Space and type Terminal and press enter/return key.
2. Run in Terminal app:
{% highlight bash %}
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null
{% endhighlight %}
If the screen prompts you to enter a password, please enter your Mac's user password to continue. When you type the password, it won't be displayed on screen, but the system would accept it. So just type your password and press ENTER/RETURN key. Then wait for the command to finish.
3. Run:
{% highlight bash %}
brew install boost
{% endhighlight %}
The output should be similar to:
{% highlight bash %}
brew install boost
==> Downloading https://homebrew.bintray.com/bottles/boost-1.69.0.mojave.bottle.tar.gz
######################################################################## 100.0%
==> Pouring boost-1.69.0.mojave.bottle.tar.gz
🍺  /usr/local/Cellar/boost/1.69.0: 13,717 files, 488.8MB
==> `brew cleanup` has not been run in 30 days, running now...
Removing: /Users/YourUserName/Library/Caches/Homebrew/node--11.6.0.mojave.bottle.tar.gz... (12.7MB)
Removing: /Users/YourUserName/Library/Logs/Homebrew/icu4c... (64B)
Removing: /Users/YourUserName/Library/Logs/Homebrew/node... (64B)
{% endhighlight %}
That's it! You can now use boost.
