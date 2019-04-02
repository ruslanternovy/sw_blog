---
layout: post
title:  "Running boost program on Mac"
date:   2019-04-01 1:11:15 -0500
categories: boost
---
In parallel to my main project I decided to keep developing my c++ skills. Recently I have installed boost library on my Mac computer and decided to write
some code to test how the library works. In particular the program that I wanted to run is a multithreaded program
program that runs a simple functionality in the created thread. The program was taken from the examples of the [boos library](https://theboostcpplibraries.com/boost.thread-management#ex.thread_01)

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
And here is how I launched this program from the command line of my Mac:
{% highlight bash %}
$ g++ main.cpp -o boost -std=c++11 -I /usr/local/include -L/usr/local/lib -lboost_system -lboost_thread-mt -lboost_chrono-mt
{% endhighlight %}
