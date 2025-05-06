# A Beginner's Detailed Guide to Quantum Computing Fundamentals

## Table of Contents

*   [Introduction: The Quantum Leap](#introduction-the-quantum-leap)
*   [I. From Classical Bits to Quantum Qubits: The Building Blocks](#i-from-classical-bits-to-quantum-qubits-the-building-blocks)
    *   [A. Classical Bits: The Certainty of 0 or 1](#a-classical-bits-the-certainty-of-0-or-1)
    *   [B. Quantum Qubits: Embracing Uncertainty with Superposition](#b-quantum-qubits-embracing-uncertainty-with-superposition)
    *   [C. The Measurement Problem: Collapsing Possibilities](#c-the-measurement-problem-collapsing-possibilities)
    *   [D. Dirac Notation: The Language of Quantum States](#d-dirac-notation-the-language-of-quantum-states)
        *   [1. Kets: Representing Quantum States](#1-kets-representing-quantum-states)
        *   [2. Bras: The Dual Representation](#2-bras-the-dual-representation)
        *   [3. Inner Product (Bra-Ket): Overlap and Projection](#3-inner-product-bra-ket-overlap-and-projection)
        *   [4. Normalization: Probability Adds Up](#4-normalization-probability-adds-up)
        *   [5. Orthogonality: Distinguishable States](#5-orthogonality-distinguishable-states)
        *   [6. Outer Product (Ket-Bra): Building Operators](#6-outer-product-ket-bra-building-operators)
    *   [E. Measurement Formalism: The Born Rule](#e-measurement-formalism-the-born-rule)
        *   [1. Measurement Bases](#1-measurement-bases)
        *   [2. Calculating Probabilities (Born Rule)](#2-calculating-probabilities-born-rule)
        *   [3. Post-Measurement State](#3-post-measurement-state)
        *   [4. Detailed Measurement Examples](#4-detailed-measurement-examples)
    *   [F. The Bloch Sphere: A Qubit's Globe](#f-the-bloch-sphere-a-qubits-globe)
        *   [1. Parameterizing a Qubit State](#1-parameterizing-a-qubit-state)
        *   [2. Mapping to the Sphere](#2-mapping-to-the-sphere)
        *   [3. Why $\theta/2$? The Geometry of Probability](#3-why-theta2-the-geometry-of-probability)
        *   [4. Visualizing Key States](#4-visualizing-key-states)
*   [II. Quantum Circuits: Choreographing Qubits](#ii-quantum-circuits-choreographing-qubits)
    *   [A. The Circuit Model: A Quantum Flowchart](#a-the-circuit-model-a-quantum-flowchart)
    *   [B. Single-Qubit Gates: Manipulating Individual Qubits](#b-single-qubit-gates-manipulating-individual-qubits)
        *   [1. The Need for Unitarity (Reversibility & Normalization)](#1-the-need-for-unitarity-reversibility--normalization)
        *   [2. Pauli Gates (X, Y, Z): Fundamental Flips and Phases](#2-pauli-gates-x-y-z-fundamental-flips-and-phases)
        *   [3. Hadamard Gate (H): The Superposition Engine](#3-hadamard-gate-h-the-superposition-engine)
        *   [4. Phase Gates (S, T): Fine-Tuning Phases](#4-phase-gates-s-t-fine-tuning-phases)
        *   [5. Gates as Bloch Sphere Rotations](#5-gates-as-bloch-sphere-rotations)
    *   [C. Multi-Qubit Systems: Scaling Up with Tensor Products](#c-multi-qubit-systems-scaling-up-with-tensor-products)
        *   [1. Why Tensor Products? Combining Spaces](#1-why-tensor-products-combining-spaces)
        *   [2. Constructing Multi-Qubit Basis States (Vectors)](#2-constructing-multi-qubit-basis-states-vectors)
        *   [3. General Multi-Qubit States](#3-general-multi-qubit-states)
        *   [4. Separable vs. Entangled States Defined](#4-separable-vs-entangled-states-defined)
    *   [D. Multi-Qubit Gates: Qubit Interactions](#d-multi-qubit-gates-qubit-interactions)
        *   [1. The Controlled-NOT (CNOT) Gate: Conditional Logic](#1-the-controlled-not-cnot-gate-conditional-logic)
        *   [2. Other Controlled Gates (Conceptual)](#2-other-controlled-gates-conceptual)
    *   [E. Universality: Building Any Computation](#e-universality-building-any-computation)
*   [III. Entanglement: The Spooky Connection](#iii-entanglement-the-spooky-connection)
    *   [A. Defining Entanglement (Revisited)](#a-defining-entanglement-revisited)
    *   [B. Bell States: The VIPs of Entanglement](#b-bell-states-the-vips-of-entanglement)
        *   [1. The Four States](#1-the-four-states)
        *   [2. Creating Bell States: A Step-by-Step Circuit Derivation](#2-creating-bell-states-a-step-by-step-circuit-derivation)
        *   [3. Bell Measurement: Identifying Entangled States](#3-bell-measurement-identifying-entangled-states)
    *   [C. Quantum Teleportation: Beam Me Up, Scotty?](#c-quantum-teleportation-beam-me-up-scotty)
        *   [1. The Setup and The Goal](#1-the-setup-and-the-goal)
        *   [2. The Protocol Step-by-Step (with Derivations)](#2-the-protocol-step-by-step-with-derivations)
        *   [3. Circuit Diagram and Interpretation](#3-circuit-diagram-and-interpretation)
        *   [4. Crucial Caveats: No Cloning, No FTL Communication](#4-crucial-caveats-no-cloning-no-ftl-communication)
    *   [D. The Q-Sphere: Visualizing Many Qubits](#d-the-q-sphere-visualizing-many-qubits)
*   [IV. Deeper Mathematical Foundations](#iv-deeper-mathematical-foundations)
    *   [A. Hilbert Space: The Quantum Arena](#a-hilbert-space-the-quantum-arena)
    *   [B. Inner and Outer Products: Tools for Calculation](#b-inner-and-outer-products-tools-for-calculation)
    *   [C. Operators, Observables, and Eigen-things](#c-operators-observables-and-eigen-things)
        *   [1. Linear Operators](#1-linear-operators)
        *   [2. Hermitian Operators and Observables](#2-hermitian-operators-and-observables)
        *   [3. Unitary Operators and Evolution](#3-unitary-operators-and-evolution)
    *   [D. Expectation Values: The Average Outcome](#d-expectation-values-the-average-outcome)
        *   [1. Definition and Calculation Methods](#1-definition-and-calculation-methods)
        *   [2. Deriving $⟨A⟩ = ⟨ψ|A|ψ⟩$](#2-deriving-a--psiaipsi)
        *   [3. Examples](#3-examples)
    *   [E. Operators on Multi-Qubit Systems (Tensor Products of Operators)](#e-operators-on-multi-qubit-systems-tensor-products-of-operators)
        *   [1. Local Operators ($A \otimes I, I \otimes B$)](#1-local-operators-a-otimes-i-i-otimes-b)
        *   [2. Global Operators ($A \otimes B$)](#2-global-operators-a-otimes-b)
    *   [F. Spin and Rotations: The Qubit-Spin Connection](#f-spin-and-rotations-the-qubit-spin-connection)
        *   [1. The Analogy](#1-the-analogy)
        *   [2. General Rotations $R_{\vec{n}}(\theta)$](#2-general-rotations-r_vecntheta)

## Introduction: The Quantum Leap

Classical computers, the bedrock of our digital age, operate on a simple principle: information is stored in **bits**, which can be either **0** or **1**. Quantum computing takes a leap into the strange and fascinating world of quantum mechanics, using **qubits** as its fundamental unit. Qubits can be 0, 1, or, remarkably, *both at the same time* through a property called **superposition**. They can also be mysteriously linked through **entanglement**. These quantum phenomena unlock possibilities for computation far beyond the reach of classical machines for certain types of problems. This guide will walk you through the essential concepts needed to understand this exciting field, starting from the very beginning.

---

## I. From Classical Bits to Quantum Qubits: The Building Blocks

### A. Classical Bits: The Certainty of 0 or 1

*   **Definition:** The fundamental unit of information in all classical computers (laptops, smartphones, supercomputers).
*   **States:** A bit must exist in one of two *mutually exclusive* and *definite* states:
    *   **0** (representing OFF, False, Low Voltage, etc.)
    *   **1** (representing ON, True, High Voltage, etc.)
*   **Certainty:** Until it's flipped, a bit *is* either 0 or 1. There's no ambiguity.

### B. Quantum Qubits: Embracing Uncertainty with Superposition

*   **Definition:** The fundamental unit of quantum information, leveraging quantum mechanical principles.
*   **Basis States:** Like a bit, a qubit has two special fundamental states, called the **computational basis states**, which correspond to the classical 0 and 1:
    *   $|0⟩$ (read "ket zero")
    *   $|1⟩$ (read "ket one")
    (We'll explore the $|⟩$ notation soon.)
*   **Superposition:** This is where qubits dramatically differ from bits. A qubit can exist in a state that is a *combination* or *superposition* of both $|0⟩$ and $|1⟩$ *simultaneously*. We write the general state of a qubit, $|ψ⟩$ (ket psi), as:
    $$
    |ψ⟩ = α|0⟩ + β|1⟩
    $$
    *   **Amplitudes ($α, β$):** These are not just weights, but **complex numbers** ($α, β \in \mathbb{C}$) called **probability amplitudes**. They encode both the *probability* of finding the qubit as 0 or 1 upon measurement *and* a *phase* relationship between the $|0⟩$ and $|1⟩$ components.
    *   **Probability Rule:** The probability of measuring the qubit as 0 is $P(0) = |α|^2$ (magnitude of $α$ squared). The probability of measuring 1 is $P(1) = |β|^2$.
    *   **Normalization Condition:** Because the probabilities must sum to 100%, the amplitudes must always satisfy:
        $$
        |α|^2 + |β|^2 = 1
        $$
    *   **Analogy (Spinning Coin):** Imagine a coin spinning in the air. Before it lands, it's neither heads nor tails. It's in a state that has the *potential* to be either. Superposition is like this spinning state – the qubit holds the potential for both $|0⟩$ and $|1⟩$, described precisely by $α$ and $β$. Only when the coin lands (measurement) does it resolve into a definite heads or tails (0 or 1).
*   **Computational Power:** Why is superposition powerful?
    *   A single qubit holds information about the probabilities ($|α|^2, |β|^2$) and relative phase ($\phi$ in $β/α = \tan(\theta/2)e^{i\phi}$).
    *   Consider $n$ qubits. A classical $n$-bit register holds *one* $n$-bit number (e.g., `011`). An $n$-qubit register can be in a superposition of *all* $2^n$ possible classical states:
        $$
        |Ψ⟩ = α_{0...0}|0...0⟩ + α_{0...1}|0...1⟩ + \dots + α_{1...1}|1...1⟩ = \sum_{x \in \{0,1\}^n} α_x |x⟩
        $$
        where $\sum |α_x|^2 = 1$. This allows quantum computers to explore a vast computational space simultaneously, leading to potential exponential speedups for specific algorithms (like Shor's algorithm for factoring or Grover's algorithm for searching).

### C. The Measurement Problem: Collapsing Possibilities

Superposition is powerful, but accessing the information isn't straightforward due to measurement.

*   **The Act of Measuring:** When we try to *measure* a qubit in a superposition state $|ψ⟩ = α|0⟩ + β|1⟩$ to determine if it's a 0 or 1, the quantum state undergoes a process called **collapse** (or state reduction).
*   **Outcome:** The superposition ceases to exist, and the qubit is forced into *one* of the classical basis states:
    *   It becomes $|0⟩$ with probability $P(0) = |α|^2$.
    *   It becomes $|1⟩$ with probability $P(1) = |β|^2$.
*   **Information Loss:** The measurement result is probabilistic. We get only *one* classical bit (0 or 1) from a single measurement. We cannot directly "see" the original complex amplitudes $α$ and $β$ or their phase relationship in a single shot. Repeated measurements on *identically prepared* qubits are needed to estimate $|α|^2$ and $|β|^2$.
*   **Quantum Algorithm Strategy:** Effective quantum algorithms don't try to read out all $2^n$ amplitudes. They use quantum gates to manipulate the amplitudes and phases, employing **interference** (where amplitudes can add constructively or destructively, like waves) to ensure that when the final measurement is made, the probability of measuring the *correct* answer is very high, while probabilities for incorrect answers are suppressed.

### D. Dirac Notation: The Language of Quantum States

To handle quantum states mathematically, we use **Dirac notation**, also called **bra-ket notation**. It's built on linear algebra (vectors and matrices).

#### 1. Kets: Representing Quantum States

*   A quantum state is represented by a **ket**, denoted $|ψ⟩$.
*   Mathematically, a ket is a **column vector** in a complex vector space called Hilbert space.
*   For a single qubit, the space is 2-dimensional ($ℂ^2$). The computational basis kets are:
    $$
    |0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \quad (\text{Vector representing state 0})
    $$
    $$
    |1⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \quad (\text{Vector representing state 1})
    $$
*   A general superposition state $|ψ⟩ = α|0⟩ + β|1⟩$ is represented by the column vector:
    $$
    |ψ⟩ = α\begin{pmatrix} 1 \\ 0 \end{pmatrix} + β\begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} (α \times 1) + (β \times 0) \\ (α \times 0) + (β \times 1) \end{pmatrix} = \begin{pmatrix} α \\ β \end{pmatrix}
    $$

#### 2. Bras: The Dual Representation

*   For every ket $|ψ⟩$, there is a corresponding **bra**, denoted $⟨ψ|$.
*   Mathematically, the bra is the **Hermitian conjugate** (or adjoint) of the ket. This involves two steps:
    1.  **Transpose:** Convert the column vector into a row vector.
    2.  **Complex Conjugate:** Take the complex conjugate ($*$) of each element. (Recall: $(a+bi)^* = a-bi$).
*   If $|ψ⟩ = \begin{pmatrix} α \\ β \end{pmatrix}$, then the bra $⟨ψ|$ is:
    $$
    ⟨ψ| = |ψ⟩^† = \begin{pmatrix} α \\ β \end{pmatrix}^† = \begin{pmatrix} α^* & β^* \end{pmatrix} \quad (\text{A row vector})
    $$
    (The $†$ symbol, read "dagger", denotes the Hermitian conjugate).
*   The bras corresponding to the basis states are:
    $$
    ⟨0| = |0⟩^† = \begin{pmatrix} 1 \\ 0 \end{pmatrix}^† = \begin{pmatrix} 1^* & 0^* \end{pmatrix} = \begin{pmatrix} 1 & 0 \end{pmatrix}
    $$
    $$
    ⟨1| = |1⟩^† = \begin{pmatrix} 0 \\ 1 \end{pmatrix}^† = \begin{pmatrix} 0^* & 1^* \end{pmatrix} = \begin{pmatrix} 0 & 1 \end{pmatrix}
    $$

#### 3. Inner Product (Bra-Ket): Overlap and Projection

*   Combining a bra $⟨φ|$ and a ket $|ψ⟩$ yields the **inner product**, denoted $⟨φ|ψ⟩$.
*   Calculation: It's standard matrix multiplication of the row vector (bra) and the column vector (ket). The result is a single **complex number** (scalar).
    $$
    ⟨φ|ψ⟩ = \begin{pmatrix} γ^* & δ^* \end{pmatrix} \begin{pmatrix} α \\ β \end{pmatrix} = γ^*α + δ^*β
    $$
*   **Meaning:**
    *   **Overlap:** $⟨φ|ψ⟩$ measures the "extent to which $|ψ⟩$ contains $|φ⟩$".
    *   **Projection Amplitude:** $⟨φ|ψ⟩$ is the complex amplitude of projecting state $|ψ⟩$ onto state $|φ⟩$.
    *   **Probability:** The *square* of the magnitude, $|⟨φ|ψ⟩|^2$, gives the probability that state $|ψ⟩$ will collapse to state $|φ⟩$ if measured in a basis containing $|φ⟩$.
*   **Example:** Inner product of $|ψ⟩ = \frac{1}{\sqrt{2}}|0⟩ + \frac{i}{\sqrt{2}}|1⟩$ with $|0⟩$.
    $|ψ⟩ = \begin{pmatrix} 1/\sqrt{2} \\ i/\sqrt{2} \end{pmatrix}$, $⟨0| = \begin{pmatrix} 1 & 0 \end{pmatrix}$.
    $$
    ⟨0|ψ⟩ = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 1/\sqrt{2} \\ i/\sqrt{2} \end{pmatrix} = (1)(1/\sqrt{2}) + (0)(i/\sqrt{2}) = \frac{1}{\sqrt{2}}
    $$
    The probability of measuring $|ψ⟩$ and getting outcome 0 is $P(0) = |⟨0|ψ⟩|^2 = |1/\sqrt{2}|^2 = 1/2$.

#### 4. Normalization: Probability Adds Up

*   The inner product of a state with itself, $⟨ψ|ψ⟩$, gives the squared length (norm squared) of the state vector.
    $$
    ⟨ψ|ψ⟩ = \begin{pmatrix} α^* & β^* \end{pmatrix} \begin{pmatrix} α \\ β \end{pmatrix} = α^*α + β^*β = |α|^2 + |β|^2
    $$
*   For any physically valid quantum state, the total probability of finding it in *some* state must be 1. This means all state vectors must be **normalized** (have a length of 1).
    $$
    ⟨ψ|ψ⟩ = |α|^2 + |β|^2 = 1
    $$
*   **Example:** Is $|φ⟩ = \frac{1}{2}|0⟩ + \frac{\sqrt{3}}{2}|1⟩$ normalized?
    $α = 1/2$, $β = \sqrt{3}/2$.
    $⟨φ|φ⟩ = |1/2|^2 + |\sqrt{3}/2|^2 = (1/4) + (3/4) = 4/4 = 1$. Yes, it is normalized.
*   **Example:** Is $|χ⟩ = |0⟩ + |1⟩$ normalized?
    $α = 1$, $β = 1$.
    $⟨χ|χ⟩ = |1|^2 + |1|^2 = 1 + 1 = 2$. No, it is not normalized. To normalize it, we divide by the square root of its norm squared ($\sqrt{2}$):
    $|χ_{\text{norm}}⟩ = \frac{1}{\sqrt{2}}(|0⟩ + |1⟩)$. This state is $|+⟩$, which we know is normalized.

#### 5. Orthogonality: Distinguishable States

*   Two states $|ψ⟩$ and $|φ⟩$ are **orthogonal** if their inner product is zero: $⟨φ|ψ⟩ = 0$.
*   Orthogonal states represent perfectly distinguishable outcomes in a quantum measurement.
*   The computational basis states $|0⟩$ and $|1⟩$ are orthogonal:
    $$
    ⟨0|1⟩ = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = (1)(0) + (0)(1) = 0
    $$
    And $⟨1|0⟩ = ⟨0|1⟩^* = 0^* = 0$.

#### 6. Outer Product (Ket-Bra): Building Operators

*   The **outer product** $|ψ⟩⟨φ|$ multiplies a ket (column vector) by a bra (row vector). The result is a **square matrix**, which represents a linear operator.
    $$
    |ψ⟩⟨φ| = \begin{pmatrix} α \\ β \end{pmatrix} \begin{pmatrix} γ^* & δ^* \end{pmatrix} = \begin{pmatrix} α γ^* & α δ^* \\ β γ^* & β δ^* \end{pmatrix}
    $$
*   **Projection Operators:** A key use is building projection operators. $P_x = |x⟩⟨x|$ projects onto the state $|x⟩$ (assuming $|x⟩$ is normalized).
    *   $P_0 = |0⟩⟨0| = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \begin{pmatrix} 1 & 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$
    *   $P_1 = |1⟩⟨1| = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}$
*   **Completeness Relation:** For any orthonormal basis $\{|x_i⟩\}$, the sum of the projectors equals the identity operator: $\sum_i |x_i⟩⟨x_i| = I$. For the computational basis: $P_0 + P_1 = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$.

### E. Measurement Formalism: The Born Rule

Let's formalize the measurement process.

#### 1. Measurement Bases

*   Measurements are performed relative to a chosen **orthonormal basis**. This basis represents the set of possible outcomes for the measurement.
*   **Computational (Z) Basis:** $\{|0⟩, |1⟩\}$. Used for standard measurements yielding 0 or 1. Corresponds to measuring spin/property along the Z-axis.
    <p align="center">
    <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/measure-z.png" alt="Z Measurement Symbol" width="50">
    <br>
    <em>Typical circuit symbol for Z-basis measurement</em>
    </p>
*   **Hadamard (X) Basis:** $\{|+⟩, |-⟩\}$. Corresponds to measuring along the X-axis.
    $$
    |+⟩ = \frac{1}{\sqrt{2}}(|0⟩ + |1⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}
    $$
    $$
    |-⟩ = \frac{1}{\sqrt{2}}(|0⟩ - |1⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}
    $$
    These are orthogonal: $⟨+|-⟩ = (\frac{1}{\sqrt{2}}⟨0| + \frac{1}{\sqrt{2}}⟨1|)(\frac{1}{\sqrt{2}}|0⟩ - \frac{1}{\sqrt{2}}|1⟩) = \frac{1}{2}(⟨0|0⟩ - ⟨0|1⟩ + ⟨1|0⟩ - ⟨1|1⟩) = \frac{1}{2}(1 - 0 + 0 - 1) = 0$.
*   **Circular (Y) Basis:** $\{|+i⟩, |-i⟩\}$. Corresponds to measuring along the Y-axis.
    $$
    |+i⟩ = \frac{1}{\sqrt{2}}(|0⟩ + i|1⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}
    $$
    $$
    |-i⟩ = \frac{1}{\sqrt{2}}(|0⟩ - i|1⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}
    $$
    These are also orthogonal: $⟨+i|-i⟩ = (\frac{1}{\sqrt{2}}⟨0| - \frac{i^*}{\sqrt{2}}⟨1|)(\frac{1}{\sqrt{2}}|0⟩ - \frac{i}{\sqrt{2}}|1⟩) = \frac{1}{2}(⟨0|0⟩ - i⟨0|1⟩ + i⟨1|0⟩ - i^*i⟨1|1⟩) = \frac{1}{2}(1 - 0 + 0 - (-i)(i)) = \frac{1}{2}(1 - i^2) = \frac{1}{2}(1 - (-1)) = \frac{1}{2}(2) = 1$? Mistake! Let's recalculate $⟨+i|-i⟩$:
    $⟨+i| = \frac{1}{\sqrt{2}}(⟨0| + i^*⟨1|) = \frac{1}{\sqrt{2}}(⟨0| - i⟨1|)$.
    $⟨+i|-i⟩ = \frac{1}{\sqrt{2}}(⟨0| - i⟨1|) \frac{1}{\sqrt{2}}(|0⟩ - i|1⟩) = \frac{1}{2}(⟨0|0⟩ - i⟨0|1⟩ - i⟨1|0⟩ + (-i)(-i)⟨1|1⟩) = \frac{1}{2}(1 - 0 - 0 + i^2(1)) = \frac{1}{2}(1 - 1) = 0$. They *are* orthogonal.

#### 2. Calculating Probabilities (Born Rule)

*   The probability $P(x_k)$ of obtaining the outcome associated with basis state $|x_k⟩$ when measuring state $|ψ⟩$ in the basis $\{|x_i⟩\}$ is given by the **Born Rule**:
    $$
    P(x_k) = |⟨x_k|ψ⟩|^2
    $$
    This is the squared magnitude of the projection amplitude.

#### 3. Post-Measurement State

*   Immediately after the measurement yields outcome $x_k$, the state of the system **collapses** to the corresponding basis state:
    $$
    |ψ⟩_{\text{after}} = |x_k⟩
    $$
    (If the original state was already $|x_k⟩$, the measurement yields $x_k$ with probability 1 and the state remains unchanged).

#### 4. Detailed Measurement Examples

Let's apply this to a more complex state: $|ψ⟩ = \frac{1+i}{2}|0⟩ + \frac{1-i}{2}|1⟩$.
First, check normalization: $α = \frac{1+i}{2}, β = \frac{1-i}{2}$.
$|α|^2 = |\frac{1+i}{2}|^2 = \frac{|1+i|^2}{4} = \frac{(\sqrt{1^2+1^2})^2}{4} = \frac{2}{4} = \frac{1}{2}$.
$|β|^2 = |\frac{1-i}{2}|^2 = \frac{|1-i|^2}{4} = \frac{(\sqrt{1^2+(-1)^2})^2}{4} = \frac{2}{4} = \frac{1}{2}$.
$|α|^2 + |β|^2 = 1/2 + 1/2 = 1$. State is normalized.

*   **Example 4a: Measurement in Z-basis $\{|0⟩, |1⟩\}$**
    *   $P(0) = |⟨0|ψ⟩|^2 = |α|^2 = 1/2$.
    *   $P(1) = |⟨1|ψ⟩|^2 = |β|^2 = 1/2$.
    *   Outcome is 0 or 1 with 50% probability each.

*   **Example 4b: Measurement in X-basis $\{|+⟩, |-⟩\}$**
    *   Probability of outcome '+': $P(+) = |⟨+|ψ⟩|^2$.
        1.  Calculate $⟨+|ψ⟩$:
            $⟨+| = \frac{1}{\sqrt{2}}(⟨0| + ⟨1|)$.
            $⟨+|ψ⟩ = \frac{1}{\sqrt{2}}(⟨0| + ⟨1|)(\frac{1+i}{2}|0⟩ + \frac{1-i}{2}|1⟩)$
            $= \frac{1}{\sqrt{2}} [ ⟨0|(\dots) + ⟨1|(\dots) ]$
            $= \frac{1}{\sqrt{2}} [ (\frac{1+i}{2}⟨0|0⟩ + \frac{1-i}{2}⟨0|1⟩) + (\frac{1+i}{2}⟨1|0⟩ + \frac{1-i}{2}⟨1|1⟩) ]$
            $= \frac{1}{\sqrt{2}} [ (\frac{1+i}{2} \cdot 1 + 0) + (0 + \frac{1-i}{2} \cdot 1) ]$
            $= \frac{1}{\sqrt{2}} [\frac{1+i}{2} + \frac{1-i}{2}] = \frac{1}{\sqrt{2}} [\frac{1+i+1-i}{2}] = \frac{1}{\sqrt{2}} [\frac{2}{2}] = \frac{1}{\sqrt{2}}$.
        2.  Calculate probability: $P(+) = |1/\sqrt{2}|^2 = 1/2$.
    *   Probability of outcome '-': $P(-) = |⟨-|ψ⟩|^2$.
        1.  Calculate $⟨-|ψ⟩$:
            $⟨-| = \frac{1}{\sqrt{2}}(⟨0| - ⟨1|)$.
            $⟨-|ψ⟩ = \frac{1}{\sqrt{2}}(⟨0| - ⟨1|)(\frac{1+i}{2}|0⟩ + \frac{1-i}{2}|1⟩)$
            $= \frac{1}{\sqrt{2}} [ ⟨0|(\dots) - ⟨1|(\dots) ]$
            $= \frac{1}{\sqrt{2}} [ (\frac{1+i}{2}) - (\frac{1-i}{2}) ]$
            $= \frac{1}{\sqrt{2}} [\frac{1+i - (1-i)}{2}] = \frac{1}{\sqrt{2}} [\frac{1+i-1+i}{2}] = \frac{1}{\sqrt{2}} [\frac{2i}{2}] = \frac{i}{\sqrt{2}}$.
        2.  Calculate probability: $P(-) = |i/\sqrt{2}|^2 = \frac{|i|^2}{|\sqrt{2}|^2} = \frac{1^2}{2} = 1/2$.
    *   Check: $P(+) + P(-) = 1/2 + 1/2 = 1$. Outcome is '+' or '-' with 50% probability each.

### F. The Bloch Sphere: A Qubit's Globe

This is a geometric visualization for the state of a **single qubit**. It maps the 2D complex state space onto the surface of a 3D real sphere.

#### 1. Parameterizing a Qubit State

Any normalized single-qubit state $|ψ⟩ = α|0⟩ + β|1⟩$ can be written, up to an unobservable *global phase*, using two real angles $θ$ and $φ$:
$$
|ψ⟩ = \cos(\theta/2)|0⟩ + e^{i\phi}\sin(\theta/2)|1⟩
$$
*   $α = \cos(\theta/2)$
*   $β = e^{i\phi}\sin(\theta/2)$
*   Check normalization: $|α|^2+|β|^2 = \cos^2(\theta/2) + |e^{i\phi}|^2\sin^2(\theta/2) = \cos^2(\theta/2) + 1 \cdot \sin^2(\theta/2) = 1$. It works!
*   **Angles:**
    *   $θ \in [0, π]$ is the **polar angle** from the +Z axis.
    *   $φ \in [0, 2π)$ is the **azimuthal angle** from the +X axis in the XY plane. $e^{i\phi}$ captures the *relative phase* between the $|0⟩$ and $|1⟩$ components.

#### 2. Mapping to the Sphere

The state $|ψ⟩$ defined by $(\theta, \phi)$ corresponds to a point on the surface of a unit sphere whose Cartesian coordinates $(x, y, z)$ define the **Bloch vector** $\vec{P}$:
$$
x = \sin\theta \cos\phi
$$
$$
y = \sin\theta \sin\phi
$$
$$
z = \cos\theta
$$
*   This is the standard spherical-to-Cartesian coordinate transformation.
*   The length of the Bloch vector is $x^2+y^2+z^2 = \sin^2\theta\cos^2\phi + \sin^2\theta\sin^2\phi + \cos^2\theta = \sin^2\theta(\cos^2\phi+\sin^2\phi) + \cos^2\theta = \sin^2\theta(1) + \cos^2\theta = 1$. All valid pure states lie *on the surface* of the sphere.

#### 3. Why $\theta/2$? The Geometry of Probability

The mapping uses $\theta/2$ in the state vector $|ψ⟩ = \cos(\theta/2)|0⟩ + \dots$ but $\theta$ in the Bloch vector coordinates $z = \cos\theta$. Why?

*   **Probability Connection:** The probability of measuring $|0⟩$ is $P(0) = |α|^2 = \cos^2(\theta/2)$. Using the trig identity $\cos^2(A) = (1+\cos(2A))/2$, we get:
    $$
    P(0) = \frac{1+\cos\theta}{2} = \frac{1+z}{2}
    $$
    Similarly, $P(1) = |β|^2 = \sin^2(\theta/2) = (1-\cos\theta)/2 = (1-z)/2$. The probabilities depend linearly on the $z$-coordinate (projection onto the Z-axis). The range $z \in [-1, 1]$ correctly maps to $P(0) \in [0, 1]$.
*   **Orthogonality:** This factor of 2 in the angle ensures that orthogonal states are **antipodal** (diametrically opposite, $180^\circ$ apart) on the Bloch sphere. For $|0⟩$, $\theta=0$; for $|1⟩$, $\theta=\pi$. The angle between them on the sphere is $\pi$. For $|+⟩$, $\theta=\pi/2, \phi=0$; for $|-⟩$, $\theta=\pi/2, \phi=\pi$. They are opposite points on the equator. Antipodal points represent maximally distinguishable states.

#### 4. Visualizing Key States

Let's find $(\theta, \phi)$ and the Bloch vector $(x, y, z)$ for our key states:

*   $|0⟩$: $α=1, β=0$. $\cos(\theta/2)=1 \implies \theta/2=0 \implies \theta=0$. $φ$ is undefined/irrelevant.
    $z = \cos(0) = 1$. $x=0, y=0$. Vector $(0, 0, 1)$ - **North Pole**.
*   $|1⟩$: $α=0, β=1$. $\cos(\theta/2)=0 \implies \theta/2=\pi/2 \implies \theta=\pi$. We need $e^{i\phi}\sin(\pi/2)=1$, so $e^{i\phi}(1)=1 \implies \phi=0$.
    $z = \cos(\pi) = -1$. $x=0, y=0$. Vector $(0, 0, -1)$ - **South Pole**.
*   $|+⟩ = \frac{1}{\sqrt{2}}|0⟩ + \frac{1}{\sqrt{2}}|1⟩$: $α=1/\sqrt{2}, β=1/\sqrt{2}$.
    $\cos(\theta/2)=1/\sqrt{2} \implies \theta/2=\pi/4 \implies \theta=\pi/2$.
    $e^{i\phi}\sin(\pi/4)=1/\sqrt{2} \implies e^{i\phi}(1/\sqrt{2})=1/\sqrt{2} \implies e^{i\phi}=1 \implies \phi=0$.
    $z = \cos(\pi/2)=0$. $x = \sin(\pi/2)\cos(0)=1\cdot1=1$. $y = \sin(\pi/2)\sin(0)=1\cdot0=0$. Vector $(1, 0, 0)$ - **+X axis**.
*   $|-⟩ = \frac{1}{\sqrt{2}}|0⟩ - \frac{1}{\sqrt{2}}|1⟩$: $α=1/\sqrt{2}, β=-1/\sqrt{2}$.
    $\cos(\theta/2)=1/\sqrt{2} \implies \theta=\pi/2$.
    $e^{i\phi}\sin(\pi/4)=-1/\sqrt{2} \implies e^{i\phi}(1/\sqrt{2})=-1/\sqrt{2} \implies e^{i\phi}=-1 \implies \phi=\pi$.
    $z = \cos(\pi/2)=0$. $x = \sin(\pi/2)\cos(\pi)=1\cdot(-1)=-1$. $y = \sin(\pi/2)\sin(\pi)=1\cdot0=0$. Vector $(-1, 0, 0)$ - **-X axis**.
*   $|+i⟩ = \frac{1}{\sqrt{2}}|0⟩ + \frac{i}{\sqrt{2}}|1⟩$: $α=1/\sqrt{2}, β=i/\sqrt{2}$.
    $\cos(\theta/2)=1/\sqrt{2} \implies \theta=\pi/2$.
    $e^{i\phi}\sin(\pi/4)=i/\sqrt{2} \implies e^{i\phi}(1/\sqrt{2})=i/\sqrt{2} \implies e^{i\phi}=i \implies \phi=\pi/2$.
    $z = \cos(\pi/2)=0$. $x = \sin(\pi/2)\cos(\pi/2)=1\cdot0=0$. $y = \sin(\pi/2)\sin(\pi/2)=1\cdot1=1$. Vector $(0, 1, 0)$ - **+Y axis**.
*   $|-i⟩ = \frac{1}{\sqrt{2}}|0⟩ - \frac{i}{\sqrt{2}}|1⟩$: $α=1/\sqrt{2}, β=-i/\sqrt{2}$.
    $\cos(\theta/2)=1/\sqrt{2} \implies \theta=\pi/2$.
    $e^{i\phi}\sin(\pi/4)=-i/\sqrt{2} \implies e^{i\phi}(1/\sqrt{2})=-i/\sqrt{2} \implies e^{i\phi}=-i \implies \phi=3\pi/2$.
    $z = \cos(\pi/2)=0$. $x = \sin(\pi/2)\cos(3\pi/2)=1\cdot0=0$. $y = \sin(\pi/2)\sin(3\pi/2)=1\cdot(-1)=-1$. Vector $(0, -1, 0)$ - **-Y axis**.

*   **Diagram:**
    <p align="center">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Bloch_sphere.svg/330px-Bloch_sphere.svg.png" alt="Bloch Sphere Diagram showing key states">
    <br>
    <em>Source: <a href="https://en.wikipedia.org/wiki/Bloch_sphere">Wikipedia</a></em>
    </p>

---

## II. Quantum Circuits: Choreographing Qubits

### A. The Circuit Model: A Quantum Flowchart

Quantum algorithms are typically described using the **circuit model**, which provides a visual language for the sequence of quantum operations.

```mermaid
graph LR
    subgraph Quantum Computer
        direction LR
        Input[Initial State |0⟩...|0⟩] -- Quantum Gates --> EvolvedState[|ψ_final⟩] -- Measurement --> Output[Classical Bits 011..0]
    end
```

*   **Components:**
    *   **Wires:** Horizontal lines represent individual qubits. Time flows from left to right along the wire. A wire carries the qubit's quantum state.
    *   **Gates:** Boxes or symbols placed on one or more wires represent **quantum gates**. These are the operations performed on the qubits.
    *   **Initialization:** Circuits usually start with qubits initialized to a specific state, typically $|0⟩$.
    *   **Measurement:** A special symbol (often resembling a gauge meter) at the end of a wire indicates a measurement in a specified basis (usually Z-basis), yielding a classical bit output.

<p align="center">
<img src="https://qiskit.org/textbook/ch-algorithms/images/teleportation_circuit_steps_1.png" width="400" alt="Simple Quantum Circuit Example">
<br>
<em>Example of a simple quantum circuit structure (from Qiskit textbook) showing initialization, gates (H, CNOT), and measurement.</em>
</p>

### B. Single-Qubit Gates: Manipulating Individual Qubits

These gates act on a single qubit, modifying its state $|ψ⟩ = α|0⟩ + β|1⟩$.

#### 1. The Need for Unitarity (Reversibility & Normalization)

*   Quantum mechanics dictates that the evolution of a closed quantum system must be **unitary**. Mathematically, a gate represented by matrix $U$ is unitary if its Hermitian conjugate (adjoint) $U^†$ is also its inverse:
    $$
    U^† U = U U^† = I \quad (\text{where } I \text{ is the identity matrix})
    $$
*   **Why Unitary?**
    1.  **Preserves Normalization:** Unitary operations preserve the inner product between states, which means they preserve the norm (length) of state vectors. If $⟨ψ|ψ⟩=1$, then $⟨ψ'|ψ'⟩ = ⟨Uψ|Uψ⟩ = ⟨ψ|U^†U|ψ⟩ = ⟨ψ|I|ψ⟩ = ⟨ψ|ψ⟩ = 1$. The total probability remains 1.
    2.  **Reversibility:** Unitary operations are always reversible. If $U$ represents a gate, its inverse operation is simply $U^†$. This reflects the reversibility of fundamental quantum dynamics. This contrasts with many classical gates (like AND) which are irreversible (lose information).

#### 2. Pauli Gates (X, Y, Z): Fundamental Flips and Phases

These are three crucial Hermitian and Unitary gates ($U=U^†$ and $U^2=I$).

*   **Pauli-X Gate (X, $\sigma_x$, NOT):**
    *   Action: Flips $|0⟩ \leftrightarrow |1⟩$. The quantum equivalent of the classical NOT gate.
    *   Matrix: $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
    *   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/x.png" alt="X Gate Symbol" height="24" style="vertical-align: middle;">
    *   Action on Basis States:
        $X|0⟩ = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix} = |1⟩$
        $X|1⟩ = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} = |0⟩$
    *   Action on General State $|ψ⟩ = α|0⟩ + β|1⟩$:
        $X|ψ⟩ = X(α|0⟩ + β|1⟩) = α(X|0⟩) + β(X|1⟩) = α|1⟩ + β|0⟩ = \begin{pmatrix} β \\ α \end{pmatrix}$. (Swaps amplitudes).
    *   Bloch Rotation: $180^\circ$ rotation around the X-axis.

*   **Pauli-Y Gate (Y, $\sigma_y$):**
    *   Action: Flips state and applies phases: $|0⟩ \rightarrow i|1⟩$, $|1⟩ \rightarrow -i|0⟩$.
    *   Matrix: $Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}$
    *   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/y.png" alt="Y Gate Symbol" height="24" style="vertical-align: middle;">
    *   Action on Basis States:
        $Y|0⟩ = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ i \end{pmatrix} = i|1⟩$
        $Y|1⟩ = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} -i \\ 0 \end{pmatrix} = -i|0⟩$
    *   Action on General State $|ψ⟩ = α|0⟩ + β|1⟩$:
        $Y|ψ⟩ = Y(α|0⟩ + β|1⟩) = α(Y|0⟩) + β(Y|1⟩) = α(i|1⟩) + β(-i|0⟩) = -iβ|0⟩ + iα|1⟩ = \begin{pmatrix} -iβ \\ iα \end{pmatrix}$.
    *   Bloch Rotation: $180^\circ$ rotation around the Y-axis.

*   **Pauli-Z Gate (Z, $\sigma_z$, Phase Flip):**
    *   Action: Leaves $|0⟩$ unchanged, flips the phase of $|1⟩$: $|0⟩ \rightarrow |0⟩$, $|1⟩ \rightarrow -|1⟩$.
    *   Matrix: $Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$
    *   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/z.png" alt="Z Gate Symbol" height="24" style="vertical-align: middle;">
    *   Action on Basis States:
        $Z|0⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} = |0⟩$
        $Z|1⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ -1 \end{pmatrix} = -|1⟩$
    *   Action on General State $|ψ⟩ = α|0⟩ + β|1⟩$:
        $Z|ψ⟩ = Z(α|0⟩ + β|1⟩) = α(Z|0⟩) + β(Z|1⟩) = α|0⟩ + β(-|1⟩) = α|0⟩ - β|1⟩ = \begin{pmatrix} α \\ -β \end{pmatrix}$.
    *   Bloch Rotation: $180^\circ$ rotation around the Z-axis.

#### 3. Hadamard Gate (H): The Superposition Engine

*   Action: Creates equal superposition states from basis states. Maps Z-basis to X-basis and vice-versa. Essential for many algorithms.
*   Matrix: $H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$
*   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/h.png" alt="H Gate Symbol" height="24" style="vertical-align: middle;">
*   Action on Basis States:
    $H|0⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}(|0⟩ + |1⟩) = |+⟩$
    $H|1⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = \frac{1}{\sqrt{2}}(|0⟩ - |1⟩) = |-⟩$
*   Action on General State $|ψ⟩ = α|0⟩ + β|1⟩$:
    $H|ψ⟩ = H(α|0⟩ + β|1⟩) = α(H|0⟩) + β(H|1⟩) = α|+⟩ + β|-⟩ = α\frac{1}{\sqrt{2}}(|0⟩+|1⟩) + β\frac{1}{\sqrt{2}}(|0⟩-|1⟩) = \frac{α+β}{\sqrt{2}}|0⟩ + \frac{α-β}{\sqrt{2}}|1⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} α+β \\ α-β \end{pmatrix}$.
*   Bloch Rotation: $180^\circ$ rotation around the axis $(1,0,1)/\sqrt{2}$ (diagonal between +X and +Z).
*   Property: $H$ is its own inverse: $H H = I$. Applying it twice does nothing.
    $H^2 = (\frac{1}{\sqrt{2}})^2 \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} = \frac{1}{2} \begin{pmatrix} (1)(1)+(1)(1) & (1)(1)+(1)(-1) \\ (1)(1)+(-1)(1) & (1)(1)+(-1)(-1) \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$.

#### 4. Phase Gates (S, T): Fine-Tuning Phases

These gates modify the relative phase $\phi$. They are *not* Hermitian but *are* Unitary.

*   **S Gate (Phase Gate, $\sqrt{Z}$):**
    *   Action: Applies a phase $i = e^{i\pi/2}$ to $|1⟩$. $|0⟩ \rightarrow |0⟩$, $|1⟩ \rightarrow i|1⟩$.
    *   Matrix: $S = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}$
    *   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/s.png" alt="S Gate Symbol" height="24" style="vertical-align: middle;">
    *   Action on Basis States: $S|0⟩=|0⟩$, $S|1⟩=i|1⟩$.
    *   Action on General State: $S|ψ⟩ = α|0⟩ + iβ|1⟩ = \begin{pmatrix} α \\ iβ \end{pmatrix}$.
    *   Bloch Rotation: $90^\circ$ rotation around the Z-axis.
    *   Property: $S S = Z$.
        $S^2 = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & i^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} = Z$.
    *   **S† Gate (S-dagger):** Inverse of S. Applies phase $-i=e^{-i\pi/2}$. $S^† = \begin{pmatrix} 1 & 0 \\ 0 & -i \end{pmatrix}$. Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/sdg.png" alt="Sdg Gate Symbol" height="24" style="vertical-align: middle;">. $S S^† = I$.

*   **T Gate ($\pi/8$ Gate, $\sqrt{S}$):**
    *   Action: Applies phase $e^{i\pi/4}$ to $|1⟩$. $|0⟩ \rightarrow |0⟩$, $|1⟩ \rightarrow e^{i\pi/4}|1⟩$.
    *   Matrix: $T = \begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/4} \end{pmatrix}$, where $e^{i\pi/4} = \cos(\pi/4) + i\sin(\pi/4) = \frac{1+i}{\sqrt{2}}$.
    *   Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/t.png" alt="T Gate Symbol" height="24" style="vertical-align: middle;">
    *   Action on Basis States: $T|0⟩=|0⟩$, $T|1⟩=e^{i\pi/4}|1⟩$.
    *   Action on General State: $T|ψ⟩ = α|0⟩ + e^{i\pi/4}β|1⟩ = \begin{pmatrix} α \\ e^{i\pi/4}β \end{pmatrix}$.
    *   Bloch Rotation: $45^\circ$ rotation around the Z-axis.
    *   Property: $T T = S$.
        $T^2 = \begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/4} \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/4} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & (e^{i\pi/4})^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & e^{i\pi/2} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix} = S$.
    *   **T† Gate (T-dagger):** Inverse of T. Applies phase $e^{-i\pi/4}$. $T^† = \begin{pmatrix} 1 & 0 \\ 0 & e^{-i\pi/4} \end{pmatrix}$. Circuit Symbol: <img src="https://quantum-computing.ibm.com/composer/docs/images/gates/tdg.png" alt="Tdg Gate Symbol" height="24" style="vertical-align: middle;">.

#### 5. Gates as Bloch Sphere Rotations

*   Every single-qubit gate $U$ corresponds to a rotation of the Bloch sphere. States $|ψ⟩$ are points on the surface, and applying gate $U$ moves the point $|ψ⟩$ to the point $U|ψ⟩$.
*   **Pauli Gates (X, Y, Z):** Rotations by $π$ (180°) around the X, Y, Z axes respectively.
*   **H Gate:** Rotation by $π$ around the axis halfway between +X and +Z.
*   **S Gate:** Rotation by $π/2$ (90°) around the Z-axis.
*   **T Gate:** Rotation by $π/4$ (45°) around the Z-axis.
*   Visualizing sequences of gates becomes visualizing sequences of rotations.

### C. Multi-Qubit Systems: Scaling Up with Tensor Products

How do we describe the state of multiple qubits together?

#### 1. Why Tensor Products? Combining Spaces

*   If one system A can be in states described by vectors in Hilbert space $H_A$ (dimension $d_A$) and another independent system B is in $H_B$ (dimension $d_B$), the combined system AB is described by vectors in the **tensor product space** $H_{AB} = H_A \otimes H_B$.
*   The dimension of the combined space is the *product* of the individual dimensions: $dim(H_{AB}) = d_A \times d_B$.
*   For N qubits, each qubit is in $H_i \cong ℂ^2$. The total space is $H_{total} = H_1 \otimes H_2 \otimes \dots \otimes H_N \cong ℂ^{2^N}$. The dimension grows exponentially!

#### 2. Constructing Multi-Qubit Basis States (Vectors)

*   A basis for the tensor product space $H_A \otimes H_B$ is formed by taking all possible tensor products of basis vectors from $H_A$ and $H_B$.
*   For two qubits ($H_1 \otimes H_2$), the computational basis is $\{ |0⟩_1 \otimes |0⟩_2, |0⟩_1 \otimes |1⟩_2, |1⟩_1 \otimes |0⟩_2, |1⟩_1 \otimes |1⟩_2 \}$. We abbreviate this as $\{ |00⟩, |01⟩, |10⟩, |11⟩ \}$.
*   **Vector Calculation (Kronecker Product):** If $|a⟩ = \begin{pmatrix} a_1 \\ a_2 \end{pmatrix}$ and $|b⟩ = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$, then
    $$
    |a⟩ \otimes |b⟩ = \begin{pmatrix} a_1 |b⟩ \\ a_2 |b⟩ \end{pmatrix} = \begin{pmatrix} a_1 \begin{pmatrix} b_1 \\ b_2 \end{pmatrix} \\ a_2 \begin{pmatrix} b_1 \\ b_2 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} a_1 b_1 \\ a_1 b_2 \\ a_2 b_1 \\ a_2 b_2 \end{pmatrix}
    $$
*   **Deriving the 2-Qubit Basis Vectors:**
    *   $|00⟩ = |0⟩ \otimes |0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \begin{pmatrix} 1 \\ 0 \end{pmatrix} \\ 0 \begin{pmatrix} 1 \\ 0 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}$
    *   $|01⟩ = |0⟩ \otimes |1⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \begin{pmatrix} 0 \\ 1 \end{pmatrix} \\ 0 \begin{pmatrix} 0 \\ 1 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}$
    *   $|10⟩ = |1⟩ \otimes |0⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \begin{pmatrix} 1 \\ 0 \end{pmatrix} \\ 1 \begin{pmatrix} 1 \\ 0 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}$
    *   $|11⟩ = |1⟩ \otimes |1⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \otimes \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \begin{pmatrix} 0 \\ 1 \end{pmatrix} \\ 1 \begin{pmatrix} 0 \\ 1 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}$
    These four vectors form the standard orthonormal basis for the 4D space of two qubits.

#### 3. General Multi-Qubit States

*   A general state of N qubits is a superposition of all $2^N$ basis states:
    $$
    |ψ⟩ = \sum_{x \in \{0,1\}^N} α_x |x⟩
    $$
    where $|x⟩ = |x_1 x_2 ... x_N⟩$ and $\sum |α_x|^2 = 1$.
*   For two qubits:
    $$
    |ψ⟩ = α_{00}|00⟩ + α_{01}|01⟩ + α_{10}|10⟩ + α_{11}|11⟩ = \begin{pmatrix} α_{00} \\ α_{01} \\ α_{10} \\ α_{11} \end{pmatrix}
    $$
    where $|α_{00}|^2 + |α_{01}|^2 + |α_{10}|^2 + |α_{11}|^2 = 1$.

#### 4. Separable vs. Entangled States Defined

*   **Separable (Product) State:** A multi-qubit state that *can* be written as a tensor product of individual qubit states.
    *   Example: $|ψ⟩ = |0⟩ \otimes |+⟩ = |0⟩ \otimes \frac{1}{\sqrt{2}}(|0⟩+|1⟩) = \frac{1}{\sqrt{2}}|00⟩ + \frac{1}{\sqrt{2}}|01⟩$.
    *   Vector: $|0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $|+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}$.
        $|0⟩ \otimes |+⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \otimes \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \begin{pmatrix} 1 \\ 1 \end{pmatrix} \\ 0 \begin{pmatrix} 1 \\ 1 \end{pmatrix} \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \\ 0 \\ 0 \end{pmatrix}$. This matches the Dirac notation ($\alpha_{00}=1/\sqrt{2}, \alpha_{01}=1/\sqrt{2}, \alpha_{10}=0, \alpha_{11}=0$).
    *   In separable states, measurements on individual qubits are independent.
*   **Entangled State:** A multi-qubit state that *cannot* be factored into a tensor product of individual qubit states.
    *   Example: $|\Phi^+⟩ = \frac{1}{\sqrt{2}}(|00⟩ + |11⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix}$. You cannot find single-qubit states $|a⟩=\begin{pmatrix}a_1\\a_2\end{pmatrix}$ and $|b⟩=\begin{pmatrix}b_1\\b_2\end{pmatrix}$ such that $|a⟩⊗|b⟩ = \begin{pmatrix} a_1b_1 \\ a_1b_2 \\ a_2b_1 \\ a_2b_2 \end{pmatrix}$ equals $\frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix}$. (Requires $a_1b_2=0$ and $a_2b_1=0$, implying either $a_1=0$ or $b_2=0$, and either $a_2=0$ or $b_1=0$. But if $a_1=0$, then $a_1b_1=0 \neq 1/\sqrt{2}$. If $b_2=0$, then $a_2b_2=0$ okay, need $a_2b_1=0$. If $b_1=0$, then $a_1b_1=0 \neq 1/\sqrt{2}$. If $a_2=0$, then $a_2b_2=0$ okay, need $a_1b_2=0$. If $b_2=0$, contradiction. If $a_1=0$, contradiction. Impossible.)
    *   Entangled states exhibit correlations that cannot be explained classically.

### D. Multi-Qubit Gates: Qubit Interactions

Gates acting on two or more qubits are necessary to create entanglement and perform complex logic.

#### 1. The Controlled-NOT (CNOT) Gate: Conditional Logic

*   **The Workhorse:** The most fundamental and widely used two-qubit gate.
*   **Action:** Takes two inputs: a **control** qubit and a **target** qubit. It applies an X (NOT) gate to the target *if and only if* the control is $|1⟩$.
*   **Symbol:** ● on control wire, ⊕ on target wire.
    <p align="center">
    <img src="https://qiskit.org/textbook/ch-basics/images/cx.png" alt="CNOT Gate Symbol" width="150">
    <br>
    <em>(Image: qiskit.org/textbook) - Top is control, bottom is target.</em>
    </p>
*   **Truth Table (Basis states):** $|Control, Target⟩ \rightarrow |Control, Target \oplus Control⟩$
    *   $|00⟩ \rightarrow |0, 0\oplus0⟩ = |00⟩$
    *   $|01⟩ \rightarrow |0, 1\oplus0⟩ = |01⟩$
    *   $|10⟩ \rightarrow |1, 0\oplus1⟩ = |11⟩$
    *   $|11⟩ \rightarrow |1, 1\oplus1⟩ = |10⟩$ (Note: $\oplus$ is addition modulo 2, so $1\oplus1=0$)
*   **Matrix ($4 \times 4$, basis $|00⟩, |01⟩, |10⟩, |11⟩$):** Reflects the truth table: maps input basis state (column) to output basis state (row with the 1).
    $$
    \text{CNOT} =
    \begin{pmatrix}
    % Output states down ->
    % Input states across ->  00  01  10  11
    1 & 0 & 0 & 0 \\ % 00 <- 00
    0 & 1 & 0 & 0 \\ % 01 <- 01
    0 & 0 & 0 & 1 \\ % 10 <- 11
    0 & 0 & 1 & 0    % 11 <- 10
    \end{pmatrix}
    $$
*   **Verification with Matrix Multiplication:** Let's check CNOT$|10⟩ = |11⟩$.
    $|10⟩ = \begin{pmatrix} 0\\0\\1\\0 \end{pmatrix}$.
    $$
    \text{CNOT}|10⟩ = \begin{pmatrix} 1&0&0&0 \\ 0&1&0&0 \\ 0&0&0&1 \\ 0&0&1&0 \end{pmatrix} \begin{pmatrix} 0\\0\\1\\0 \end{pmatrix} = \begin{pmatrix} (1)(0)+(0)(0)+(0)(1)+(0)(0) \\ (0)(0)+(1)(0)+(0)(1)+(0)(0) \\ (0)(0)+(0)(0)+(0)(1)+(1)(0) \\ (0)(0)+(0)(0)+(1)(1)+(0)(0) \end{pmatrix} = \begin{pmatrix} 0\\0\\0\\1 \end{pmatrix}
    $$
    The result $\begin{pmatrix} 0\\0\\0\\1 \end{pmatrix}$ is indeed the vector for $|11⟩$.
*   **Entanglement Creation:** As shown previously, applying CNOT to $|+0⟩ = \frac{1}{\sqrt{2}}(|00⟩+|10⟩)$ yields the entangled state $|\Phi^+⟩ = \frac{1}{\sqrt{2}}(|00⟩+|11⟩)$. This is a standard way to generate entanglement.

#### 2. Other Controlled Gates (Conceptual)

*   The CNOT principle can be generalized. A **Controlled-U** gate applies a single-qubit gate $U$ to the target qubit if the control qubit is $|1⟩$, and does nothing (applies $I$) if the control is $|0⟩$.
*   Examples include Controlled-Z (CZ), Controlled-Phase (CPhase), Controlled-H (CH), etc. The Toffoli gate (CCNOT) has two control qubits and one target.

<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Controlled-U_gate.svg/150px-Controlled-U_gate.svg.png" alt="Controlled-U Gate Symbol" >
<br>
<em>General symbol for a Controlled-U gate.</em>
</p>

### E. Universality: Building Any Computation

*   **Definition:** A set of quantum gates is **universal** if any possible quantum computation (i.e., any $N$-qubit unitary transformation) can be implemented (or approximated arbitrarily closely) using only gates from that set.
*   **Significance:** We don't need to physically build every conceivable gate. A small universal set is sufficient.
*   **Common Universal Sets:**
    *   {All single-qubit gates, CNOT}
    *   {Hadamard, S, T, CNOT} (A common discrete set for fault-tolerant designs)
    *   {Hadamard, T, CNOT} (T provides rotation by an irrational fraction of $2\pi$, allowing arbitrary approximations).

---

## III. Entanglement: The Spooky Connection

Entanglement is a central concept in quantum mechanics, describing profound correlations between quantum systems.

### A. Defining Entanglement (Revisited)

*   A multi-qubit state is **entangled** if it *cannot* be described independently for each qubit; it cannot be written as a tensor product $|ψ⟩_A \otimes |χ⟩_B \otimes \dots$.
*   The qubits in an entangled state are perfectly correlated (or anti-correlated) in certain measurement bases, regardless of their separation. Changes to one instantaneously affect the potential measurement outcomes of the others.

### B. Bell States: The VIPs of Entanglement

The four Bell states are the simplest examples of maximally entangled two-qubit states.

#### 1. The Four States

$$
|\Phi^+⟩ = \frac{1}{\sqrt{2}} (|00⟩ + |11⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix} \quad (\text{Correlated: } 00 \text{ or } 11)
$$
$$
|\Phi^-⟩ = \frac{1}{\sqrt{2}} (|00⟩ - |11⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ -1 \end{pmatrix} \quad (\text{Correlated with phase: } 00 \text{ or } -11)
$$
$$
|\Psi^+⟩ = \frac{1}{\sqrt{2}} (|01⟩ + |10⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 0 \\ 1 \\ 1 \\ 0 \end{pmatrix} \quad (\text{Anti-correlated: } 01 \text{ or } 10)
$$
$$
|\Psi^-⟩ = \frac{1}{\sqrt{2}} (|01⟩ - |10⟩) = \frac{1}{\sqrt{2}}\begin{pmatrix} 0 \\ 1 \\ -1 \\ 0 \end{pmatrix} \quad (\text{Anti-correlated with phase: } 01 \text{ or } -10)
$$
They form an orthonormal basis for the 2-qubit space.

#### 2. Creating Bell States: A Step-by-Step Circuit Derivation

The standard circuit uses H on the first qubit, then CNOT with qubit 1 as control, qubit 2 as target. Let's derive the creation of $|\Phi^+⟩$ from $|00⟩$.

1.  **Initial State:** $|ψ_0⟩ = |00⟩ = |0⟩ \otimes |0⟩ = \begin{pmatrix} 1\\0\\0\\0 \end{pmatrix}$.
2.  **Apply H to Qubit 1:** The operator is $H \otimes I$.
    $H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$, $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$.
    $H \otimes I = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \otimes I & 1 \otimes I \\ 1 \otimes I & -1 \otimes I \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} I & I \\ I & -I \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1&0&1&0 \\ 0&1&0&1 \\ 1&0&-1&0 \\ 0&1&0&-1 \end{pmatrix}$.
    $|ψ_1⟩ = (H \otimes I)|ψ_0⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1&0&1&0 \\ 0&1&0&1 \\ 1&0&-1&0 \\ 0&1&0&-1 \end{pmatrix} \begin{pmatrix} 1\\0\\0\\0 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1\\0\\1\\0 \end{pmatrix}$.
    This vector corresponds to $\frac{1}{\sqrt{2}}(|00⟩ + |10⟩)$, which is $|+⟩ \otimes |0⟩$.
3.  **Apply CNOT (Control=1, Target=2):**
    $\text{CNOT} = \begin{pmatrix} 1&0&0&0 \\ 0&1&0&0 \\ 0&0&0&1 \\ 0&0&1&0 \end{pmatrix}$.
    $|ψ_2⟩ = \text{CNOT}|ψ_1⟩ = \begin{pmatrix} 1&0&0&0 \\ 0&1&0&0 \\ 0&0&0&1 \\ 0&0&1&0 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1\\0\\1\\0 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1\\0\\0\\1 \end{pmatrix}$.
    The final state vector $\frac{1}{\sqrt{2}}\begin{pmatrix} 1\\0\\0\\1 \end{pmatrix}$ corresponds exactly to $|\Phi^+⟩ = \frac{1}{\sqrt{2}}(|00⟩ + |11⟩)$.

#### 3. Bell Measurement: Identifying Entangled States

*   This projects a 2-qubit state onto the Bell basis $\{ |\Phi^+⟩, |\Phi^-⟩, |\Psi^+⟩, |\Psi^-⟩ \}$.
*   The circuit is the reverse of creation: CNOT (1->2), then H on qubit 1, then measure both qubits in the Z-basis.
*   The pair of classical bits obtained `m1 m2` indicates which Bell state was measured. (The exact mapping depends on convention, e.g., `00` -> $\Phi^+$, `01` -> $\Psi^+$, `10` -> $\Phi^-$, `11` -> $\Psi^-$ is one possibility).

### C. Quantum Teleportation: Beam Me Up, Scotty?

This protocol demonstrates how to transmit an *unknown* quantum state from Alice to Bob using shared entanglement and classical communication.

#### 1. The Setup and The Goal

*   **Alice:** Has qubit S in an unknown state $|φ⟩_S = α|0⟩_S + β|1⟩_S$. She doesn't know $α$ or $β$.
*   **Bob:** Is physically separated from Alice.
*   **Entanglement Resource:** Alice and Bob share an entangled pair of qubits, A and B, typically in the state $|\Phi^+⟩_{AB} = \frac{1}{\sqrt{2}}(|00⟩_{AB} + |11⟩_{AB})$. Alice holds A, Bob holds B.
*   **Classical Channel:** Alice can send two classical bits to Bob.
*   **Goal:** Make Bob's qubit B end up in the state $|φ⟩$, identical to Alice's original $|φ⟩_S$.

#### 2. The Protocol Step-by-Step (with Derivations)

1.  **Initial 3-Qubit State:** The state of the combined system (S, A, B) is:
    $$
    |\text{initial}⟩ = |φ⟩_S \otimes |\Phi^+⟩_{AB} = (α|0⟩_S + β|1⟩_S) \otimes \frac{1}{\sqrt{2}}(|00⟩_{AB} + |11⟩_{AB})
    $$
    Expanding this gives:
    $$
    |\text{initial}⟩ = \frac{α}{\sqrt{2}}|000⟩ + \frac{α}{\sqrt{2}}|011⟩ + \frac{β}{\sqrt{2}}|100⟩ + \frac{β}{\sqrt{2}}|111⟩
    $$
    (Where the order is S, A, B).

2.  **Rewriting in Alice's Bell Basis (The Clever Part):** We rewrite the state by grouping Alice's qubits (S and A) and expressing their combined state using the Bell basis for SA. We use the following identities (which can be derived by expressing Bell states in the computational basis and solving for the computational states):
    *   $|00⟩_{SA} = \frac{1}{\sqrt{2}}(|\Phi^+⟩_{SA} + |\Phi^-⟩_{SA})$
    *   $|01⟩_{SA} = \frac{1}{\sqrt{2}}(|\Psi^+⟩_{SA} + |\Psi^-⟩_{SA})$
    *   $|10⟩_{SA} = \frac{1}{\sqrt{2}}(|\Psi^+⟩_{SA} - |\Psi^-⟩_{SA})$
    *   $|11⟩_{SA} = \frac{1}{\sqrt{2}}(|\Phi^+⟩_{SA} - |\Phi^-⟩_{SA})$

    Substitute these into the expanded initial state (keeping track of Bob's qubit B):
    $|\text{initial}⟩ =$
    $\frac{α}{\sqrt{2}}[\frac{1}{\sqrt{2}}(|\Phi^+⟩_{SA} + |\Phi^-⟩_{SA})] \otimes |0⟩_B$  *(from $\alpha|000⟩$)*
    $+ \frac{α}{\sqrt{2}}[\frac{1}{\sqrt{2}}(|\Psi^+⟩_{SA} + |\Psi^-⟩_{SA})] \otimes |1⟩_B$  *(from $\alpha|011⟩$ - note A is 1)*
    $+ \frac{β}{\sqrt{2}}[\frac{1}{\sqrt{2}}(|\Psi^+⟩_{SA} - |\Psi^-⟩_{SA})] \otimes |0⟩_B$  *(from $\beta|100⟩$)*
    $+ \frac{β}{\sqrt{2}}[\frac{1}{\sqrt{2}}(|\Phi^+⟩_{SA} - |\Phi^-⟩_{SA})] \otimes |1⟩_B$  *(from $\beta|111⟩$)*

    Now, collect terms based on the SA Bell state:
    $|\text{initial}⟩ = \frac{1}{2} [$
    $|\Phi^+⟩_{SA} \otimes (α|0⟩_B + β|1⟩_B)$  *(Terms with $\Phi^+$)*
    $+ |\Phi^-⟩_{SA} \otimes (α|0⟩_B - β|1⟩_B)$  *(Terms with $\Phi^-$)*
    $+ |\Psi^+⟩_{SA} \otimes (α|1⟩_B + β|0⟩_B)$  *(Terms with $\Psi^+$)*
    $+ |\Psi^-⟩_{SA} \otimes (α|1⟩_B - β|0⟩_B)$  *(Terms with $\Psi^-$)*
    $]$

    Recognize the operations on Bob's qubit relative to the target state $|φ⟩_B = α|0⟩_B + β|1⟩_B$:
    *   $α|0⟩_B + β|1⟩_B = I |φ⟩_B$
    *   $α|0⟩_B - β|1⟩_B = Z |φ⟩_B$
    *   $α|1⟩_B + β|0⟩_B = X |φ⟩_B$
    *   $α|1⟩_B - β|0⟩_B = X(α|0⟩_B - β|1⟩_B) = XZ |φ⟩_B$ (Also equals $-iY|φ⟩_B$)

    So, the state is beautifully rearranged as:
    $$
    |\text{initial}⟩ = \frac{1}{2} [ \quad |\Phi^+⟩_{SA} \otimes (I |φ⟩_B) \quad + \quad |\Phi^-⟩_{SA} \otimes (Z |φ⟩_B) \quad + \quad |\Psi^+⟩_{SA} \otimes (X |φ⟩_B) \quad + \quad |\Psi^-⟩_{SA} \otimes (XZ |φ⟩_B) \quad ]
    $$

3.  **Alice's Bell Measurement:** Alice measures her qubits S and A in the Bell basis. The outcome will be one of the four Bell states, randomly, each with probability $(1/2)^2 = 1/4$. Let her classical outcome bits be $m_1 m_2$.

4.  **Collapse:** Based on the rearranged state, if Alice measures:
    *   $|\Phi^+⟩_{SA}$ (outcome $m_1m_2=00$), Bob's state instantly becomes $I|φ⟩_B = |φ⟩_B$.
    *   $|\Phi^-⟩_{SA}$ (outcome $m_1m_2=10$), Bob's state instantly becomes $Z|φ⟩_B$.
    *   $|\Psi^+⟩_{SA}$ (outcome $m_1m_2=01$), Bob's state instantly becomes $X|φ⟩_B$.
    *   $|\Psi^-⟩_{SA}$ (outcome $m_1m_2=11$), Bob's state instantly becomes $XZ|φ⟩_B$.

5.  **Classical Communication:** Alice sends $m_1, m_2$ to Bob.

6.  **Bob's Correction:** Bob applies a recovery operation based on the bits received: $X^{m_2} Z^{m_1}$.
    *   If $00$: Apply $X^0 Z^0 = I \cdot I = I$. Bob has $|φ⟩$. Correct.
    *   If $01$: Apply $X^1 Z^0 = X \cdot I = X$. Bob has $X|φ⟩$. Apply $X$. $X(X|φ⟩) = X^2|φ⟩ = I|φ⟩ = |φ⟩$. Correct.
    *   If $10$: Apply $X^0 Z^1 = I \cdot Z = Z$. Bob has $Z|φ⟩$. Apply $Z$. $Z(Z|φ⟩) = Z^2|φ⟩ = I|φ⟩ = |φ⟩$. Correct.
    *   If $11$: Apply $X^1 Z^1 = X \cdot Z = XZ$. Bob has $XZ|φ⟩$. Apply $XZ$. $(XZ)(XZ)|φ⟩ = X(ZX)Z|φ⟩ = X(-XZ)Z|φ⟩ = -X^2Z^2|φ⟩ = -I \cdot I |φ⟩ = -|φ⟩$. Wait, there's a phase! Let's re-check the recovery $X^{m_2} Z^{m_1}$.
        If Bob receives $m_1=1, m_2=1$, his state is $XZ|φ⟩$. He applies $X^{1}Z^{1} = XZ$. Result: $XZ (XZ |φ⟩)$.
        Does $(XZ)(XZ)=I$? $XZXZ = X(iY)Z = i(XYZ) = i(iI) = -I$.
        Ah, the standard correction is $Z^{m_1} X^{m_2}$. Let's try that.
        If $11$: Apply $Z^1 X^1 = ZX$. Bob has $XZ|φ⟩$. Apply $ZX$. $ZX(XZ|φ⟩) = Z(XX)Z|φ⟩ = ZIZ|φ⟩ = Z^2|φ⟩ = I|φ⟩ = |φ⟩$. Yes, the correction $Z^{m_1} X^{m_2}$ works perfectly.

    *Result:* Bob's qubit B is now in the state $|φ⟩$, identical to Alice's original state.

#### 3. Circuit Diagram and Interpretation

<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/01/Quantum_teleportation_circuit.svg/500px-Quantum_teleportation_circuit.svg.png" alt="Quantum Teleportation Circuit">
<br>
<em>(Image: Wikimedia Commons, User: Dormouse) - The final gates on Bob's (bottom) wire are controlled by the classical bits $m_1, m_2$. The Z gate is applied if $m_1=1$, the X gate is applied if $m_2=1$. This implements the $Z^{m_1} X^{m_2}$ correction.</em>
</p>

#### 4. Crucial Caveats: No Cloning, No FTL Communication

*   **No-Cloning:** Alice's original state $|φ⟩_S$ is destroyed by her Bell measurement. Teleportation *moves* the state, it doesn't copy it.
*   **Classical Limit:** Bob needs Alice's classical bits $m_1, m_2$ (which travel no faster than light) to know which correction ($I, X, Z,$ or $ZX$) to apply. The "instantaneous" collapse on Bob's side doesn't transmit usable information faster than light.

### D. The Q-Sphere: Visualizing Many Qubits

*   **Purpose:** Visualizes the amplitudes ($α_x$) and phases of all $2^N$ computational basis states $|x⟩$ for an N-qubit state $|ψ⟩ = \sum α_x |x⟩$.
*   **Layout:** Points on a sphere correspond to basis states, arranged by Hamming weight on latitudes ($|0...0⟩$ North, $|1...1⟩$ South).
*   **Blobs:** At each point $|x⟩$:
    *   **Size** $\propto$ Probability $P(x) = |α_x|^2$.
    *   **Color** $\propto$ Phase of $α_x$.

<p align="center">
<img src="https://quantum-computing.ibm.com/docs/iqx/guide/images/q-sphere-3qubit.png" width="400" alt="Q-Sphere Example for 3 Qubits">
<br>
<em>Example Q-Sphere for a 3-qubit state from IBM Quantum documentation. Shows basis state labels and colored blobs representing amplitudes.</em>
</p>

---

## IV. Deeper Mathematical Foundations

Here we formalize the mathematical structures underpinning quantum computation.

### A. Hilbert Space: The Quantum Arena

*   **Definition:** A (complex) **Hilbert space** is the mathematical environment for quantum mechanics. It is a complete inner product space over the complex numbers.
    *   **Vector Space:** Allows addition of states (superposition) and scalar multiplication (amplitudes).
    *   **Inner Product $⟨φ|ψ⟩$:** Defines length/norm and orthogonality.
    *   **Completeness:** Ensures mathematical well-behavedness (limits exist within the space).
*   **Qubit Systems:** The state space for $N$ qubits is the $2^N$-dimensional Hilbert space $H_N \cong ℂ^{2^N}$.

### B. Inner and Outer Products: Tools for Calculation

*   **Inner Product $⟨φ|ψ⟩ = \sum_k φ_k^* ψ_k$:** A complex scalar measuring overlap/projection. Key for Born rule $P(x) = |⟨x|ψ⟩|^2$ and normalization $⟨ψ|ψ⟩ = 1$.
*   **Outer Product $|ψ⟩⟨φ|$:** An $N \times N$ matrix (operator). Key for constructing projectors $P_x = |x⟩⟨x|$ and the identity $I = \sum_i |x_i⟩⟨x_i|$.

### C. Operators, Observables, and Eigen-things

Operators act on kets to produce other kets: $A|ψ⟩ = |φ⟩$. In finite dimensions, they are matrices.

#### 1. Linear Operators

Quantum operators are linear: $A(α|ψ⟩ + β|φ⟩) = α(A|ψ⟩) + β(A|φ⟩)$.

#### 2. Hermitian Operators and Observables

*   **Observable:** A physical property that can be measured (e.g., energy, position, spin component).
*   **Hermitian Operator ($A = A^†$):** Represents an observable.
    *   **Real Eigenvalues:** The possible numerical outcomes of measuring observable $A$ are the *eigenvalues* $a_i$ of the matrix $A$. These are guaranteed to be real for Hermitian operators.
    *   **Eigenvectors $|a_i⟩$:** The states corresponding to specific outcomes ($A|a_i⟩ = a_i|a_i⟩$). Eigenvectors for distinct eigenvalues are orthogonal and form a basis for the space. Measurement collapses the state $|ψ⟩$ into one of the $|a_i⟩$.
    *   **Examples:** Pauli matrices $X, Y, Z$ are Hermitian.
        *   $Z$ has eigenvalues +1, -1 with eigenvectors $|0⟩, |1⟩$.
        *   $X$ has eigenvalues +1, -1 with eigenvectors $|+⟩, |-⟩$.
        *   $Y$ has eigenvalues +1, -1 with eigenvectors $|+i⟩, |-i⟩$.

#### 3. Unitary Operators and Evolution

*   **Evolution/Gates:** Represented by **Unitary Operators** ($U^† U = I$).
*   **Properties:** Preserve inner product, norm, and are reversible ($U^{-1} = U^†$).
*   **Connection:** Generated by Hermitian operators: $U = e^{i \gamma H}$.

### D. Expectation Values: The Average Outcome

#### 1. Definition and Calculation Methods

*   **Definition:** The average value obtained if an observable $A$ is measured many times on identical copies of state $|ψ⟩$. Denoted $⟨A⟩_ψ$ or $⟨A⟩$.
*   **Method 1 (Probabilities):** Sum of (outcome $\times$ probability):
    $$
    ⟨A⟩_ψ = \sum_i a_i P(a_i) = \sum_i a_i |⟨a_i|ψ⟩|^2
    $$
*   **Method 2 (Operator Sandwich):** Easier calculation using the operator $A$:
    $$
    ⟨A⟩_ψ = ⟨ψ| A |ψ⟩
    $$

#### 2. Deriving $⟨A⟩ = ⟨ψ|A|ψ⟩$

We use the **spectral decomposition** of a Hermitian operator $A$, which states $A = \sum_i a_i |a_i⟩⟨a_i|$ (where $|a_i⟩⟨a_i|$ is the projector onto the eigenspace for eigenvalue $a_i$).
$$
⟨ψ| A |ψ⟩ = ⟨ψ| \left( \sum_i a_i |a_i⟩⟨a_i| \right) |ψ⟩
$$
By linearity of the inner product:
$$
= \sum_i a_i ⟨ψ| a_i⟩⟨a_i |ψ⟩
$$
Since $⟨ψ|a_i⟩ = (⟨a_i|ψ⟩)^*$, we have $⟨ψ|a_i⟩⟨a_i|ψ⟩ = (⟨a_i|ψ⟩)^* (⟨a_i|ψ⟩) = |⟨a_i|ψ⟩|^2$.
$$
= \sum_i a_i |⟨a_i|ψ⟩|^2
$$
This matches Method 1.

#### 3. Examples

*   **$⟨Z⟩$ for $|ψ⟩ = |+⟩ = \frac{1}{\sqrt{2}}(|0⟩+|1⟩)$:**
    $⟨+|Z|+⟩ = ⟨+| (-|-)⟩ = 0$. (Since $Z|+⟩ = |-⟩$ and $⟨+|-⟩=0$).
    Interpretation: 50% chance of +1 (state $|0⟩$), 50% chance of -1 (state $|1⟩$). Average = 0.
*   **$⟨X⟩$ for $|ψ⟩ = |0⟩$:**
    $⟨0|X|0⟩ = ⟨0| (|1⟩) = ⟨0|1⟩ = 0$. (Since $X|0⟩ = |1⟩$).
    Interpretation: $|0⟩ = \frac{1}{\sqrt{2}}(|+⟩+|-⟩)$. 50% chance of +1 (state $|+⟩$), 50% chance of -1 (state $|-⟩$). Average = 0.
*   **$⟨Z⟩$ for $|ψ⟩ = \frac{\sqrt{3}}{2}|0⟩ + \frac{i}{2}|1⟩$:**
    $⟨ψ|Z|ψ⟩ = (\frac{\sqrt{3}}{2}⟨0| - \frac{i}{2}⟨1|) Z (\frac{\sqrt{3}}{2}|0⟩ + \frac{i}{2}|1⟩)$
    $= (\frac{\sqrt{3}}{2}⟨0| - \frac{i}{2}⟨1|) (\frac{\sqrt{3}}{2}Z|0⟩ + \frac{i}{2}Z|1⟩)$
    $= (\frac{\sqrt{3}}{2}⟨0| - \frac{i}{2}⟨1|) (\frac{\sqrt{3}}{2}|0⟩ + \frac{i}{2}(-|1⟩))$
    $= (\frac{\sqrt{3}}{2})^2 ⟨0|0⟩ - (\frac{\sqrt{3}}{2})(\frac{i}{2})⟨0|1⟩ - (\frac{i}{2})(\frac{\sqrt{3}}{2})⟨1|0⟩ + (-\frac{i}{2})(-\frac{i}{2})⟨1|1⟩$
    $= \frac{3}{4}(1) - 0 - 0 + (\frac{i^2}{4})(1) = \frac{3}{4} - \frac{1}{4} = \frac{2}{4} = \frac{1}{2}$.
    Interpretation: $P(0)=|\sqrt{3}/2|^2=3/4$, $P(1)=|i/2|^2=1/4$. Average = $(3/4)(+1) + (1/4)(-1) = 1/2$.

### E. Operators on Multi-Qubit Systems (Tensor Products of Operators)

Operators acting on multiple qubits are also constructed using tensor products.

#### 1. Local Operators ($A \otimes I, I \otimes B$)

*   If $A$ acts only on qubit 1, the operator is $A_1 = A \otimes I$.
*   If $B$ acts only on qubit 2, the operator is $B_2 = I \otimes B$.
*   **Example:** $X_1 = X \otimes I$ (X on qubit 1 of 2).
    $X \otimes I = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \otimes \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 \cdot I & 1 \cdot I \\ 1 \cdot I & 0 \cdot I \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \\ 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \end{pmatrix}$.
*   **Example:** $Z_2 = I \otimes Z$ (Z on qubit 2 of 2).
    $I \otimes Z = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \otimes \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} = \begin{pmatrix} 1 \cdot Z & 0 \cdot Z \\ 0 \cdot Z & 1 \cdot Z \end{pmatrix} = \begin{pmatrix} 1&0&0&0 \\ 0&-1&0&0 \\ 0&0&1&0 \\ 0&0&0&-1 \end{pmatrix}$.

#### 2. Global Operators ($A \otimes B$)

*   If $A$ acts on qubit 1 and $B$ acts on qubit 2 simultaneously.
*   **Example:** $H_1 H_2 = H \otimes H$.
    $H \otimes H = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \otimes \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$
    $= \frac{1}{2} \begin{pmatrix} 1 \cdot H & 1 \cdot H \\ 1 \cdot H & -1 \cdot H \end{pmatrix} = \frac{1}{2} \begin{pmatrix} H & H \\ H & -H \end{pmatrix}$
    $= \frac{1}{2} \begin{pmatrix} \frac{1}{\sqrt{2}}(1 & 1) & \frac{1}{\sqrt{2}}(1 & 1) \\ \frac{1}{\sqrt{2}}(1 & -1) & \frac{1}{\sqrt{2}}(1 & -1) \\ \frac{1}{\sqrt{2}}(1 & 1) & -\frac{1}{\sqrt{2}}(1 & 1) \\ \frac{1}{\sqrt{2}}(1 & -1) & -\frac{1}{\sqrt{2}}(1 & -1) \end{pmatrix}$  <- Incorrect expansion above. Let's use blocks correctly.
    $H \otimes H = \frac{1}{2} \begin{pmatrix}
    1\begin{pmatrix} 1&1\\1&-1 \end{pmatrix} & 1\begin{pmatrix} 1&1\\1&-1 \end{pmatrix} \\
    1\begin{pmatrix} 1&1\\1&-1 \end{pmatrix} & -1\begin{pmatrix} 1&1\\1&-1 \end{pmatrix}
    \end{pmatrix}
    = \frac{1}{2} \begin{pmatrix}
    1 & 1 & 1 & 1 \\
    1 & -1 & 1 & -1 \\
    1 & 1 & -1 & -1 \\
    1 & -1 & -1 & 1
    \end{pmatrix}$.

### F. Spin and Rotations: The Qubit-Spin Connection

#### 1. The Analogy

*   The mathematical framework for a single qubit ($ℂ^2$ Hilbert space, Pauli operators) is identical to that describing the intrinsic angular momentum (spin) of a spin-1/2 particle (like an electron).
*   Spin Up $|\uparrow⟩ \equiv |0⟩$, Spin Down $|\downarrow⟩ \equiv |1⟩$.

#### 2. General Rotations $R_{\vec{n}}(\theta)$

*   Any single-qubit unitary gate $U$ corresponds to a rotation of the Bloch sphere.
*   A rotation by angle $θ$ around the axis specified by the unit vector $\vec{n} = (n_x, n_y, n_z)$ is given by the operator:
    $$
    R_{\vec{n}}(\theta) = e^{-i (\theta/2) (\vec{n} \cdot \vec{\sigma})}
    $$
    where $\vec{\sigma} = (X, Y, Z)$ is the vector of Pauli matrices, and $\vec{n} \cdot \vec{\sigma} = n_x X + n_y Y + n_z Z$.
*   **Expansion:** Using $( \vec{n} \cdot \vec{\sigma} )^2 = I$ and Euler's formula for operators ($e^{iA} = \cos A + i \sin A$ generalized):
    $$
    R_{\vec{n}}(\theta) = \cos(\theta/2) I - i \sin(\theta/2) (\vec{n} \cdot \vec{\sigma})
    $$
*   **Examples:**
    *   Rotation about Z ($n_x=0, n_y=0, n_z=1$): $\vec{n} \cdot \vec{\sigma} = Z$.
        $R_z(\theta) = \cos(\theta/2)I - i\sin(\theta/2)Z = \begin{pmatrix} \cos(\theta/2)-i\sin(\theta/2) & 0 \\ 0 & \cos(\theta/2)+i\sin(\theta/2) \end{pmatrix} = \begin{pmatrix} e^{-i\theta/2} & 0 \\ 0 & e^{i\theta/2} \end{pmatrix}$.
        *   $Z = e^{i\pi/2} R_z(\pi)$. (Z gate is $\pi$ rotation around Z, up to global phase $i$).
        *   $S = e^{i\pi/4} R_z(\pi/2)$. (S gate is $\pi/2$ rotation around Z, up to global phase).
        *   $T = e^{i\pi/8} R_z(\pi/4)$. (T gate is $\pi/4$ rotation around Z, up to global phase).
    *   Rotation about X ($n_x=1, n_y=0, n_z=0$): $\vec{n} \cdot \vec{\sigma} = X$.
        $R_x(\theta) = \cos(\theta/2)I - i\sin(\theta/2)X = \begin{pmatrix} \cos(\theta/2) & -i\sin(\theta/2) \\ -i\sin(\theta/2) & \cos(\theta/2) \end{pmatrix}$.
        *   $X = i R_x(\pi)$. (X gate is $\pi$ rotation around X, up to global phase $i$).

This provides a powerful geometric intuition: single-qubit algorithms are sequences of rotations on the Bloch sphere.