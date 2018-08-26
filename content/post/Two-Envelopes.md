+++
title = "Two Envelopes"
date = 2018-08-26T07:00:23+05:30
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = []

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Probability"]
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

Two Envelopes Paradox is another one of those problems which test your probability and math basics. Some times being mathematically correct, means being methodical and writing each step properly in your logic. Leaving nothing but the axioms as assumptions.

So let's quickly get into the problem.

### The problem

[Wiki Link](https://en.wikipedia.org/wiki/Two_envelopes_problem)

**_"You are given two indistinguishable envelopes, each containing money, one contains twice as much as the other. You may pick one envelope and keep the money it contains. Having chosen an envelope at will, but before inspecting it, you are given the chance to switch envelopes. Should you switch?"_**

### A faulty argument

There's an argument that favours switching. THe problem is to find the fault in this argument. (Obviously its no use switching your choices).

The switching argument: Now suppose you reason as follows:<br>
1. I denote by A the amount in my selected envelope.<br>
2.The probability that A is the smaller amount is 1/2, and that it is the larger amount is also 1/2.<br>
3. The other envelope may contain either 2A or A/2.<br>
4. If A is the smaller amount, then the other envelope contains 2A.<br>
5. If A is the larger amount, then the other envelope contains A/2.<br>
6. Thus the other envelope contains 2A with probability 1/2 and A/2 with probability 1/2.<br>
7. So the expected value of the money in the other envelope is:
\begin{align}
\frac{1}{2} (2A) + \frac{1}{2} (\frac{A}{2}) = \frac{5A}{4}
\end{align}<br>
8. This is greater than A, so I gain on average by swapping.<br>
9. After the switch, I can denote that content by B and reason in exactly the same manner as above.<br>
10. I will conclude that the most rational thing to do is to swap back again.<br>
11. To be rational, I will thus end up swapping envelopes indefinitely.<br>
12. As it seems more rational to open just any envelope than to swap indefinitely, we have a contradiction.<br>


### Something's fishy.(Part 1)

Let S be the total sum in both envelopes.

When Envelope 1 has larger value:
\begin{align}
S = A + \frac{A}{2} = \frac{3A}{2}
\end{align}
<br>
When Envelope 1 has smaller value:
\begin{align}
S = A + 2A = 3A
\end{align}

But, the sum should be constant in both the cases. This is, from a first look, what goes wrong here. 

### What's A?
We saw in the last section that the sum of values in both envelopes were not coming out to be equal. This requires us to look at what is A.<br>
What exactly is A?<br>
Since A is being used to compare with the expected value of money in the second envelope, A is actually the expected value of money in Envelope 1.

Let *a* denote the value of the money in Envelope 1, then:

\begin{align}
E_p[a] = A
\end{align}
where p is the probability density function on random variable a.

Now, that we understand what's A. Let's see what went wrong.

### Something's fishy.(Part 2)
As, stated earlier, sometimes being mathematically correct, means writing down things well.

Let b denote value of money in 2nd envelope.
So,
\begin{align}
E_q[b] = B 
\end{align}
\begin{align}
B = P(a>b)E[a \mid a > b)  + P(a>b)E[a \mid a > b)
\end{align}
\begin{align}
B = \frac{1}{2}E[a \mid a > b] +  \frac{1}{2}E[a \mid a < b]
\end{align}

We observe that, 
\begin{align}
E[a \mid a > b] > A\  \,, \ E[a \mid a > b] < A
\end{align}

<br>
This is because average of $E[a \mid a > b]$ and $E[a \mid a < b]$ is A. And since intuitively, 
<br>
\begin{align}
E[a \mid a > b] >  E[a \mid a > b] 
\end{align}

(8) should hold.

Hence substituting both $E[a \mid a > b]$ and $E[a \mid a < b]$ as A is wrong in step 7 of the argument.

However, we were asserting that being mathematically correct means writing everything down. So, let's not leave (8) and (9) to intuition and see more concretely why they are true.

### Be rigourous, be right

Let $P(x,y)$ denote the joint probability of amount x being in envelope 1 and amount y being in envelope 2.

We assert that \begin{align}
P(x,y) = P(y,x)
\end{align}

It's easy to see this is true. If $x\neq2y$ or $2x\neq y$, then $P(x,y) = 0$.(such an arrangement is not possible as one of $x$ and $y$ must be double of other)

However, if this is not the case, then envelope $1$ and envelope $2$ are not subject of any bias. That is they are _indistinguishable_ and hence probability that amount $x$ is kept in envelope $1$ and $y$ is kept in envelope $2$ is same as $x$ is kept in $2$ and $y$ is kept in $1$.


