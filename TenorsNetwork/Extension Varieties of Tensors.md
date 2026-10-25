---
title: Extension Varieties of Tensors
tags:
  - WP1
  - geometry
  - tensor
---
**Authors:** Enrica Barrilli, Oriol Reig 

# Extension Varieties of Tensors

Let $T\in S_d$ be a symmetric tensor of order $d$ in $n$ variables that we want to decompose, and let $r$ be its rank. An *extension variety* parametrises the lifts of the tensor to a larger space, while keeping the rank unchanged. The lift can increase the order, by considering the space of tensors of order $d'>d$ (a **degree extension**), or the number of variables, by considering the space of tensors in $n'>n$ variables (a **dimension extension**). The motivation is that a decomposition which is hard to find for $T$, may become accessible from a suitable lift.

Let $K$ be an algebraically closed field of characteristic $0$, $S_d$ the space of homogeneous polynomials of degree $d$ in $x_0,\dots,x_n$, identified with the symmetric tensors of order $d$, and $R=K[x_1,\dots,x_n]$ with $R_d$ the polynomials of degree at most $d$. We look for

$$
T = \sum_{i=1}^r\omega_i\,\ell_i^d,\qquad \omega_i\in K\setminus\{0\},\quad \ell_i\in S_1,
$$

with $r$ minimal. After a generic change of coordinates and scaling we may assume that $\xi_{i,0} = 1$, so that

$$
\ell_i=(\boldsymbol{x},\xi_i)=x_0+x_1\xi_{i,1}+\dots+x_n\xi_{i,n},\qquad \xi_i\in K^n .
$$

Thanks to apolarity, $T$ corresponds to a functional $\Lambda_T\in R_d^{\ast}$ with $\Lambda_T(\boldsymbol{x}^\alpha)=a_\alpha\binom{d}{\alpha}^{-1}$, where $a_\alpha$ is the coefficient of $\boldsymbol{x}^\alpha$ in $T$, and finding a decomposition of $T$ is equivalent to finding a decomposition of the dual element

$$
\Lambda_T=\sum_{i=1}^r\omega_i\,\mathrm{ev}_{\xi_i}.
$$

Let

$$
\rho : (R'_{d'})^{\ast} \to (R_d)^{\ast},
$$

where

$$
R'=K[x_1,\dots,x_{n'}]\supseteq R, \qquad n'\geq n, \qquad d'\geq d.
$$

An *extension* of $\Lambda_T$ corresponds to an element $\tilde\Lambda\in R'^{\,\ast}_{d'}$ such that $\rho(\tilde\Lambda)=\Lambda_T$ and its Hankel operator has the same rank $r$. A degree extension corresponds to $n'=n$, $d'>d$, and a dimension extension to $d'=d$, $n'>n$.

## Hankel operators and extensions

To any $\Lambda\in R^{\ast}$ we associate the Hankel operator $H_\Lambda:R\to R^{\ast}$, $p\mapsto p\star\Lambda$, where $(p\star\Lambda)(q)=\Lambda(pq)$. Its kernel $I_\Lambda$ is an ideal, $A_\Lambda=R/I_\Lambda$ is Gorenstein, and $\dim_{K}A_\Lambda=\mathrm{rank}\,H_\Lambda$. We know the first terms of $\Lambda$, namely the moments $h_\alpha=\Lambda_T(\boldsymbol{x}^\alpha)$ for $|\alpha|\le d$, and we look for the remaining ones.

Fix a set $B=\{\boldsymbol{x}^{\beta_1},\dots,\boldsymbol{x}^{\beta_r}\}$ of monomials *connected to* $1$, i.e. each $m\in B$ is $1$ or $m=x_jm'$ with $m'\in B$. Put $B^+=B\cup x_1B\cup\dots\cup x_nB$. 

We consider the formal Hankel matrix

$$
H^B_\Lambda(\boldsymbol{h})=\big(h_{\alpha+\beta}\big)_{\alpha,\beta\in B},
$$

where

$$
h_\gamma \ \text{ is the given value if } |\gamma|\le d \text{ and a new unknown otherwise,}
$$

and a new unknown otherwise, and, when $\det H^B_\Lambda(\boldsymbol{h})\neq0$, the formal multiplication matrices

$$
M_i(\boldsymbol{h})=\big(H^B_\Lambda(\boldsymbol{h})\big)^{-1}H^B_{x_i\star\Lambda}(\boldsymbol{h}),\qquad 1\le i\le n.
$$

The constraints on the unknown moments come from commutation [BCMT, Thm. 4.2]: there exists an extension $\tilde\Lambda\in R^{\ast}$ with $\mathrm{rank}\,H_{\tilde\Lambda}=r$ and $B$ a basis of $A_{\tilde\Lambda}$ if and only if $\det H^B_\Lambda(\boldsymbol{h})\ne0$ and

$$
M_i(\boldsymbol{h})\,M_j(\boldsymbol{h})-M_j(\boldsymbol{h})\,M_i(\boldsymbol{h})=0,\qquad 1\le i\lt j\le n,
$$

and then $\tilde\Lambda$ is unique. This is a polynomial system of degree at most $2$ in the unknown moments. An equivalent description asks that all the $(r+1)\times(r+1)$ minors of $H^{B^+}_\Lambda(\boldsymbol{h})$ vanish.

Since $H_{x_i\star\Lambda}=M_{x_i}^t\circ H_\Lambda$, the points of $\tilde\Lambda$ are given by the common eigenvectors of the multiplication-by-$x_i$ operators $M_{x_i}$, whose eigenvalues are the coordinates $\xi_{j,i}$ of the points. If the joint eigenvalues are $r$ distinct points, then $I_{\tilde\Lambda}$ is radical, and the weights $\omega_j$ are obtained from the linear system $\Lambda_T=\sum_j\omega_j\,\mathrm{ev}_{\xi_j}$ on $R_d$. Otherwise, it gives a *generalized additive decomposition* of length $r$ [BMT].

A **dimension extension** lifts $T\in S_d$ to a tensor in $n'>n$ variables, by the same principle: we look for $\tilde\Lambda$ on $R'=K[x_1,\dots,x_{n'}]$ with $\rho(\tilde\Lambda)=\Lambda_T$ and $\mathrm{rank}\,H_{\tilde\Lambda}=r$, and the extension variety is the set of all such $\tilde\Lambda$.

## References

**[BCMT]** J. Brachat, P. Comon, B. Mourrain, E. Tsigaridas, *Symmetric tensor decomposition*, arXiv:0901.3706, 2009.

**[BMT]** E. Barrilli, B. Mourrain, D. Taufer, *Generalized additive decompositions of symmetric tensors*, arXiv:2510.25681, 2025.
