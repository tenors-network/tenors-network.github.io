---
title: Applications to Quantum Information
tags:
  - "#optimization"
  - quantum
  - application
  - WP3
---
**Authors:** Jonas Britz, Younes Naceur


## Polynomial optimization in quantum information

Many problems in quantum information, such as characterizing quantum correlations, detecting entanglement, and optimizing quantum dynamics, can be formulated as polynomial optimization problems involving quantum states and measurement operators. Since these problems are generally nonconvex and computationally hard, **moment and sum-of-squares (SOS) hierarchies** provide systematic approximations through semidefinite programming (SDP).

Two prominent applications are:

- **NPA hierarchy (Navascués–Pironio–Acín):** A hierarchy of semidefinite relaxations for characterizing quantum correlations in Bell scenarios. Based on moments of noncommuting measurement operators, it provides upper bounds on Bell inequality violations and tests whether observed correlations are compatible with quantum theory [1].
- **DPS hierarchy (Doherty–Parrilo–Spedalieri):** A hierarchy of semidefinite tests for quantum state separability, based on symmetric extensions and positive partial transposition. Successively higher levels give increasingly strong criteria for detecting entanglement [2].

## Research contributions

### Certified bounds on optimization problems in quantum theory

Numerical semidefinite relaxations can produce bounds that are not mathematically rigorous due to floating-point errors. In [3], we develop a framework for extracting **certified rational bounds** from numerical solutions of noncommutative polynomial optimization problems. The method also exploits sparsity and symmetry to provide reliable certificates for several quantum information problems.

### Reachability and optimal-time certificates for quantum control

In [4], we apply moment relaxations with differential constraints to **quantum optimal control**. Our framework provides rigorous upper bounds on achievable fidelities and lower bounds on the minimum time required to reach target quantum states or gates under control constraints. Applications include entangled-state preparation, quantum gate synthesis, and excitation transfer in spin chains.

### Semidefinite hierarchies for diagonal unitary invariant bipartite quantum states



## References

1. M. Navascués, S. Pironio, A. Acín, [*A convergent hierarchy of semidefinite programs characterizing the set of quantum correlations*](https://doi.org/10.1088/1367-2630/10/7/073013), New Journal of Physics **10**, 073013 (2008).
2. A. C. Doherty, P. A. Parrilo, F. M. Spedalieri, [*Complete family of separability criteria*](https://doi.org/10.1103/PhysRevA.69.022308), Physical Review A **69**, 022308 (2004).
3. Y. Naceur, J. Wang, V. Magron, A. Acín, [*Certified bounds on optimization problems in quantum theory*](https://arxiv.org/abs/2512.17713), arXiv:2512.17713 (2025).
4. Y. Naceur, L. Balada Gaggioli, [*Reachability and optimal-time certificates for quantum control*](https://arxiv.org/abs/2606.24645), arXiv:2606.24645 (2026).
5. J. Britz, M. Laurent, [*Semidefinite hierarchies for diagonal unitary invariant bipartite quantum states*](https://arxiv.org/abs/2512.06551), arXiv:2512.06551 (2025).


# Courses

-  [Compatibility problems in quantum information](https://drive.google.com/file/d/1F8wkrT4JAQfWFxB_3ncruZYvJmd82m61/view?usp=sharing)|[Omar Fawzi (École Normale Supérieure de Lyon)](https://perso.ens-lyon.fr/omar.fawzi/)
	- [Slides](https://drive.google.com/file/d/1j4Jq_vYYZBdF5R1bvKH2Yh6edtSfBE1C/view?usp=sharing) [Recording](https://youtu.be/Htk5io1cSls) 
