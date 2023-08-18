---
author: "Monte Carlo"
title: "Concepts of Covariance, the Dirac Distribution and Empirical Distribution"
date: "2023-08-18"
tags: ["Probability and Information Theory"]
thumbnail: /prob.png
draft: false
math: true
---
These things is what probability class didn't teach me.
## Covariance
Covariance is a statistical concept that measures the degree to which two random variables change together. In other words, it quantifies the relationship between two variables and indicates whether they tend to increase or decrease together. It is an important concept in understanding the joint behavior of variables and is widely used in statistics, probability theory, and data analysis:

$$
Cov(f(x), g(y)) = E[(f(x) - E[f(x)])(g(y) - E[g(y)])]
$$

High absolute values of the covariance mean that the values change very much and are both far from their respective means at the same time. 

If the sign of the covariance is positive, then both variables tend to take on relatively high values simultaneously. 

If the sign of the covariance is negative, then one variable tends to take on a relatively high value at the times that the other takes on a relatively low value and vice versa.

## The Dirac Distribution and Empirical Distribution

In practice, sometimes we want to determine the mass in probability distribution clusters around a single point. We can redefine a pdf to a function that is zero-valued everywhere except 0, yet integrates to 1, or we can say a Dirac delta function \\(\delta(x)\\):

$$
p(x) = \delta(x-\mu)
$$

This Dirac delta function is a generalized function which is a kind of function that is defined in terms of its properties when integrated. Here is a schematic representation of the Dirac delta function by a line surmounted by an arrow.

![Dirac distribution](/dirac.png)

A common use of the Dirac delta distribution is as a component of an **empirical distribution** over continuous variables:

$$
\hat p(x) = \frac{1}{m}\sum_{i=1}^{m} \delta(x-x^{(i)})
$$

The intuition behind the above empirical probability distribution is that it's a discrete distribution, you assume that your variable can take only the values as observed in your sample, with probabilities equal to empirical probabilities. If your data is not discrete, then only the [empirical distribution function](https://en.wikipedia.org/wiki/Empirical_distribution_function) makes sense as an approximation of the true distribution. This is why histograms and kernel density estimators were developed so that we can approximate the continuous density function using empirical data.