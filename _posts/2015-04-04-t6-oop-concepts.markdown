---
layout: post
title:  Modeling Modules - Class/Module Face off
date:   2015-04-04
categories: jekyll update
---
Classes in Ruby allow the user to create individual objects. This is done by instantiating the class, or creating objects that are instances of that class. Each instance of the same class then has access to specific instance methods which were defined in our class definition. This blog post will discuss the differences and similarities between classes and modules.

In Ruby, each class can only be assigned one superclass. The subclass can borrow instance methods from its superclass, which is also known as inheritance. While each class can only have a single superclass, the initial subclass has access to the superclass of its superclass. The ladder effect continues until we reach BasicObject, which is the farthest you can go. What happens if we create a bunch of objects from multiple classes, but we need to carry over some of the same functionality? We could rewrite that code into each of our classes or we could create a new module.

A module allows us the ability to store code that can be used by multiple classes. While each class can only have a single superclass, there is no limitation to how many modules can be mixed in.

{% highlight ruby %}
module Something
end
{% endhighlight %}

A module definition begins with the keyword “module”, much like how we begin our class definitions with the word “class”. We can then define methods inside the module that may be used by any class that mixes the module in.

{% highlight ruby %}
include Something
prepend Something
{% endhighlight %}

We can mix our module into any number of classes by calling “include” or “prepend”. Include signifies that each object of that class should search the designated module for a specific method after searching the base class, but before searching the superclass. By prepending a module, you tell each object to search the module for the functionality first, before we even attempt to search the base class.

{% highlight ruby %}
class OurClass
  include Something
  include SomethingElse
  include ThisOneFirst
end
{% endhighlight %}

Mixing in modules works like a stack data structure in the sense that the last module mixed in will be the first module searched when an object is looking for a particular method. In the above example, ThisOneFirst will be the first module searched for functionality even though Something and SomethingElse were included in our class first.

Though modules help add tremendous flexibility to our programs, entities are generally best modeled in classes because modules don’t have instances. We should utilize modules to help model characteristics or properties of the entities. At the end of the day, modules are just a way of adding functionality to our classes, while making it such that we never have to repeat ourselves.