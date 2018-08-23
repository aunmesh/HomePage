+++
title = "Monty Hall Problem- A Bayesian Reasoning"
date = 2018-08-23T04:52:10+05:30
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ['Asim Unmesh']

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ['Probability']
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++

Monty Hall Problem is famous problem in probability.  It is not only famous, but also important. This problem tests how good we understand probability. One of its appearence in popular culture is in this [scene](https://www.youtube.com/watch?v=Zr_xWfThjJ0) of "21" movie. Please ignore, the explanation given there. But I bet you can't ignore the amazing Kevin Spacey. 

<br>So, what is the problem?
Problem statement(taken from [wiki](https://en.wikipedia.org/wiki/Monty_Hall_problem)):
<br><br>
**_Suppose you're on a game show, and you're given the choice of three doors: Behind one door is a car; behind the others, goats. You pick a door, say No. 1, and the host, who goes by the name Monty, knows what's behind the doors. He opens another door, say No. 3, which has a goat. He then says to you, "Do you want to pick door No. 2?" Is it to your advantage to switch your choice?_**
<br><br>

I first became acquainted with this problem during an internship interview. I had just started my sophomore year in college. This was the first problem interviewer asked me. I tried to think, but couldn't understand why should we even bother to revise. Finally, I decided that it was a trick question, and said that no we shouldn't. I made up a faulty reasoning to support my claim. I wasn't given an offer, and I place the blame on this wretched problem.(Hence, the blog post :P)

### "Why? Why should we even bother to switch?"<br>
It is important to address this "why" before proceeding any further. We need to bother simply because there is a change in information. Extra information has been made available by Monty. That information is the presence of a goat behind the third door. This information was not there when we picked door 1. At the start, there was the possibility, that the car could be behind the 3rd door. Now we know for sure that it is not the case. Hence, we need to think.


### Enter Probability
Probability theorem is an amazing part of Mathematics. One of the reasons it is so amazing is because it has enabled a rational procedure for making guesses. I will say that again - **_"Rational Guess Work"_**. And thus, if we are to be smart here, and make rational choices, we need to follow Probability Theory.


### The Answer
Lets not stand on ceremony here and reveal the answer. The answer is - **_Yes, it is in our interest to switch_**. In fact, the probability of us winning if we switch is 2/3, while if we don't is just 1/3.
<br>Counter-intuitive? Yes? No? For me it was. It was very counter-intuitive that we should switch.

### A faulty argument that we should not switch
[Note: We represent Car by **C** and Goat by **G**]<br>
A faulty argument using probability theory proceeds as follow:
<br>Upon revelation, by Monty, there is now a 50-50 chance of our door having the car. This is because our door can now have either car or goat. And since only goat is left, the possibilities are: <br> **C G**, or **G C**. Hence there is 1/2 probability for each configuration, and so making a switch does not help.

##### Where's the fault?

The fault is in assuming that both these configurations are equi-probable. That is, the possibility that one can occur is same as the other. However, that is not the case. It will become clear later, as to why that is not the case. But, the major reason this mistake is committed is because history is ignored. The past information is compltely ignored and only the current possibilities are consulted.

Possible configurations according to the past information:<br>
**C G G** (config 1) , **G C G**(config 2) , **G G C**(config 3)
<br> All of these are equiprobable hence each of the configurations probability is 1/3.

### A correct reasoning
Now, upon revelation, we reason as follows:<br>

If the starting configuration was *config 1*, then Monty could have opened either door 2 or door 3. Thus the likelihood of Monty opening door 3(assuming he is constrained to open the doors which weren't picked), is 1/2.
If the starting configuration was *config 2*, Monty would have been forced to open door 3, as he could not open door 2(as door 2 has car behind it). So, the likelihood of opening door 3 in this case is 1.
<br>Hence we see that present events(Monty revealing to us door 3 and it having a goat) would have been twice as probable to occur if *config 2* was originally the case than if *config 1* was the case. And since the present event did occur, by a simple application of Bayes Rule , we can see that we are twice as likely to win if we switch, than if we don't.
<br><br>
While this reasoning is correct, it is also convoluted. It is not simple and lucid. Beofre presenting a simpler reasoning, I will cite from this [blog](https://betterexplained.com/articles/understanding-the-monty-hall-problem/), another way at why switching is beneficial.

### Why switching is better [courtsey of [betterexplained](https://betterexplained.com/articles/understanding-the-monty-hall-problem/)]
Let’s see why removing doors makes switching attractive. Instead of the regular game, imagine this variant:<br>
1. There are 100 doors to pick from in the beginning<br>
2. You pick one door<br>
* Monty looks at the 99 others, finds the goats, and opens all but 1<br>
Do you stick with your original door (1/100), or the other door, which was filtered from 99?

It’s a bit clearer: Monty is taking a set of 99 choices and improving them by removing 98 goats. When he’s done, he has the top door out of 99 for you to pick.

Your decision: Do you want a random door out of 100 (initial guess) or the best door out of 99? Said another way, do you want 1 random chance or the best of 99 random chances?

**We’re starting to see why Monty’s actions help us. He’s letting us choose between a generic, random choice and a curated, filtered choice. Filtered is better.**


### A Bayesian Reasoning

One realises, if they look at the problem carefully, is that the probability of door 1 having a car hasn't changed. Before revelation proability that door 1 has Car was 1/3. Post revelation the probability still remains 1/3.
<br>( This is because pre revelation, door 1 could either have a car, or 1st goat or 2nd goat. Hence 1/3 probability .Post revelation we have seen that configuration **C G** has 1/3 probability and configuration **G C** has 2/3 probability. So, post revelation, probability of door 1 having a car is same as the probability of **C G** configuration, or 1/3). 

This is remarkable. 
Let's see why this happens.
<br>When I chose door 1, I had placed my belief on *config 1*. So, when Monty opened door 3 and showed me a goat, should I be surprised? If I should be surprised, by how much should I be surprised? Since I chose *config 1*, I hoped the Car to be in the first door and goats behind the other 2 doors. Thus, if I assume *config 1* to be the case, I shouldn't be surprised at all that the goat is behind door 3. However, I should be surprised. This is not because of the goats or cars, but because of what Monty did. Monty revealed door 3, rather than door 2. Why? How probable is this. It's probability is 1/2. Monty revealing door 3 should surprise us even if we assume *config 1* to be true.
<br>Let's revisit Baye's rule:<br>

P(B|A) = A(A|B)P(B)/P(A)
<br>or in our case <br>

P( Car behind door 1 | what happened) = P(what happened | Car behind door 1) * P(Car behind door 1 | knowledge before game) / P(what happened | knowledge before game)

We have ascertained that P(all that happened | Car behind door 1) = 1/2.
<br>Now what is P( all that happened)? We have to find the probability of "What happened" given our prior knowledge, that is at the beginning of the game. Or more clearly, what is the probability that I would have chosen door 1, and then Monty would have revealed door 3 to be having a goat?
<br> Let's find out this probability using 3 disjoint events. That is 3 disjoint configurations. "What happened", could not have happened if *config 3* was the case. "What happened" could have happened with 1 probability if *config 2* was the case. However, *config 2* has 1/3 probability. What happened could have happened with 1/2 probability if *config 1* were the case, however, *config 1* itself has 1/3 probability.

Hence net probability of "What happened" given our prior beliefs is <br>
1/2*1/3 + 1/3 = 1/2.

So, we see that  P(what happened | Car behind door 1) = P(what happened | knowledge before game).
<br> They cancel out and we are left with:<br>
P( Car behind door 1 | what happened) = P(Car behind door 1 | knowledge before game).
<br>So, now we know why the probability stays the same.
