---
layout: post
title:  "Unique elements in vector"
date:   2019-04-12 1:11:15 -0500
categories: interview questions
---
Sounds like a simple solution which it is, but it took me a bit over 5 minutes to implement this task. I started to implement tasks from testdome.com web resource as a recap of my knowledge.

The task is called "Merge names". Implement the unique_names method. When passed two vectors of names, it will return a vector containing the names that appear in either or both vectors. The returned vector should have no duplicates.

For example, calling unique_names(std::vector<std::string>{"Ava", "Emma", "Olivia"}, std::vector<std::string>{"Olivia", "Sophia", "Emma"}) should return a vector containing Ava, Emma, Olivia, and Sophia in any order.

{% highlight cpp %}
#include <iostream>
#include <vector>

void add_unique_names(const std::vector<std::string> &names
  , std::vector<std::string> &res)
{
    for(size_t i = 0; i < names.size(); i++)
    {
        std::string x = names[i];
        if(std::find(res.begin(), res.end(), x) == res.end()) {
            res.push_back(x);
        }
    }
}

std::vector<std::string> unique_names(const std::vector<std::string>& names1
  , const std::vector<std::string>& names2)
{
    std::vector<std::string> res;

    add_unique_names(names1, res);
    add_unique_names(names2, res);

    return res;
}

#ifndef RunTests
int main()
{
    std::vector<std::string> names1 = {"Ava", "Emma", "Olivia"};
    std::vector<std::string> names2 = {"Olivia", "Sophia", "Emma"};

    std::vector<std::string> result = unique_names(names1, names2);
    for(auto element : result)
    {
        std::cout << element << ' '; // should print Ava Emma Olivia Sophia
    }
}
#endif

{% endhighlight %}

Then I was browsing Internet to find an alternative solution to the problem and found [this implementation](https://github.com/walidAbbassi/TestDomeCpp/blob/master/MergeNames.cpp).

Essentially the author of the program create one list from both of them and then eliminates duplicates. Let's see who's approach is more efficient.

For this purpose I decided to find a [list of names](https://github.com/hadley/data-baby-names/blob/master/baby-names.csv) and to make several duplicates in it.

In addition to this I wrote a simple python script that extracts just names from the given list and organizes them in a file:
{% highlight cpp %}
import re

input = open("baby-names.csv")
output = open("just-baby-names.csv", "w")

listOfNames = []

for line in input:
        listOfNames += re.findall(r'"(.*?)",', line)

for name in listOfNames:
        output.write("%s\n" % name)

input.close()
output.close()

{% endhighlight %}

It turned out that my version of the code is really slow. I haven't done any other measurements but it looks like a call t o sorting takes up too much of the time. As a recap of what I saw in the code of the previous link from github I decided to implement the code. Here what I got:

{% highlight cpp %}
#include <algorithm>
#include <iostream>
#include <vector>

std::vector<std::string> unique_names(const std::vector<std::string>& names1
, const std::vector<std::string>& names2)
{
    std::vector<std::string> res;

    res.insert(res.begin(), names1.begin(), names1.end());
    res.insert(res.begin(), names2.begin(), names2.end());
    std::sort(res.begin(), res.end());
    auto it = std::unique(res.begin(), res.end());
    res.erase(it, res.end());

    return res;
}

#ifndef RunTests
int main()
{
    std::vector<std::string> names1 = {"Ava", "Emma", "Olivia"};
    std::vector<std::string> names2 = {"Olivia", "Sophia", "Emma"};

    std::vector<std::string> result = unique_names(names1, names2);
    for(auto element : result)
    {
        std::cout << element << ' '; // should print Ava Emma Olivia Sophia
    }
}
#endif
{% endhighlight %}

Just in case if you decide to try this examples and check performance, [here is a link on the data repository](https://github.com/ruslanternovy/data).
