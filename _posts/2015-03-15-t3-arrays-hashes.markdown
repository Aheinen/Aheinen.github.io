---
layout: post
title:  Stop... Ruby Time! - You're a Wizard, 'Array!
date:   2015-03-15
categories: jekyll update
---
I know what you are thinking... MC Hammer and Harry Potter references in the same post, this guy is awesome! And let me assure you sir/madam, I most definitely am awesome. Anyway, on to learning about the fun world of Hashes and Arrays!

 Arrays and Hashes are two similar, yet different ways of storing objects in ordered lists in Ruby. They are similar in the sense that they can each store any object (number, string, boolean, arrays, hashes, etc.), but are different in the way that they store them. Arrays index objects in numerical order, while Hashes are stored in key/value pairs (where each unique key stores a single value). Hashes are also ordered in the sense that Ruby remembers the order that the keys were entered in.

The easiest ways to create a Hash or an Array is with the .new method or the respective literal constructor.

{% highlight ruby %}
my_array = Array.new(size, initial_value)
my_hash = Hash.new(default)
{% endhighlight %}

By calling the .new method, it will create an empty Array/Hash if no arguments are passed. If you choose the .new method to create an Array, you have the option of declaring its size by inserting an integer as your first argument. If you give the method a second argument, each object in the array will be initialized to contain that argument. Each object in the array will be initialized as nil if you do not provide a second argument.

If you choose the .new method to create a Hash, you can set the default value for a key that does not exist.

Retrieving Values from an Array:
{% highlight ruby %}
my_array = [1, 2, 3]
puts my_array[0]
#=> prints 1
{% endhighlight %}

Above we define my_array and populate it with the integers 1, 2 and 3. In the next line we call puts (which tells our computer to print out the following statement to our screen) on the value that is indexed at position 0 in my_array. Always remember that computers begin counting at 0. Therefore, this statement would print the value 1 (which is the object in the 0th position of our array) to our screen.

Retrieving Values from a Hash:
{% highlight ruby %}
my_hash = {elephant: 1, dinosaur: 2, hippopotamus: 3}
puts my_hash[:hippopotamus]
#=> prints 3
{% endhighlight %}

Hash keys can be strings followed by a hash-rocket (“key_1” => “value_1”) or a symbol,which is always followed immediately by a colon (key_1: “value_1”). In the example above, we create a Hash with a symbol as our key. In the second line of the code, we are telling the computer to print the value associated with the key “:hippopotamus” to our screen (yes, the colon is in the right place. It goes on the left side of the key when you are calling it). Just be sure to remember that each key must be unique in a given Hash, however multiple keys can point to the same value.

So what did we learn today? Arrays and Hashes are a way of storing objects in easily accessible lists. Each value in an Array is associated with its specific numeric position, while each value in a Hash is associated with a unique key. Finally, we can create Arrays/Hashes by enacting the .new method or using the literal constructor.