---
title: Applications to Finance
tags:
  - WP3
  - application
---
**Author:** Llorenç Balada

Many financial questions involve an uncertain future. What might a share be worth next year? How much could a portfolio lose? What payment should we expect from a contract linked to future market prices?

Mathematical models help us answer these questions by describing possible outcomes and their probabilities. Often, the calculation we need is an average over those outcomes. Monte Carlo simulation is a standard way to estimate this average. Quantum computing offers another approach, but making it useful requires us to represent the underlying probabilities efficiently. This is where tensor networks can help.

## From possible outcomes to an average payment

A **probability distribution** tells us which outcomes are possible and how likely each one is. If outcome $x_i$ has probability $p_i$, then

$$
p_i\geq 0,
\qquad
\sum_i p_i=1.
$$

Suppose a simplified model gives three possible prices for a share in one year:

| Future share price | Probability |
|---|---:|
| €80 | 25% |
| €100 | 50% |
| €120 | 25% |

Now consider a contract that pays the amount by which the future price exceeds €100. If the share reaches €120, it pays €20; otherwise, it pays nothing. This is the payment from a **call option** with a strike price of €100:

$$
f(S)=\max(S-100,0).
$$

The average payment predicted by the model is

$$
\mathbb{E}[f(S)]
=
0.25\times 0
+
0.50\times 0
+
0.25\times 20
=
€5.
$$

The symbol $\mathbb{E}$ means **expected value**: a probability-weighted average. More generally,

$$
\boxed{
\mathbb{E}[f(X)]=\sum_i p_i f(x_i).
}
$$

