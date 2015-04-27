---
layout: post
title:  The Teaching Continues - Putting a Bow on the Box Model
date:   2015-03-08
categories: jekyll update
---
Close your eyes for a second. Listen to my soothing voice. Now take a deep breath and… OK. You don’t have to do any of that, just look at the image of a picture frame below while I tell you how simple the CSS ‘box model’ really is!

There are four main aspects to the box model: content, padding, border and margin. In our analogy below, the picture is our content, the space between the picture and the actual frame is our padding, the frame is our border and the space between this frame and other frames on our wall is the margin. I’ll pause a second here for effect. Is your mind blown? No? That sounds too easy? Well that’s because it is easy!

![Box-Model](https://github.com/Aheinen/phase-0-unit-1/blob/master/week-2/imgs/picture_frame.png?raw=true)

Sadly, I have to throw a wrench in our pretty little analogy. Imagine that we didn’t only put pictures inside frames in our houses. Imagine that everything we owned, including our own bodies were put into frames like this (this would make for some awkward social interactions, huh?). That is what the box model really means. Absolutely every bit of content we put on our web page exists inside a rectangular box.

You can use specific code on your CSS page to manipulate each of these aspects. The size of the content is set with the “width” and “height” commands. Padding and margin are set in similar manners. You can use long-hand notation to set the right padding or left margin by typing “padding-right” or “margin-left”. Alternatively, you can set all four sides at once by calling “margin: top dimension right dimension bottom dimension left dimension”. The border is set by calling “border: thickness style color”. While content, padding, border and margin all account for different portions of our box model, each one contributes to the overall width and height of our element.

{% highlight css %}
p {
  border-top: 1px;
  margin-right: 10px;
  padding-bottom: 5px;
}
{% endhighlight %}

{% highlight css %}
p {
  border: 1px solid black;
  margin: 10px 20px 10px 20px;
  padding: 5px 5px 10px 5px;
}
{% endhighlight %}


OK, let’s wrap it up (see what I did there?). The box model is the CSS version of a picture frame, except every element we put on a webpage exists in this virtual picture frame. The content, padding, border and margin of each of our elements can be set with specific code on our CSS page.
