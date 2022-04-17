---
layout: post
title:  "git revert multiple commits"
date:   2022-04-17 1:11:15 -0500
categories: git
---
Git revert is a command that allows a user to revert a history of the git repository by applying a command:

{% highlight bash %}
git revert <hash_of_the_comit_to_revert>
{% endhighlight %}

this command is useful and helps to create a commit without deleting this commit from the history. This way the history of the repo stays the same, but with the necessary commit removed. As a result of the git revert command there going to be a commit that reverts a specific commit from a branch.

On practice there can be several commits that needs to be deleted and it can be problematic. Let's look at these cases:
1. Revert multiple commits starting from a given (including it). In this case the reverting operation will revert commits starting from <hash_A> commit till HEAD of the branch:

{% highlight bash %}
$ git revert --no-commit <hash_A>^..HEAD  
$ git commit -m 'message'
{% endhighlight %}

2. Revert multiple commits that include merge commits.

{% highlight bash %}
$ git diff --binary HEAD <hash_A> | git apply
{% endhighlight %}

There are other different variation of git commands that can allow revert.