Expected values appear throughout finance, from estimating portfolio losses to pricing options. For option pricing, the probabilities must follow financial pricing theory, and future payments must also be discounted to their present value. The central computational task remains the evaluation of an expectation. [Rebentrost, Gupt and Bromley (2018)](https://arxiv.org/abs/1805.00109)

## Monte Carlo: learning the average from random scenarios

Our example has only three outcomes, so we can calculate the average directly. A realistic model might include many assets and their prices at many different times. There can be far too many scenarios to list them all.

**Monte Carlo simulation** avoids this enumeration. It generates random scenarios according to the model, calculates the payment in each one, and takes their average:

$$
\widehat{\mu}_{\mathrm{MC}}
=
\frac{1}{N}
\sum_{j=1}^{N} f(X^{(j)}).
$$

Here, $X^{(j)}$ is the $j$-th simulated scenario, and $N$ is the number of simulations.

The estimate improves as we generate more scenarios. However, for independent samples with finite variance, its root-mean-square statistical error is

$$
\sqrt{
\mathbb{E}\!\left[
(\widehat{\mu}_{\mathrm{MC}}-\mu)^2
\right]
}
=
\frac{\sigma}{\sqrt{N}},
\qquad
\mu=\mathbb{E}[f(X)].
$$

Here, $\sigma$ measures how much the payments vary between scenarios. Consequently, reducing the error by a factor of ten requires roughly one hundred times as many simulations. This becomes costly when we need accurate estimates. [Montanaro (2015)](https://arxiv.org/abs/1504.06987)

## Representing probabilities on a quantum computer

To use a quantum algorithm, we first need a quantum version of our probability model.

A quantum computer uses **qubits**. When measured, each qubit gives either 0 or 1, but before measurement, several qubits can be in a **superposition** of different binary strings. These strings can label our market scenarios.

We represent the distribution with a state of the form

$$
|\psi\rangle=\sum_i\sqrt{p_i}\,|i\rangle.
$$

The notation $|i\rangle$ labels scenario $i$. Its coefficient, $\sqrt{p_i}$, is called an **amplitude**. Measurement probabilities are the squared magnitudes of amplitudes, so

$$
\Pr(\text{observe scenario }i)=|\sqrt{p_i}|^2=p_i.
$$

For our example, label the three prices with $00$, $01$, and $10$. The state becomes

$$
|\psi\rangle
=
\frac12|00\rangle
+
\frac{1}{\sqrt2}|01\rangle
+
\frac12|10\rangle.
$$

Constructing this state is called **state preparation**. It is a necessary step before applying quantum estimation algorithms. [Rebentrost, Gupt and Bromley (2018)](https://arxiv.org/abs/1805.00109)

## Encoding the distribution efficiently with tensor networks

With $n$ qubits, we can label $2^n$ scenarios. But this compact description does not mean that loading an arbitrary distribution is easy: specifying all its amplitudes could still require $2^n$ numbers.

To make preparation efficient, we need to use structure in the distribution. Smoothness, symmetries, or particular relationships between variables may allow a much smaller representation. **Tensor networks** provide one way to find and use that structure.

A tensor is an array with several indices. For example, a joint probability distribution for three assets is a tensor whose entry $P_{ijk}$ gives the probability of a particular combination of their prices.

Quantum amplitudes also form a tensor. Writing the scenario label as a binary string gives

$$
A_{b_1b_2\cdots b_n}
=
\sqrt{p_{b_1b_2\cdots b_n}},
\qquad b_j\in\{0,1\}.
$$

A tensor network represents this large array using connected smaller arrays. In a **matrix product state**, also known as a **tensor train**, an amplitude is approximated by multiplying a sequence of small matrices:

$$
\boxed{
A_{b_1b_2\cdots b_n}
\approx
G_1(b_1)G_2(b_2)\cdots G_n(b_n).
}
$$

The first and last factors have dimensions that make the final result a single number. If the intermediate matrix dimensions remain bounded by a modest value $\chi$, the storage requirement scales approximately as

$$
O(n\chi^2)
\quad\text{instead of}\quad
2^n.
$$

The number $\chi$ is called the **bond dimension**. Larger bond dimensions can capture more complicated structure, but require more resources. [Iaconis, Johri and Zhu (2024)](https://doi.org/10.1038/s41534-024-00805-0)

This representation can also guide the construction of a quantum circuit that prepares the desired state. Researchers have investigated this approach for smooth functions, including Gaussian and lognormal distributions. The benefit depends on whether the required amplitudes admit an accurate, compact tensor representation. [Holmes and Matsuura (2020)](https://arxiv.org/abs/2005.04351)

## Using Quantum Amplitude Estimation to calculate the average

Once the distribution is prepared, we still need to extract the expected payment. Measuring the state repeatedly would simply generate random scenarios, much like Monte Carlo.

**Quantum Amplitude Estimation (QAE)** uses additional quantum operations to estimate a probability more efficiently.

First, suppose our finite model has payments between zero and $F_{\max}$. We rescale them:

$$
g_i=\frac{f(x_i)}{F_{\max}},
\qquad 0\leq g_i\leq 1.
$$

We then add an extra qubit. For each scenario $i$, the circuit makes this qubit have probability $g_i$ of being measured as 1. Across the whole distribution, that probability is

$$
\boxed{
a=\sum_i p_i g_i
=
\frac{\mathbb{E}[f(X)]}{F_{\max}}.
}
$$

Estimating $a$ therefore gives the expected payment through

$$
\mathbb{E}[f(X)]=F_{\max}a.
$$

QAE uses the preparation circuit and its reverse to create quantum interference from which this probability can be inferred. For a bounded, rescaled quantity and a fixed confidence level, the costs scale as

$$
\begin{aligned}
\text{Ordinary Monte Carlo:}\quad
&O(\varepsilon^{-2})\text{ samples},\\
\text{Ideal QAE:}\quad
&O(\varepsilon^{-1})\text{ circuit calls},
\end{aligned}
$$

where $\varepsilon$ is the desired absolute error. This is the **quadratic speedup** offered by QAE. [Brassard and colleagues (2002)](https://arxiv.org/abs/quant-ph/0005055)

## Putting the pieces together

The calculation now has a clear sequence:

$$
\text{Probability model}
\;\longrightarrow\;
\text{tensor representation}
\;\longrightarrow\;
\text{quantum state preparation}
\;\longrightarrow\;
\text{QAE estimate}.
$$

Tensor networks help with representing and preparing the distribution; QAE improves the scaling of the estimation step. Whether this leads to a practical advantage depends on the full cost, including preparation, payment evaluation, approximation errors, and quantum hardware errors. Research on tensor-based preparation identifies the complete estimation workflow as an important next step. [Iaconis, Johri and Zhu (2024)](https://doi.org/10.1038/s41534-024-00805-0)

