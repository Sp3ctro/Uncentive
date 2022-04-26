---
layout: post
title: "Matrix Operations"
author: "Uncentive"
categories: post
tags: [Maths]
---

For an intro to matrices in general, see [this post](https://uncentive.org/matrices)

## Multiplication
Matrix multiplication is done by repetitive vector multiplication. Multiplication of two vectors is...

$$\begin{bmatrix}a_1 & a_2 & a_3 \end{bmatrix}\begin{bmatrix}a_1\\b_1\\c_1\end{bmatrix} = a_1b_1 + a_2b_2 + a_3b_3 + ... + a_nb_n = \sum^{n}_{i=1}a_ib_i$$

If we are denoting these matrices as **A** and **B** then we can say in this case that **AB** = **BA**. We can't multiply two column vectors as that won't work with the way that matrix multiplication works.

If the two matrices being multiplied do not have the same number of rows and columns, then your resulting matrix will be an $m \times p$ sized matrix. For example, if matrix **A** has m rows and n columns$(m \times n)$, and if matrix **B** has n rows and p columns $(n \times p)$, then the resulting matrix will be a $(m \times p)$ sized matrix.

If a matrix is multiplied by a scalar (an individual value) then all elements of the matrix are simply multiplied by that scalar value.

## Transpose
Transpose is the process of making the matrix rows into columns, and columns into rows. Often we have to do this so that we can perform matrix multiplication.
$$A' = A^T = \begin{bmatrix}a_1 & a_2 & a_3\end{bmatrix}^T = \begin{bmatrix}a_1\\a_2\\a_3\end{bmatrix}$$
And in relation to matrix multiplication as explained above...
$$a'b = b'a = \sum^{n}_{i=1}a_ib_i$$

## Addition
Matrix addition is done by adding the corresponding elements of each matrix. So if we are to add matrices **A** and **B** together, we'd simply do...$$ \begin{bmatrix}
a_1 \\
a_2 \\
a_3
\end{bmatrix}  +  \begin{bmatrix}
b_1 \\
b_2 \\
b_3
\end{bmatrix}  = \begin{bmatrix}
a_1 + b_1 \\
a_2 + b_2 \\
a_3 + b_3
\end{bmatrix}$$

Two matrices can only be added together if they are of the same $(m \times n)$ size. The resulting matrix will also be the same size.  The order in which the matrices are added is not relevant.

## Equality
If we say that **A** is equal to **B** we are simply saying that the first element in **A** is equal to the first element in **B**, and so on.

## Kronecker Product
An operation on two matrices resulting in a block matrix. If A = an _m x n_ matrix, and B is a _p x q_ matrix, then the Kronecker product $A \otimes B$ is an _pm x qn_ block matrix. For example...

$$\begin{bmatrix}
    1 & 2 \\
    3 & 4 \\
  \end{bmatrix} \otimes
  \begin{bmatrix}
    0 & 5 \\
    6 & 7 \\
  \end{bmatrix} =
  \begin{bmatrix}
    1 \begin{bmatrix}
      0 & 5 \\
      6 & 7 \\
    \end{bmatrix} &
    2 \begin{bmatrix}
      0 & 5 \\
      6 & 7 \\
    \end{bmatrix} \\

    3 \begin{bmatrix}
      0 & 5 \\
      6 & 7 \\
    \end{bmatrix} &
    4 \begin{bmatrix}
      0 & 5 \\
      6 & 7 \\
    \end{bmatrix} \\
  \end{bmatrix}$$

  $$\begin{bmatrix}
    1\times 0 & 1\times 5 & 2\times 0 & 2\times 5 \\
    1\times 6 & 1\times 7 & 2\times 6 & 2\times 7 \\
    3\times 0 & 3\times 5 & 4\times 0 & 4\times 5 \\
    3\times 6 & 3\times 7 & 4\times 6 & 4\times 7 \\
  \end{bmatrix} =

  \begin{bmatrix}
     0 &  5 &  0 & 10 \\
     6 &  7 & 12 & 14 \\
     0 & 15 &  0 & 20 \\
    18 & 21 & 24 & 28
  \end{bmatrix}$$

## Trace
The trace of a matrix is the sum of the diagonal elements. It is denoted as $tr(A)$.

## determinant
The **determinant** is a [scalar value](https://en.wikipedia.org/wiki/Scalar_(mathematics) "Scalar (mathematics)") that is a [function](https://en.wikipedia.org/wiki/Function_(mathematics)) of the entries of a [square matrix](https://en.wikipedia.org/wiki/Square_matrix "Square matrix"). In the case of a 2 × 2 matrix the determinant can be defined as: $$\begin{align}|A| = \begin{vmatrix} a & b\\c & d \end{vmatrix}=ad-bc.\end{align}$$

Similarly, for a 3 × 3 matrix ''A'', its determinant is:
$$\begin{align}
  |A| = \begin{vmatrix} a & b & c \\ d & e & f \\ g & h & i \end{vmatrix}
     &= a\,\begin{vmatrix} e & f \\ h & i \end{vmatrix} -
        b\,\begin{vmatrix} d & f \\ g & i \end{vmatrix} +
        c\,\begin{vmatrix} d & e \\ g & h \end{vmatrix} \\[3pt]
     &= aei + bfg + cdh - ceg - bdi - afh.
\end{align}$$

The determinant is nonzero if and only if the matrix is Invertible.
