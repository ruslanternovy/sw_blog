---
layout: post
title:  "Singleton"
date:   2019-04-26 1:11:15 -0500
categories: C++
---
On one of the interviews I was asked to implement one of the coding patterns. First idea was to implement a regular singleton class:
{% highlight cpp %}
class Singleton {
  static Singleton* instance;
public:
  ~Singleton();
  static Singleton* getInstance() { return instance; }
};
{% endhighlight %}
Simple class - nothing is new. The answer to my implementation was how we can make it more simple. I didn't know the answer. It turned out that c++11
{% highlight cpp %}
class Singleton {
public:
  ~Singleton();
  static Singleton& get(){
    static Singleton instance;
    return instance;
  }
};
{% endhighlight %}
And the last little note about implementing Singleton class will be deleting methods that might be potentially dangerous in terms of ruining the idea of the singleton template. Just delete implementation of the copy constructor and assignment operator:
{% highlight cpp %}
class Singleton {
public:
  ~Singleton();
  static Singleton& get(){
    static Singleton instance;
    return instance;
  }
  Singleton(Singleton const&)               = delete;
  void operator=(Singleton const&)          = delete;
};
{% endhighlight %}
