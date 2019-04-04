---
layout: post
title:  "Running boost program on Mac"
date:   2019-04-01 1:11:15 -0500
categories: boost
---
In parallel to my main project I decided to keep developing my c++ skills. Recently I have installed boost library on my Mac computer and decided to write
some code to test how the library works. In particular the program that I wanted to run is a multithreaded program
program that runs a simple functionality in the created thread. The program was taken from the examples of the [boost library](https://theboostcpplibraries.com/boost.thread-management#ex.thread_01)

{% highlight cpp %}
#include <boost/thread.hpp>
#include <boost/chrono.hpp>
#include <iostream>

void wait(int seconds)
{
  boost::this_thread::sleep_for(boost::chrono::seconds{seconds});
}

void thread()
{
  for (int i = 0; i < 5; ++i)
  {
    wait(1);
    std::cout << i << '\n';
  }
}

int main()
{
  boost::thread t{thread};
  t.join();
}
{% endhighlight %}
And here is how I compile and link this program from the command line on my Mac:
{% highlight bash %}
$ g++ main.cpp -o boost -std=c++11 -I /usr/local/include -L/usr/local/lib -lboost_thread-mt -lboost_chrono-mt
{% endhighlight %}

Option *-I* can be omitted as long as you use standard paths for the include libraries(compiler option *-I*): */usr/local/include* and the list of the directories to be searched for libraries (compiler option *-L*): */usr/local/lib*

The line for compiling and linking the code after removing -I and -L options will look like this:
{% highlight bash %}
$ g++ main.cpp -o boost -std=c++11 -lboost_thread-mt -lboost_chrono-mt
{% endhighlight %}

Just in case if you decide to create a Makefile for your project where the convenience of compiling and linking a bunch of files together would be appreciated, here is a Makefile example:
{% highlight bash %}
flags = -std=c++11 -I //usr//local//include -L//usr//local//lib -lboost_thread-mt -lboost_chrono-mt
all:
  c++ ${flags} main.cpp -o boost
{% endhighlight %}
And the simple variant that uses standard paths for includes and libraries:
{% highlight bash %}
flags = -std=c++11 -lboost_thread-mt -lboost_chrono-mt
all:
  c++ ${flags} main.cpp -o boost
{% endhighlight %}
