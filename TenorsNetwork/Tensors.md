---
title: Tensors
aliases:
  - tensor
tags:
  - tensor
  - polynomial
---

What are tensors ?

Vectors are generalizations of scalars in higher *dimension*. Matrices are generalizations of vectors in another *mode*. Tensors can be seen as generalizations of matrices in *higher modes*. 

## Multlinear tensors

$$
T \equiv [T_{i_1, ..., i_d}] = \sum_{i_1, \ldots, i_n}  T_{i_1, \ldots, i_d}\, x_{1,i_1} \otimes \cdots \otimes x_{d,i_d} \quad \in E_1 \otimes \cdots \otimes E_d
$$ 
## Symmetric tensors 

$$
F = \sum_{|\alpha|=d} F_{\alpha} x_1^{\alpha_1} \cdots x_n^{\alpha_n} = \sum_{|\alpha|=d} F_{\alpha}\, \mathbf{x}^{\alpha} \quad \in S^d(E)
$$

## Skew-symmetric tensors

$$
\Psi = \sum_{i_1< \cdots < i_d} \Psi_{i_1, \ldots, i_d}\, x_{i_1} \wedge \cdots \wedge x_{i_d} \quad \in \wedge^d(E)
$$
## Multi-symmetric tensors

$$
F = \sum_{|\alpha_1|=d_1,\ldots, |\alpha_m|= d_m} F_{\alpha_1, \ldots, \alpha_m}\, \mathbf{x}_{1}^{\alpha_1} \cdots \mathbf{x}_m^{\alpha_m} \quad \in S^{d_1}(E_1) \otimes \cdots \otimes S^{d_m}(E_m)
$$