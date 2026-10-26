---
title: Applications to Energy
tags:
  - WP3
  - application
---
**Author:** Luca Wellmeier

One of the most important problems in power systems engineering is the following:

> How can an electric grid meet consumer demands at the lowest possible economic generation cost while respecting the physical limitations of its components.

This is usually referred to as the **Optimal Power Flow** problem, and, since energy transmission lines are more efficiently built on alternating current, often abbreviated as AC-OPF.
It can be modeled mathematically as an optimization problem where:
- the variables encode a grid configuration (including power generation targets, voltages etc.),
- the objective is the minimization of total grid operating cost for a given configuration, and
- the constraints are the physical laws of power transmission and the limits of the installed equipment (thermal limits of transmission lines, energy generation limits, and so on).

In practice, such models can become enormous: think about a whole country's energy infrastructure.
Even after coarse simplification, one often ends up with grids containing thousands of generators, loads, transformers, shunts and all sorts of other equipment that all need to be controlled simultaneously.
To make things worse, such models are generally formulated with quadratic or even quartic terms, making the optimization landscape highly non-linear and non-convex.
Thus, lots of resarch effort has been spent on finding better solutions as even seemingly tiny improvements can save a grid operators millions.

In this post, we introduce the basic engineering background needed for the AC-OPF problem, and discuss a rather recent line of research that tries to tackle the problem via global optimization instead of the industry-standard approaches via local optimization.

## A brief introduction to AC power flow

_WIP_

## From local to global optimization

_WIP_

## Recent results

_WIP_

## References

1. Blog post by Letif Mones (2020): "A Gentle Introduction to Power Flow". Published on _Invenia Blog_ ([web](https://invenia.github.io/blog/2020/12/04/pf-intro/)).
2. Article by Ghaddar, Marecek, Mevissen (2015): Optimal Power Flow as a Polynomial Optimization Problem. Published in _IEEE Transactions on Power Systems Volume_ ([journal](https://ieeexplore.ieee.org/abstract/document/7024950/), [preprint](https://arxiv.org/abs/1404.3626)).
3. Article by Wang, Magron, Lasserre (2022): "Certifying global optimality of AC-OPF solutions via sparse polynomial optimization". Published in _Electric Power Systems Research_ ([journal](https://doi.org/10.1016/j.epsr.2022.108683), [preprint](https://arxiv.org/abs/2109.10005)).
4. Article by Le Franc, Magron, Lasserre, Ruiz, Panciatici (2023): "Minimal sparsity for second-order moment-SOS relaxations of the AC-OPF problem". Published in _IEEE Transactions on Power Systems_ ([journal](https://doi.org/10.1109/TPWRS.2023.3333691), [preprint](https://arxiv.org/abs/2305.19232)).
5. Data repository (v23, 2023): "`pglib-opf`: Benchmarks for the Optimal Power Flow Problem". Published on GitHub ([web](https://github.com/power-grid-lib/pglib-opf)).
