---
author: "Monte Carlo"
title: "The Moore-Penrose Pseudoinverse"
date: "2023-08-17"
tags: ["Linear Algebra"]
thumbnail: /pseudoinverse.png
draft: false
math: true
---

## Definition

As we learned in linear algebra, we can not inverse a matrix if it is not square. For example, if we want to solve the equation:

$$
\boldsymbol{Ax=y}
$$

If the matrix \\(\boldsymbol{A}\\) is invertible then the solution is \\(\boldsymbol{x = A^{-1}y}\\). What if \\(\boldsymbol{A}\\) is not invertible, we can define the pseudoinverse of A as:

$$
\boldsymbol{A^+ = \lim_{\delta\to 0}(A^{\top}A + \delta^2I)^{-1}A^{\top}}
$$

where \\(\boldsymbol{\delta}\\) is added to prevent \\(\boldsymbol{A^{\top}A}\\) reach zero.

In practice with [SVD](https://machinelearningcoban.com/2017/06/07/svd/), \\(\boldsymbol{A = UDV^{\top}}\\), assume matrix \\(\boldsymbol{A}\\) is a non-zero matrix and matrix \\(\boldsymbol{D}\\) is invertible, we can rewrite the above formula as:

$$
A^+ = (A^{\top}A)^{-1}A^{\top}\\\ 
=(VDU^{\top}UDV^{\top})^{-1}VDU^{\top}\\\
=VD^{-2}V^{-1}VDU^{\top} \\\
 = VD^{-1}U^{\top}
$$

For general if matrix \\(\boldsymbol{D}\\) is  not invertible, then it can be written as:

$$
\boldsymbol{A^+ = VD^+U^\top}
$$

where \\(\boldsymbol{U}\\), \\(\boldsymbol{D}\\) and \\(\boldsymbol{V}\\) are the singular value decomposition of \\(\boldsymbol{A}\\) and \\(\boldsymbol{D^+}\\) can be obtained by taking the reciprocal of \\(\boldsymbol{D}\\) non-zero elements, then taking the transpose of the resulting matrix.

## Practice example
For example, give a matrix \\(\boldsymbol{A = \begin{bmatrix}
1 & 2 \\\
3 & 4 \\\
5 & 6 
\end{bmatrix}}\\)have the size 3x2. Then we can calculate the \\(\boldsymbol{A^+}\\) as:

$$
\boldsymbol{A^+ = (A^{\top}A)^{-1}A^{\top}}\\\ 
= \boldsymbol{(\begin{bmatrix}
1 & 2 \\\
3 & 4 \\\
5 & 6 
\end{bmatrix}^{\top}\begin{bmatrix}
1 & 2 \\\
3 & 4 \\\
5 & 6 
\end{bmatrix})^{-1}\begin{bmatrix}
1 & 2 \\\
3 & 4 \\\
5 & 6 
\end{bmatrix}^{\top}}\\\
= \begin{bmatrix}
-4/3 & -1/3 & 2/3\\\
13/12 & 1/3 & -5/12 \\\
\end{bmatrix}
$$

Or by the second way, with calculated \\(\boldsymbol{U}, \boldsymbol{D}\\) (or usually denoted as \\(\boldsymbol{\Sigma}\\)) and \\(\boldsymbol{V}\\) as:

![image-removebg.png](/image-removebg.png)

This will give the same result as the above method.