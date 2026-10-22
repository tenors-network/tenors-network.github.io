---
title: Optimization
tags:
  - optimization
  - quantum
  - polynomial
  - WP1
  - geometry
  - course
---
**Authors:** Matteo Bechere, Sami Halase, Francesco Maria Mascarin

## Tensors and polynomial optimization 
Optimization means solving problems of the form
$$
 \inf_{x \in S} f(x)
$$
Optimization means solving problems of the form
$$
\inf_{x \in S} f(x).
$$
An important special class is **polynomial optimization (POP)**: the objective $f$ is a polynomial and the feasible set is a basic closed semialgebraic set
$$
S = \{ x \in \mathbb{R}^n : g_1(x) \ge 0, \dots, g_m(x) \ge 0 \},
$$
where $g_1, \dots, g_m$ are polynomials as well. This class is very expressive: it contains, for instance, combinatorial problems such as max-cut, and is therefore hard in general. Its algebraic structure, however, allows for powerful approximation schemes.

### Two dual points of view

**Sums of squares.** The minimum $f_{\min}$ is the largest $\lambda$ such that $f - \lambda$ is nonnegative on $S$. Nonnegativity is hard to check, so one asks instead for an algebraic certificate
$$
f - \lambda = \sigma_0 + \sum_{j=1}^{m} \sigma_j \, g_j ,
$$
where each $\sigma_j$ is a **sum of squares** of polynomials. Once the degrees are bounded, finding such a certificate is a semidefinite program.

**Moments.** Equivalently, $f_{\min}$ is the minimum of $\int f \, d\mu$ over all probability measures $\mu$ supported on $S$. A measure is replaced by its sequence of moments up to some degree, and the condition that it comes from a measure on $S$ is relaxed to the positive semidefiniteness of the associated *moment* and *localizing* matrices. This is again a semidefinite program.

