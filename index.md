---
layout: base
title: Complexity Classes of Games
---

### Introduction 

_Computational complexity is the study of how difficult problems are._ In the same way that physics is not about building better rockets, but understanding the natural principles behind rocket construction, computational complexity is not about building better algorithms! Rather, it’s studying problems _themselves_ as separate, natural entities. [[^1]] Broadly speaking, we assign problems to classes denoted by inscrutable series of capital letters (**P, NP, PSPACE, EXPTIME, BQP**) depending on how quickly the problem becomes stupidly difficult to solve as you try more and more complicated versions of it. That difficulty is given in terms of the resources a computer would have to use. There are more complicated resources (like communicating with other computers) but here we’ll just think about time and space.

### What is a problem?

Let’s look at a simple example problem: “Given a number, is that number prime?” This is an interesting problem for a computer to solve because there’s an infinite amount of numbers. “Given a number less than twenty, is that number prime?” is not — the computer could just store a look-up table that tells it whether the number is prime or not, and solve it in no time! A wise man once said that “an algorithm is a finite solution to an infinite problem”.

This problem, which we’ll give the name PRIME, becomes only a _little_ more difficult as each of its values increases. That is, determining whether 1736598123657 is prime is certainly difficult, but it doesn’t take much longer than determining whether 1736598123653 is prime. Problems like this we call **P**, which stands for polynomial time — formally, if a problem is in the class **P**, solving the problem takes polynomially more time as the input increases. \\(c \cdot n^{x}\\) [Make this LaTeX definition in the webpage.] We’ll get to some other classes later.

![](img1.jpeg)

Before we move on to games, there’s some necessary jargon: we say that a problem has an infinite number of _instances_. In the case of PRIME, each instance is a number. In chess, our problem might be called WHITE-WINNING, which asks “given this initial position, does white have a _sure-fire_ way to win the game?” An _instance_ of WHITE-WINNING would be an arrangement of pieces on the board. So that we have an infinite number of instances, we generalize our chessboard from 8 squares by 8 to any number n squares by n. This allows us to learn more about chess in the 8 by 8 case by learning how much harder chess gets when you make it bigger. WHITE-WINNING is not in **P** — we’ll see what it is in later on.

[IMG HERE]

Now that you’ve seen some examples, maybe it will be easier to grasp this counterintuitive definition: **a problem is any mapping we can make from the natural numbers to a boolean (true or false, yes or no)**. [further topics: there’s more than decision problems] [Make this LaTeX definition in the webpage.]

### KLONDIKE: **NP** and **NP**-COMPLETE

For Klondike we examined if the game was solvable from an initial state. If you are not familiar with Klondike, it is also known as “classic solitaire” and it is preinstalled on most Windows versions. Of course, the randomness comes from the deck being shuffled and dealt, and due to the nature of the game not all initial board states are solvable, even with perfect gameplay.

The runtime of contemporary algorithms to find if a game of klondike is solvable is in the class known as **NP**. In fact, it is _**NP**-complete_, which means it is at least as hard as any problem in **NP**. [further topics: completeness and reduction] It’s the case for **NP**-complete puzzles that determining whether an instance is solvable is the same as going through the motions and solving it! More on this later.

Interestingly, humans are very, very bad at this game when compared to computers.  Modern estimates place between 70-80% of initial configurations as being solvable. Human abilities in this game are far lower. There exists a variant of pyramid solitaire known as “Thoughtful Solitaire”. In this variation, the player is able to see all cards which would normally be hidden. In trials with experts, only approximately 36.6% of games were solved, out of a sample size of 2,000. Humans will fail to solve a solvable game about half of the time, this is when they are given access to all cards which would normally be hidden.

A human, even knowing all the cards, cannot plan far enough ahead to properly win the game, so this leads to the greatly decreased rate of successful solutions compared to the rate calculated by contemporary algorithms, which can keep track of all possible “routes” as easily as it can multiply two absurdly large numbers.

[NEED TO ADD CITATIONS]

But why is Klondike **NP**-complete, and what is the class **NP**?
 
Let’s take another look at the class **P**. Remember the problem PRIME? Well, one way of drawing the instances is like this:

[IMG HERE]

Where the length of the lines might indicate the length of the computation to figure out whether the number is prime. (One way is to try to divide by every number less than it!)
 
Let’s name the problem of whether or not an initial condition of Klondike is solvable KLONDIKE-SOLVE. That initial condition will be our _problem instance_. Then, there’s lots of ways to generalize Klondike to have an infinite number of instances — let’s say we keep increasing the number of suits past four, or the number of ranks past 13. (2 through 10, Jack, Queen, King, Ace.) To check whether a game is solvable, we can’t just do something simple like divide by every instance less than it — we have to play through each game! The computational path might look like this. (This is an exercise for you, dear reader: _imagine_ the instances of the solitaire games that are being mapped to each natural number, as the author doesn’t feel like drawing them! What might it look like when the number of cards changes? Make your own solitaire generalization.)

[IMG HERE]

KLONDIKE-SOLVE asks, “does at least one of the ways of playing the game, starting from this instance, end in a solved game?” For instance #1437, this is true — for #1438, there is _no way_ to play the game or make choices such that you win. (Them’s the breaks!)

Then, we can look at the formal definition of **NP**:

{% raw %}
$$Latex Definition Here$$
{% endraw %}
 
This should provide some intuition why _almost all puzzles are **NP**-complete_ — **NP** are things that are easy (polynomial time) to check the answer to, but hard (exponential time, as you have to check every path) to _find_ the answer to,  and that’s pretty much what a puzzle _is_, right? 


  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
  {% raw %}
$$a^2$$
{% endraw %}
  
[^1]: [Cite: Nature of comp^2.]


[intro](#introduction)
