---
title: Extension Varieties of Tensors
tags:
  - WP1
  - geometry
  - tensor
---
**Authors:** Enrica Barrilli, Oriol Reig 

Let $T\in S_d$ be a symmetric tensor of order $d$ in $n$ variables that we want to decompose, and let $r$ be its rank. An *extension variety* parametrises the lifts of the tensor to a larger space, while keeping the rank unchanged. The lift can increase the order, by considering the space of tensors of order $d'$ with $d'\gt d$ (a **degree extension**), or the number of variables, by considering the space of tensors in $n'$ variables with $n'\gt n$ (a **dimension extension**). The motivation is that a decomposition which is hard to find for $T$ may become accessible from a suitable lift.

Let $K$ be an algebraically closed field of characteristic $0$. Let $S_d$ be the space of homogeneous polynomials of degree $d$ in $x_0,\dots,x_n$, identified with the symmetric tensors of order $d$. Let $R$ be the polynomial ring in $x_1,\dots,x_n$ over $K$, and $R_d$ the polynomials of degree at most $d$. We look for

$$
T = \sum_{i=1}^r \omega_i\, \ell_i^d, \qquad \omega_i\in K\setminus\{0\},\quad \ell_i\in S_1,
$$

with $r$ minimal. After a generic change of coordinates and scaling we may assume that the coefficient of $x_0$ in each $\ell_i$ is $1$, so that

$$
\ell_i=(\mathbf{x},\xi_i)=x_0+x_1\xi_{i,1}+\dots+x_n\xi_{i,n}, \qquad \xi_i\in K^n.
$$

Thanks to apolarity, $T$ corresponds to a linear form $\Lambda_T$ on $R_d$ defined by

$$
\Lambda_T(\mathbf{x}^\alpha)=a_\alpha\binom{d}{\alpha}^{-1},
$$

where $a_\alpha$ is the coefficient of $\mathbf{x}^\alpha$ in $T$. Finding a decomposition of $T$ is then equivalent to finding a decomposition of the dual element

$$
\Lambda_T=\sum_{i=1}^r \omega_i\, \mathrm{ev}_{\xi_i}.
$$

Let $R'$ be the polynomial ring in $x_1,\dots,x_{n'}$ with $n'\ge n$, so that $R\subseteq R'$, and let $d'\ge d$. Denote by $\rho$ the restriction map

$$
\rho : (R'_{d'})^{\ast} \longrightarrow (R_d)^{\ast}.
$$

An *extension* of $\Lambda_T$ is an element $\tilde\Lambda\in (R'_{d'})^{\ast}$ such that $\rho(\tilde\Lambda)=\Lambda_T$ and its Hankel operator has the same rank $r$. A degree extension corresponds to $n'=n$ and $d'\gt d$, and a dimension extension to $d'=d$ and $n'\gt n$.

## Hankel operators and extensions

To any linear form $\Lambda$ on $R$ we associate the Hankel operator

$$
H_\Lambda : R \to R^{\ast}, \qquad p \mapsto p\star\Lambda, \qquad (p\star\Lambda)(q)=\Lambda(pq).
$$

Its kernel $I_\Lambda$ is an ideal, the quotient algebra

$$
A_\Lambda = R / I_\Lambda
$$

is Gorenstein, and

$$
\dim_K A_\Lambda = \mathrm{rank}\, H_\Lambda .
$$

We know the first terms of $\Lambda$, namely the moments

$$
h_\alpha=\Lambda_T(\mathbf{x}^\alpha), \qquad |\alpha|\le d,
$$

and we look for the remaining ones.

Fix a set $B$ of $r$ monomials, called *connected to 1*: each $m\in B$ is either $1$ or $m=x_j m'$ with $m'\in B$. Put

$$
B^+=B\cup x_1B\cup\dots\cup x_nB .
$$

We consider the formal Hankel matrix

$$
H^B_\Lambda(\mathbf{h})=\big(h_{\alpha+\beta}\big)_{\alpha,\beta\in B},
$$

where $h_\gamma$ is the given value if $|\gamma|\le d$ and a new unknown otherwise. When $\det H^B_\Lambda(\mathbf{h})\neq 0$, the formal multiplication matrices are

$$
M_i(\mathbf{h})=\big(H^B_\Lambda(\mathbf{h})\big)^{-1} H^B_{x_i\star\Lambda}(\mathbf{h}), \qquad 1\le i\le n.
$$

The constraints on the unknown moments come from commutation [BCMT, Thm. 4.2]. There exists an extension $\tilde\Lambda$ with

$$
\mathrm{rank}\, H_{\tilde\Lambda}=r \quad\text{and}\quad B \text{ a basis of } A_{\tilde\Lambda}
$$

if and only if $\det H^B_\Lambda(\mathbf{h})\neq 0$ and

$$
M_i(\mathbf{h})\,M_j(\mathbf{h})-M_j(\mathbf{h})\,M_i(\mathbf{h})=0, \qquad 1\le i\lt j\le n.
$$

In this case $\tilde\Lambda$ is unique. This is a polynomial system of degree at most $2$ in the unknown moments. An equivalent description asks that all the $(r+1)\times(r+1)$ minors of the matrix

$$
H^{B^+}_\Lambda(\mathbf{h})
$$

vanish.

Since

$$
H_{x_i\star\Lambda}=M_{x_i}^{t}\circ H_\Lambda ,
$$

the points of $\tilde\Lambda$ are given by the common eigenvectors of the multiplication operators by $x_1,\dots,x_n$, whose eigenvalues are the coordinates $\xi_{j,i}$ of the points. If the joint eigenvalues are $r$ distinct points, then the kernel of $H_{\tilde\Lambda}$ is a radical ideal, and the weights $\omega_j$ are obtained from the linear system

$$
\Lambda_T=\sum_{j=1}^r \omega_j\,\mathrm{ev}_{\xi_j} \quad\text{on } R_d .
$$

Otherwise, it gives a *generalized additive decomposition* of length $r$ [BMT].

A **dimension extension** lifts $T\in S_d$ to a tensor in $n'\gt n$ variables, by the same principle. We look for $\tilde\Lambda$ on $R'$ with

$$
\rho(\tilde\Lambda)=\Lambda_T \quad\text{and}\quad \mathrm{rank}\, H_{\tilde\Lambda}=r,
$$

and the extension variety is the set of all such $\tilde\Lambda$.

## References

**[BCMT]** J. Brachat, P. Comon, B. Mourrain, E. Tsigaridas, *Symmetric tensor decomposition*, arXiv:0901.3706, 2009.
