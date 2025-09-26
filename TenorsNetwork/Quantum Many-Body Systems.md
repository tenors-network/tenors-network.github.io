# Algebraic Varieties in Quantum Many-Body Physics

In quantum many-body physics, one often studies **families of quantum states** that are defined by algebraic constraints. These families naturally form **algebraic varieties**, i.e. solution sets of polynomial equations.

## 1. From Quantum States to Varieties

- A pure state of \(N\) particles in local Hilbert space \(\mathbb{C}^d\) is a vector
  \[
  \psi \in (\mathbb{C}^d)^{\otimes N}.
  \]
- In coordinates, \(\psi\) is specified by complex amplitudes \(\psi_{i_1 i_2 \dots i_N}\).
- Imposing algebraic relations among these amplitudes defines a **variety** inside projective space \(\mathbb{P}^{d^N - 1}\).

**Example:**
- **Product states** are tensors of rank one. The set of all product states is the **Segre variety**
  \[
  \text{Seg}(\mathbb{P}^{d-1} \times \cdots \times \mathbb{P}^{d-1}) \subset \mathbb{P}^{d^N - 1}.
  \]

## 2. Varieties from Entanglement Structure

- **Matrix Product States (MPS):** Defined by polynomial relations between amplitudes and tensor parameters. The closure of the set of MPS of fixed bond dimension forms an algebraic variety.
- **Symmetry constraints:** Imposing invariance under group actions leads to varieties cut out by polynomial invariants.
- **Rank conditions:** Reduced density matrices with bounded rank correspond to determinantal varieties.

## 3. Why Varieties Matter

- **Classification:** Algebraic geometry provides a language to classify families of quantum states.
- **Geometry ↔ Physics:** Singularities, dimension, and degree of a variety reflect physical features such as degeneracy, correlations, or phase transitions.
- **Computational tools:** Polynomial equations allow symbolic and numerical methods (Gröbner bases, tensor networks) to analyze many-body states.

## 4. Outlook

The study of algebraic varieties arising in quantum many-body physics bridges:
- **Physics**: entanglement, correlations, tensor network ansätze.  
- **Mathematics**: projective geometry, invariant theory, commutative algebra.  

This perspective opens pathways for **exact classifications** of quantum states and **new algorithms** for simulation and optimization.

