---
layout: post
title:  "Vim shortcuts"
date:   2019-04-15 1:11:15 -0500
categories: miscellaneous
---
Since I use a lot vim for writing test programs just to check how this or that functionality works I use vim text editor a lot. It lets me quickly implement necessary code in any language I am working with. I don't do much editing, but still decided to create my own cheat sheet for vim commands.

{% highlight bash %}
[Control][b] - Move back one full screen
[Control][f] - Move forward one full screen
[Control][d] - Move forward 1/2 screen
[Control][u] - Move back (up) 1/2 screen
{% endhighlight %}

My association for remembering those shortcuts at least first two will be to remember letter 'b' stands for backwards, letter 'f' stands for forward. Letters 'd' and 'u' stand respectively for 'down' and 'up'.

Navigation in vim by word
{% highlight bash %}
w - jump to the beginning of the next word.
W - jump to the beginning of the next word that can contain a punctuation.
b - jump backwards to the beginning of the word.
{% endhighlight %}

One useful command for replacing
{% highlight bash %}
:%s/string to replace/replacement string/g
{% endhighlight %}
Last g in the command stands for globally which means provide replacement globally
There can be another variant of the replacement commands which includes 'gc' in the end of the commands instead of just 'g' which means 'replace with confirmation'.