Increasing the degree gives the **moment–SOS hierarchy** (or Lasserre hierarchy) of lower bounds on $f_{\min}$. Under a mild compactness assumption these bounds converge to $f_{\min}$ ([Lasserre, 2001](https://doi.org/10.1137/S1052623400366802)).

### Where tensors enter

The moments of degree $d$ of a measure $\mu$ form a symmetric tensor,
$$
M_d(\mu) = \int \tilde{x}^{\otimes d} \, d\mu(x), \qquad \tilde{x} = (1, x),
$$
so the moment side of the hierarchy is an optimization over symmetric tensors. When the problem has finitely many minimizers $\xi_1, \dots, \xi_r$, an optimal measure is $\mu = \sum_i \omega_i \delta_{\xi_i}$ and its moment tensor has the decomposition
$$
M_d(\mu) = \sum_{i=1}^{r} \omega_i \, \tilde{\xi}_i^{\otimes d}, \qquad \omega_i > 0 .
$$
Recovering the minimizers from the output of the relaxation is therefore a symmetric [[Algorithms for Tensor Decomposition|tensor decomposition]] problem, with the extra requirement that the weights be positive.

## Tensors with positive representation


## Optimization on Lissajous varieties

Lissajous varieties are affine algebraic varieties parametrized by sine and cosine functions. They generalize algebraic Lissajous planar curves to higher dimensions by applying a component-wise trigonometric map to a rational affine complex subspace. Concretely, for an integer matrix $A \in \mathbb{Z}^{d \times n}$ and a shift $b \in \mathbb{C}^n$,
$$
\mathcal{L}_{A,b} = \cos\big(\mathrm{Row}(A) - \tfrac{\pi}{2} b\big),
$$
with the cosine applied coordinate-wise. For instance, $A = (1 \ \ 1)$ and $b = (0, 1)$ give the circle $t \mapsto (\cos t, \sin t)$. The degree of $\mathcal{L}_{A,b}$ is, up to a combinatorial factor, the volume of a polytope built from the columns of $A$. A first example is Cayley's cubic surface, the algebraic boundary of the $3 \times 3$ elliptope.

### Equations from tensor product algebras

The defining equations of Lissajous varieties have a natural [[TenorsNetwork/What is a tensor?|tensor]] structure. Substituting $x_j = \tfrac{1}{2}(y_j + y_j^{-1})$ leads to the algebra
$$
\mathcal{A} = \bigotimes_{j=1}^{n} K[y_j^{\pm 1}] / \langle 2x_j - y_j - y_j^{-1} \rangle,
$$
a tensor product of $n$ two-dimensional algebras, one for each coordinate, so $\dim \mathcal{A} = 2^n$. Equations of $\mathcal{L}_{A,b}$ are obtained as rank conditions on multiplication maps acting on $\mathcal{A}$. These are $2^n \times 2^n$ matrices with polynomial entries in $x$, built from Kronecker products of $2 \times 2$ blocks. When $\mathcal{L}_{A,b}$ is a hypersurface, it is the zero set of the determinant of a single multiplication map, which is a power of its defining polynomial.

### Positive points and convex optimization

The positive points $\mathcal{L}^+_{A,b} = \cos\big((\mathrm{Row}(A) - \tfrac{\pi}{2} b) \cap (0, \pi)^n\big)$ can be computed by convex optimization: $x^*$ lies in $\mathcal{L}^+_{A,b} \cap \{A x = \omega\}$ if and only if it is the unique minimizer of
$$
\min_{x \in (-1,1)^n} \; -\frac{\pi}{2} b^\top x - \sum_{j=1}^{n} \Big( x_j \arccos(x_j) - \sqrt{1 - x_j^2} \Big) \quad \text{subject to} \quad A x = \omega .
$$
This applies to the **Kuramoto model** of coupled oscillators on a graph $G$. Its steady states are the points of a sine Lissajous variety on an affine slice $A x = \omega / K$, with $A$ the reduced incidence matrix of $G$. The degree of this variety bounds the number of isolated equilibria. Whenever a positive point exists on this slice, it is unique and corresponds to a linearly stable equilibrium, which is found by solving the convex program above. 

### Graph elliptopes

For a graph $G = ([n], E)$, the **graph elliptope** $\mathcal{E}(G) \subset \mathbb{R}^E$ is the set of partial correlation matrices supported on $E$ that admit a positive semidefinite completion. For the complete graph it is the elliptope, the feasible set of the Goemans–Williamson relaxation of max-cut.

For **cycle-completable** graphs, the algebraic boundary of $\mathcal{E}(G)$ is a union of determinantal hypersurfaces and Lissajous varieties. The latter come from the cycles of $G$ and are defined by the **cycle polynomial**, obtained by rationalizing $x_1 = \cos\big( \sum_{i=2}^{n} \arccos x_i \big)$. It can be computed recursively as a resultant of smaller cycle polynomials, and its degree answers a question of Sturmfels and Uhler. Moreover, $\mathcal{E}(G)$ is a spectrahedron exactly when its algebraic boundary avoids the interior, which happens precisely when $G$ is chordal.

### References

- F. M. Mascarin, S. Telen. [Lissajous varieties](https://doi.org/10.1515/advgeom-2026-0008). *Advances in Geometry* 26(2), 263–282, 2026.
- M. Laurent, F. M. Mascarin, S. Telen. [The algebraic boundary of graph elliptopes](https://arxiv.org/abs/2605.02484). Preprint, 2026.

## Courses
 - [Semidefinite approximations for polynomial optimization, with applications to quantum information](https://drive.google.com/file/d/1cgErrrstRVfacz2YQIryLiKNheHQ9LxZ/view?usp=sharing)|[Monique Laurent (CWI)](https://www.cwi.nl/en/people/monique-laurent/) 
	 - [Lecture Notes (POP and QI)](https://drive.google.com/file/d/1Ptn3PIWcVrgjV2U1mFWGzjqS4dyArrOk/view?usp=sharing) [Hand-out Part 1](https://drive.google.com/file/d/1ul0vLcb9jAvk0XEJF-N4xr3PByWdUPoz/view?usp=sharing)  [Hand-out Part 2](https://drive.google.com/file/d/18y9KWVAws2HXdWNYhAxlgMtvW8e_dvUj/view?usp=sharing)  
	 - [Recording 1/2](https://youtu.be/i5LiEp7j9Nw) [Recording 2/2](https://youtu.be/CbxqvnLUG04)  
 - [Introduction to tropical geometry](https://drive.google.com/file/d/1XOqjtNvNWxntMs9MDchZZKmBkPY8Tvb6/view?usp=sharing)      [Mateusz Skomra (LAAS-CNRS)](https://homepages.laas.fr/mskomra/)
	 - [Hand-out](https://drive.google.com/file/d/1yAnOPlLlnOHmopz_xwbwtERjJ4TRfvE1/view?usp=sharing)  [Recording](https://youtu.be/k31WQzQZPdQ) (Part 1)  [Recording](https://youtu.be/EBYKAcmhWTM) (Part 2)
 - [Algebraic Varieties and Regularization](https://drive.google.com/file/d/19-68WT9JOY3YAZTgyiGgC9Ohir-2xFr4/view?usp=drivesdk) - [Simon Telen]((https://sites.google.com/view/simontelen/home-page))

	 




