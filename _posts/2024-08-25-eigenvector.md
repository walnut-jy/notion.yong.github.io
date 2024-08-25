---
layout: post
title: Eigenvalue and EigenVector
tags: eigenvalue, eigenvector, decomposition, basic
math: true
date: 2024-08-24 15:32 +0800
---

# Definition of Eigenvalue & Eigenvector

$$
Av = \lambda v 
$$
For square matrix $A$, we can see this matrix as linear transformation for vector $v$, where $v$ does not equal to 0. We call this 'eigenvector', with constant multiplication value called 'eigenvalue'.

$$
\left(\begin{array}{ccc} 
a_{11} & a_{12} & a_{13}\\
a_{21} & a_{22} & a_{23}\\
a_{31} & a_{32} & a_{33}\\
\end{array}\right)
\left(\begin{array}{c} 
v_1\\ 
v_2\\
v_3
\end{array}\right)
=
\lambda
\left(\begin{array}{c}
v_1\\
v_2\\
v_3
\end{array}\right)
$$ 

That is, \\\(\lambda\\\) implies eigenvalue of matrix $A$, and $v$ implies eigenvector of matrix $A$ in terms of \\\(\lambda\\\). Direction of vector $v$ did not change, only amount of magnitude did as much as \\\(\lambda\\\) after linear transformation $A$.

As $(A - \lambda I)v = 0$, inverse matrix of $A - \lambda I$ cannot exists. (if exists, $v$ becomes 0 that violates our assumption.) Therefore, 
$$
det(A - \lambda I) = 0
$$


Apply it on real numberset
$$
A 
= 
\left(\begin{array}{cc}
1 & 2 \\
2 & 4
\end{array}\right)
$$

since, 
$$
det(A - \lambda I) = 0 \\
\\
det\left(\begin{array}{cc}
1-\lambda & 2 \\
2 & 4-\lambda
\end{array}\right)
=0
$$

$$
(1-\lambda)*(4-\lambda) - 4 = 0 \\
\lambda^2 - 5 \lambda = 0 \\
$$

$\therefore \ \lambda = 0, 5$

When $\lambda = 0$,
$$
\left(\begin{array}{cc}
1 & 2 \\
2 & 4 
\end{array}\right)
\left(\begin{array}{cc}
v_1 \\
v_2
\end{array}\right) = 0
$$
$v_1 + 2 v_2 = 0$ and $2 v_1 + 4 v_2 = 0$
Therefore, $v_1 = - v_2$ which shows matrix A dimension is lower than 2.

When $\lambda = 5$,
$$
\left(\begin{array}{cc}
1 & 2 \\
2 & 4
\end{array}\right)
\left(\begin{array}{cc}
v_1 \\
v_2
\end{array}\right) = 
5
\left(\begin{array}{cc}
v_1 \\
v_2
\end{array}\right)
$$
$v_1 + 2 v_2 = 5 v_1$ and $2 v_1 + 4 v_2 = 5 v_2$
Therefore, $v_2 = 2 v_1$ for eigenvalue $\lambda = 5$.

We can do EigenDecomposition using above ideas.


reference : https://darkpgmr.tistory.com/105


## Examples

Example 5.8 from Axler, S. (2015). Linear algebra done right (3rd ed.). New York, NY: Springer


Suppose $T \in \mathcal{L}\left(\mathbf{F}^2\right)$ is defined by

$$
T(w, z)=(-z, w) .
$$

(a) Find the eigenvalues and eigenvectors of $T$ if $\mathbf{F}=\mathbf{R}$.

(b) Find the eigenvalues and eigenvectors of $T$ if $\mathbf{F}=\mathbf{C}$.


solution (a) \
If $\mathbf{F}=\mathbf{R}$, then $T$ is a counterclockwise rotation by $90^{\circ}$ about the origin in $\mathbf{R}^2$. $T(w, z)=(-z, w)$ \
An operator $T$ has an eigenvalue if and only if there exists a nonzero vector in its domain that gets sent by the operator to a scalar multiple of itself. However, $90^{\circ}$ counterclockwise rotation of a nonzero vector in $\mathbf{R}^2$ obviously never equals a scalar multiple of itself.  
Conclusion: if $\mathbf{F}=\mathbf{R}$, then $T$ has no eigenvalues (and thus has no eigenvectors).



solution (b) \
To find eigenvalues of $T$, we must find the scalars $\lambda$ such that

$$
T(w, z)=\lambda(w, z) = (-z, w)
$$

has some solution other than $w=z=0$. The equation above is equivalent to the simultaneous equations.

$$
-z=\lambda w, \quad w=\lambda z .
$$


Substituting the value for $w$ given by the second equation into the first equation gives

$$
-z=\lambda^2 z
$$


Now $z$ cannot equal 0, so the equation above leads to the equation

$$
-1=\lambda^2 \\
$$

$\therefore \lambda = \plusmn i$

It is easy to verify that $i$ and $-i$ are eigenvalues of $T$. Indeed, the eigenvectors corresponding to the eigenvalue $i$ are the vectors of the form $(w,-w i)$, with $w \in \mathbf{C}$ and $w \neq 0$, and the eigenvectors corresponding to the eigenvalue $-i$ are the vectors of the form $(w, w i)$, with $w \in \mathbf{C}$ and $w \neq 0$. (Multiplication of $i^3$ and $i$ for the equation $\lambda(w, z) = (-z, w)$)