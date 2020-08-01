---
layout: post
title:  "Jenkins in docker"
date:   2020-07-31 1:11:15 -0500
categories: Jenkins
---
This is a first post from the series about how to run Jenkins in a Docker container.
The end goal is to spin up a docker container with Jenkins building a Golang code.

This post is dedicated setting up Jenkins that is run in a docker container.

First step I took is a docker installation. Docker software was installed fairly easy.
I was following the instructions from the [docker installation page](https://docs.docker.com/docker-for-mac/install/)

Once Docker software was installed on my laptop, I run a command that downloads Jenkins image and spins up a container using a command:
{% highlight bash %}
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins jenkins/jenkins
{% endhighlight %}
Next step will be going to setup Jenkins environment. For this go to the address http://localhost:8080
Once on the page Jenkins will propose to enter admin password. The instructions for where to get a password are displayed on the page.
After entering a password there will be main dashboard where using search line find and select next plugins:
1. Publish over SSH
2. SSH
3. Golang plugin
4. xUnit

Also remove unnecessary plugins selected by default
1. Ant
2. Subversion

Click "Apply" in the end of choosing the list of the plugins that need to be installed.
Finally you will see a ![page](./assets/Jenkins_ready.jpg)
Click 'Start using Jenkins'

In part two we will walk through the setting up Jenkins for building a simple project.
