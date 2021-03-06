---
layout: post
title:  Is there an echo? - Is there an echo?
date:   2015-03-22
categories: jekyll update
---
The enumerable module is a special module in Ruby that is included in most collection objects. This particular module allows the user many different ways of iterating through a collection of data. By defining the instance method named each, the particular class gains access to numerous related behaviors. Each is a very common iterator in Ruby that will iterate (or step through) a specific data set one object at a time. Each takes a block of code as an argument and enacts that block on each object that it iterates over.

Below is a small example of how .each would work on a basic array. We call .each on my_array and tell Ruby to take each number in our array (we use the pipe brackets, to refer to each object in the set), multiply it by two and print it out to our screen. Therefore, we get 2468 printed out to our screen. Now be careful! The each method will always return the original array it was called on (That’s why we see >>[1, 2, 3, 4] at the bottom of our example).

{% highlight ruby %}
my_array = [1, 2, 3, 4]
my_array.each { |num| print num * 2 }
#=> prints 2468
#=> returns [1, 2, 3, 4]
{% endhighlight %}

OK. Now that you know a bit more about enumerators and the .each method in Ruby, lets dive into another enumerable method. Like each, the enumerable method cycle takes a block of code as an argument. Unlike each, cycle also takes an optional integer value as an argument.

{% highlight ruby %}
cycle(n = nil) { |object| block }
{% endhighlight %}

Cycle calls the given block on each object that we iterate over in the data set n times. If a value for n is not given, the iteration will go on forever. Let’s see what happens when we use the same block as we did with each, but lets pass cycle the integer value of 3.

{% highlight ruby %}
my_array = [1, 2, 3, 4]
my_array.cycle(3) { |num| print num * 2 }
#=> prints 246824682468
#=> returns nil
{% endhighlight %}

OK, so that wasn’t that shocking… We had the same thing printed to our screen as we did when we used each. The only difference is that the cycle method allowed us to iterate over my_array two extra times without having to make separate calls to do so. What is interesting though, is that nil was returned. Unlike each, nil will always be returned if a block is passed to cycle, but an Enumerator will be returned if no block is given.

To recap: The enumerable module allows classes to have many different ways of iterating through a collection of data. Each is one of the most common methods that executes a block of code on each object in a data set. Cycle works like each, but takes a second argument (an integer) that tells the method exactly how many times to iterate over the set. If no integer argument is given, cycle will run on forever!