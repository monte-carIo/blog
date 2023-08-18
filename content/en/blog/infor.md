---
author: "Monte Carlo"
title: "Information Theory"
date: "2023-08-18"
tags: ["Probability and Information Theory"]
thumbnail: /inforwall.jpg
draft: false
math: true
---
### Intuition
The basic intuition behind information theory is that learning that an unlikely event has occurred is more informative than learning that a likely event has occurred. A message saying “the sun rose this morning” is so uninformative as to be unnecessary to send, but a message saying “there was a solar eclipse this morning” is very informative.

Independent events should have additive information. For example, the information gained from the event that a tossed coin has come up as heads twice is double than the event a tossed coin has come up as heads once. From this, we define the **self-information** of an event to be:

$$
I(x) = - logP(x)
$$

with the units of nats (one nat equal information gained by observing an event of probability \\(\frac{1}{e}\\)).

### Continuous variable
The same definition for it but some of the properties will be lost. For example, an event with unit density still has zero information, despite not being an event that is guaranteed to occur:

- Unit density means \\(p(x)=1\\), where \\(p(.)\\) is a probability density function and \\(x\\) is a continuous random variable.
- An event with unit density has zero information:
    
    $$
    I(x) = -\log p(x) \\\
     = -\log 1\\\
     = 0
    $$
    
- In fact, it is an event that can be zero probability of occurring if the probability of a continuous random variable is equal to any specific value (rather than a continuous range of real values).

We can quantify the amount of uncertainty in an entire probability distribution using the **Shannon entropy** (or **differential entropy** when x is continuous):

$$
H(x) = E_{X \sim P}[I(x)]
$$

![infor](/infor.png)

Distributions that are nearly deterministic (where the outcome is nearly certain) have low entropy, and distributions that are closer to uniform have high entropy.