---
layout: post
title:  Welcome to My Inn! - Grab a Seat By the Fire, Class is in Session
date:   2015-03-29
categories: jekyll update
---
Over the past year I have grown obsessed with Blizzard Entertainment's online collectible card game Hearthstone. In the game, two players enter an arena at a time, each armed with their own deck of 30 cards. Players trade turns playing minions and spells until one player's life total falls to zero. OK, so that is a bit oversimplified. Just trust me on this, it's an awesome game (and it's "free-to-play" - yes, that is in quotes on purpose).

Anyway, we were given the task of explaining Ruby Classes this week and were told that it would be helpful if we modeled a real-world object as an example. Now, this is the part where you ask, "You were told to model a real-world object and you chose an online card game that has no physical properties at all?" Sure did, smart ass.

Classes in Ruby give you a way to easily create numerous objects that essentially behave the same way and share a similar batch of methods. You do this by instantiating the class, or creating objects that are instances of that class.  In our Hearthstone example, we will define a class called Deck, which we will instantiate with different decks (or arrays that are passed as the initial argument). We will then create individual methods in the class (or instance methods - because they are intended to be used by all instances of a class) to shuffle the deck, draw some cards, add some cards to our deck, show our hand and check how many cards are remaining in our deck. These are all things that need to occur in a game of Hearthstone (the analogy is looking pretty good now, huh?).

{% highlight ruby %}
class Deck
  def initialize(card_deck)
    @card_deck = card_deck
    @my_hand = [ ]
  end
{% endhighlight %}

We start by saying 'class Deck', which lets Ruby know that we are creating a new class named Deck.  We then create our first method, initialize, which takes an array of strings (cards) as an argument. This method is called initialize because it will automatically be run each time we create a new object of the Deck class We then declare and set our first two instance variables. The ‘@‘ sign in front of the variable name is a way for other Ruby developers to know you are talking about an instance variable. Instance variables are accessible in any method throughout a single instance (or one deck, in this case) of the class. We set our deck of cards equal to our input array and set our hand to an empty array.

{% highlight ruby %}
def shuffle
  @card_deck.shuffle!
end
{% endhighlight %}

Next up is another instance method, which we have named shuffle. Here we tell Ruby to take our instance variable (which of course is accessible in this method because it is an instance variable), shuffle it and return it.

{% highlight ruby %}
def draw(amount)
  (amount).times do
    @my_hand << @card_deck.pop
  end
end
{% endhighlight %}

Now that we have shuffled our deck, we define an instance method to draw some cards. We do that by passing in an integer as our argument, which will determine how many cards we draw. The argument is used to run a .times loop to push that specific amount of cards from our card deck and into our hand.

{% highlight ruby %}
def add(card)
  @card_deck << card
  p "Added #{card} to your deck!"
end

def display_hand
  p @my_hand
end
{% endhighlight %}

Here are two more instance methods that will print a message to the screen. Our add method will add the card that you pass as an argument to our existing deck, be sure to not go above 30 cards though, that would be cheating!. The second method will display your hand by printing it to the screen as an array of strings.

{% highlight ruby %}
def cards_remaining
  p "You have #{@card_deck.length} cards remaining."
end
{% endhighlight %}

In Hearthstone, each deck can only have 30 cards in it. When you run out of cards, you begin taking incremental damage for each non-card that you draw. So here we define a method that will print out how many cards you have remaining in your deck, this will help you avoid a nasty fatigue death.

{% highlight ruby %}
my_deck = [“Execute”, “Execute”, “Shield Slam”, “Shield Slam”, “Whirlwind”, “Fiery War Axe”, “Fiery War Axe”, “Armorsmith”, “Armorsmith”, “Cruel Taskmaster”, “Cruel Taskmaster”, “Shield Block”, “Acolyte of Pain”, “Acolyte of Pain”, “Big Game Hunter”, “Death’s Bite”, Death’s Bite”, “Brawl”, “Harrison Jones”, “Sludge Blecher”, “Sludge Belcher”, “Shieldmaiden”, “Shieldmaiden”, “Sylvanas Windrunner”, “Dr. Boom”, “Grommash Hellscream”, “Ragnaros the Firelord”, “Sneed’s Old Shredder”, “Alexsrasza”]
{% endhighlight %}

{% highlight ruby %}
warrior_deck = Deck.new(my_deck)
warrior_deck.add("Loatheb")
#=> "Added Loatheb to your deck!"

warrior_deck.shuffle
warrior_deck.draw(4)
warrior_deck.display_hand
#=> ["Big Game Hunter", "Sneed's Old Shredder", "Alexstrasza", "Shield Slam"]

warrior_deck.cards_remaining
#=> "You have 26 cards remaining."
{% endhighlight %}

Now we have created our deck, which I have populated with 29 cards. We substantiate our class by setting warrior_deck equal to a new instance of our class (with Deck.new) and pass in the deck we want to use. Realizing we only had 29 cards in our deck, we add Loatheb, to fend off those pesky combo druids. We then shuffle our deck and draw four cards. Ooof, that is a slow start. Rack up another win for that face hunter opponent of yours…

As I said, this is a very basic implementation of a very complex game, but you should now get the gist of how powerful the Ruby class system really is. We could add more functionality to our class by adding methods to manage our mana progression, board state and card stats. Pretty soon we would be able to play a real game of Hearthstone. Take that Blizzard!