---
layout: post
title:  Battle Royale - Ruby vs. JavaScript
date:   2015-04-11
categories: jekyll update
---
The more you learn, the more you feel like you don’t know. After four straight weeks of Ruby, we journeyed into the belly of the beast that is JavaScript. The more rigid structure/syntax of JavaScript is definitely the first notable difference when you make the switch from Ruby. I’m not sure my semicolon button was prepared for the hammering it took this week. All I know is I want my clean looking Ruby programs back!

The next thing you notice is that JavaScript will let you run pretty much ANYTHING. Want to multiply “fish” times “hello”? Sure, that makes sense. You get NaN (not a number) in return, but it will run! JavaScript has no type error and let’s you pass as many arguments you want into any function, which can be very confusing for a beginner such as myself. It’s like JavaScript wants to be the “cool” high school parent that lets their kid and his friends drink in their basement on Saturday nights.

OK, so I’m being a little harsh. There is a lot of cool stuff about JavaScript; constructor functions (which help create instances of an object), the “this” keyword and explicit returns, just to name a few. Not only that, but JavaScript does share a lot of similarities with Ruby. Let’s take a minute to talk about the similarities and the differences between objects in JavaScript and hashes in Ruby.

Both JavaScript objects and Ruby hashes hold sets of key/value pairs. They work similar to an array, except instead of accessing each value with a specific index number, we access it with a key. The keys are similar between the two in that they can be strings (surrounded in “ “) or be a variable name with a colon at the end (called a symbol in Ruby). These keys can house any value type (boolean, integer, function, etc.) in either language.

Below we show how we would define a hash/object and populate it with key/value pairs, how we would add key/value pairs after the original hash/object has been created and how to print the values to the console.

{% highlight ruby %}
#=> Ruby Hashes
#=> Define a hash with some key/value pairs inside
my_hash = {
  "key one" => "value one",
  key_two: "value two"
}

#=> Add a new key/value pair after a hash has been created
my_hash[:new_key] = "new value"

#=> Print the value associated with each key to the console
puts my_hash["key_one"]
puts my_hash[:key_two]
{% endhighlight %}

{% highlight javascript %}
// JavaScript Objects
// Define an object with some key/value pairs inside
var my_object {
  propertyOne: "value one",
  "property two": "value two"
};

// Add a new key/value pair after an object has been created
my_object.newProperty = "new value";

// Print the value associated with each key to the console
console.log(object.propertyOne);
console.log(object["property two"]);
{% endhighlight %}