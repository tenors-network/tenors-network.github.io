---
title: Tensors with Structures
tags:
  - tensor
  - WP2
  - algorithms
  - WP1
  - geometry
---
**Authors:** Matteo Bechere, Henri Breloer


## Tensors with symmetries

In mathematics, the concept of **symmetry** is encoded by group actions. A group can act on a tensor by changing coordinates, permuting its indices, or transforming the underlying vector spaces. A tensor is called **invariant** if it remains unchanged under the action. More generally, an **equivariant** tensor transforms according to a fixed rule.

Symmetries appear naturally in geometry, data analysis, and physics. Rotations and reflections describe Euclidean symmetries, permutation groups exchange indistinguishable variables, and matrix groups encode changes of coordinates. Identifying these actions can help to identify which features of a tensor are intrinsic and which depend extrinsically on the chosen representation.

### Permutations and tensor spaces

One of the most fundamental symmetries of a tensor comes from permuting its factors. For a vector space $V$, the symmetric group acts on the tensor power $V^{\otimes d}$ by rearranging the $d$ factors. Tensors fixed by every permutation are **symmetric tensors** and form the space $\mathrm{Sym}^d(V)$. Alternating tensors instead acquire the sign of the permutation and form the exterior power $\bigwedge^d V$.

More general tensors need not be completely symmetric or alternating. They may satisfy mixed symmetry relations associated with partitions and Young diagrams. These different symmetry types provide a natural way to organize the otherwise very large space $V^{\otimes d}$.

### Schur–Weyl duality

A central example of the interaction between group actions and tensors is **Schur–Weyl duality**. On $V^{\otimes d}$, there are two commuting actions: the general linear group $\mathrm{GL}(V)$ acts simultaneously on every tensor factor, while the symmetric group $\mathfrak{S}_d$ permutes those factors.

Schur–Weyl duality describes how these two actions determine one another and decompose the tensor space into components indexed by partitions of $d$. Each component records both a type of permutation symmetry and an irreducible representation of $\mathrm{GL}(V)$. This provides a bridge between multilinear algebra and the representation theory of symmetric and linear groups.

From a computational perspective, such a decomposition replaces one large tensor space with smaller, structured pieces. Problems involving linear maps, equations, or invariants can often be studied separately on these components.

### Invariants and changes of coordinates

A second important question is how to describe quantities that remain unchanged when a group acts on a tensor. Such quantities are called **invariants**. For example, when the orthogonal group acts by rotations and reflections, invariant functions capture information that does not depend on the choice of orthonormal coordinates.

Invariant theory seeks to construct these functions and determine whether they distinguish generic group orbits. Polynomial invariants are often the first objects considered, but rational invariants, quotients of polynomial functions, can provide a more flexible description. They can serve as coordinates on a quotient space and help classify tensors up to the relevant symmetry.

### Symmetric tensors and homogeneous polynomials

Symmetric tensors have a particularly useful interpretation: an element of $\mathrm{Sym}^d(V)$ can be identified with a homogeneous polynomial, or **form**, of degree $d$. Under this correspondence, a change of coordinates in $V$ induces an action on the polynomial’s variables. Questions about symmetric tensors modulo a group action can therefore be translated into questions about homogeneous polynomials modulo coordinate transformations.

For the orthogonal group, the problem becomes that of understanding which rational expressions in the coefficients of a form remain unchanged under rotations and reflections. The even-degree case has additional structure arising from the compatibility between the polynomial degree and the quadratic form preserved by the orthogonal group.

A concrete study of this setting is given in [*Rational invariants of even degree polynomials under the orthogonal group*](https://arxiv.org/abs/2501.17504). The article investigates rational invariants for even-degree homogeneous polynomials under orthogonal transformations. Through the identification of homogeneous polynomials with symmetric tensors, it provides an example of how group actions, invariant theory, and tensor symmetries combine to describe tensors independently of the coordinates used to represent them.

## Tensor with structured decomposition 
Tensors are a way of representing multidimensional information and they appear in fields ranging from engineering and statistics, to signal processing and scientific computing. Unfortunately, tensors can become large and difficult to interpret. Tensor decomposition addresses this problem by expressing a complicated tensor as a sum of simpler building blocks, known as simple tensors.
Decompositions often reveal patterns which are hidden in the original data. They also provide a compact representation: the smallest number of simple building blocks needed to reconstruct a tensor is called its __rank__ and it is a measure of the tensor's complexity.

### Where *structure* enters
Many tensors encountered in practice are not arbitrary. Their entries may be linked to symmetries or constraints, so the simple components in their decomposition are expected to lie on a particular geometric shape.

In [this](https://arxiv.org/abs/2606.25712) recent work, we study symmetric tensors whose components lie on a __rational variety__. The points of this geometrical shape can be generated by a small collection of parameters using polynomial or rational formulae. Instead of searching freely through the whole space, we know in advance that the building blocks must lie in this lower-dimensional shape.

### Turning structure into an advantage
This additional constraint might appear to make the (already hard) decomposition problem harder! In fact, it can make the problem substantially smaller. The central idea is to translate the original structured tensor into another symmetric tensor involving fewer variables, though generally of higher order.
Under suitable assumptions, decomposing this smaller object is equivalent to decomposing the original one ([Theorem 3.17.](https://arxiv.org/pdf/2606.25712)). The correspondence preserves the number of components: every decomposition of the reduced tensor produces a structured decomposition of the original tensor with the same length, and vice versa.

The resulting strategy ([Algorithm 4.1.](https://arxiv.org/pdf/2606.25712)) is therefore:
1. Recognize the tensor's geometric structure.
2. Transform the tensor into a lower-dimensional representation.
3. Decompose the smaller representation.
4. Map the result back to the original tensor.

This is valuable because standard decomposition methods, that don't exploit structured data, may struggle with the original tensor, even when a short decomposition exists. In [Symmetric tensor decomposition on rational varieties](https://arxiv.org/abs/2606.25712) we give an example ([Section 4.1](https://arxiv.org/pdf/2606.25712)) in which a direct method fails on a symmetric tensor of size 6 and order 4, while the structure-aware approach makes the decomposition possible.

The takeaway message is that having structure on your tensors is not just an extra restriction, instead it is useful geometric information that, when incorporated in the decomposition methods, often allows to solve decomposition problems that would otherwise be out of reach.

To dive deeper into the topic, more technical presentation of parts of the paper [Symmetric tensor decomposition on rational varieties](https://arxiv.org/abs/2606.25712) can [be found on Youtube](https://www.youtube.com/watch?v=rA4nNGRQBtM).
