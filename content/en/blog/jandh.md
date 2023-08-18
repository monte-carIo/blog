---
author: "Monte Carlo"
title: "Jacobian and Hessian Matrices"
date: "2023-08-18"
tags: ["Numerical Computation"]
thumbnail: /prob.png
draft: true
math: true
---
## Jacobian and Hessian Matrices

The matrix containing all partial derivatives is known as a Jacobian matrix.

If we have a function $f : \mathbb{R^m \rightarrow R^n}$, then the Jacobian matrix $J \in \mathbb{R^{m \times n}}$ is defined as:

$$
J_{i,j} = \frac{\partial f(x)_i}{\partial x_j}
$$

When our function has multiple input dimensions, there are many second derivatives. These derivatives can be collected together into a matrix called the Hessian matrix. The Hessian matrix $H(f)(x)$ is defined such that:

$$
H(f)(x)_{i,j} = \frac{\partial^2f(x)}{\partial x_i \partial x_j}
$$

Based on the Hessian matrix, we can make a second-order Taylor series approximation of $f(x)$ around $x^{(0)}$:

$$
f(x^{(0)} - \alpha g) \approx f(x^{(0)}) -\alpha g^\top g + \frac{1}{2}\alpha g^\top Hg
$$

where g is the gradient and $H$ is the Hessian at $x^{(0)}$ and $\alpha$  is the learning rate. 

Solving for the optimal step size that decreases the Taylor series approximation of the function the most yields give us:

$$
\alpha ^* = \frac{g^\top g}{g^\top Hg}
$$

In the worst case, when g aligns with the eigenvector of H corresponding to the maximal eigenvalue, then this optimal step size is given by $\frac{1}{\lambda_{\max}}$.