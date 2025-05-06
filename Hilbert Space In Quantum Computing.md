## 1. Hilbert Space in Quantum Computing

**What is a Vector Space?**

Before Hilbert space, we need to understand a **vector space**. Informally, it's a collection of objects called **vectors** that you can add together and multiply by scalars (numbers), and these operations follow certain rules (like associativity, commutativity for addition, distributivity, etc.). Think of arrows in 2D or 3D space – you can add them head-to-tail, and you can stretch or shrink them by multiplying by a number.

**What is an Inner Product Space?**

An **inner product space** is a vector space equipped with an additional operation called the **inner product**. The inner product takes two vectors and produces a scalar (a single number, which can be complex in quantum mechanics). It generalizes the concept of the dot product in Euclidean space and allows us to define notions like:

*   **Length (Norm):** The length or norm of a vector $|ψ⟩$ is defined as $|||ψ⟩|| = \sqrt{⟨ψ|ψ⟩}$.
*   **Angle/Orthogonality:** The inner product helps define the "angle" between vectors. Two vectors $|ψ⟩$ and $|φ⟩$ are **orthogonal** if their inner product is zero: $⟨φ|ψ⟩ = 0$.

**What Makes it a Hilbert Space?**

A **Hilbert space** ($H$) is a specific type of inner product space that is also **complete**.

*   **Inner Product:** It has a well-defined inner product $⟨φ|ψ⟩$.
*   **Completeness:** This is a technical property meaning that any sequence of vectors in the space that *should* converge (a Cauchy sequence) *actually does* converge to a vector *within* the space. Intuitively, it means the space has "no holes" or "missing points". This is crucial for the mathematics of quantum mechanics, particularly when dealing with infinite-dimensional systems or continuous variables, but even for finite-dimensional qubit systems, the framework is built upon Hilbert spaces.

**Why is Hilbert Space Important in Quantum Computing?**

Hilbert space is the fundamental mathematical playground where quantum mechanics and quantum computing happen. Its importance stems from the **postulates of quantum mechanics**:

1.  **State Postulate:** The state of any isolated quantum system (like a qubit or a register of qubits) is described by a **unit vector** (a vector with norm 1) in a complex Hilbert space associated with that system. This vector is called the **state vector**, often denoted using ket notation like $|ψ⟩$.
    *   *Why Hilbert space?* Its vector space structure allows for **superposition** (linear combinations of states), and the inner product allows us to calculate **probabilities** and check for **normalization**. Completeness ensures mathematical rigor.

2.  **Evolution Postulate:** The evolution of a closed quantum system over time is described by a **unitary transformation** acting on its state vector. Unitary transformations are linear operators $U$ such that $U^† U = U U^† = I$ (where $U^†$ is the conjugate transpose and $I$ is the identity).
    *   *Why Hilbert space?* Unitary operators are defined on Hilbert spaces. Crucially, they **preserve the inner product** ($⟨Uφ|Uψ⟩ = ⟨φ|ψ⟩$) and thus preserve the norm ($||U|ψ⟩|| = |||ψ⟩||$). This means if a state starts normalized ($⟨ψ|ψ⟩ = 1$), it stays normalized after evolution, conserving total probability. Quantum gates are unitary transformations.

3.  **Measurement Postulate:** Quantum measurements are described by a set of measurement operators acting on the state space. For the common case of projective measurements, measuring an observable corresponds to projecting the state vector onto the eigenvectors (basis states) of the corresponding Hermitian operator (observable). The probability of obtaining a particular outcome is given by the square of the magnitude of the inner product between the state vector and the corresponding eigenvector (Born rule).
    *   *Why Hilbert space?* Inner products are essential for calculating measurement probabilities. Orthogonal basis states (eigenvectors of observables) represent distinct measurement outcomes.

**Hilbert Space for Qubit Systems:**

*   **Single Qubit:**
    *   The state of a single qubit is described by a vector in a 2-dimensional complex Hilbert space, denoted as $H_1 \cong ℂ^2$.
    *   The standard basis, called the **computational basis**, is $\{|0⟩, |1⟩\}$, where:
        $$
        |0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad |1⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
        $$
    *   A general state $|ψ⟩$ is a superposition (linear combination) of these basis states:
        $$
        |ψ⟩ = α|0⟩ + β|1⟩ = \begin{pmatrix} α \\ β \end{pmatrix}
        $$
    *   $α, β \in ℂ$ are complex amplitudes satisfying the normalization condition $|α|^2 + |β|^2 = 1$.

*   **Two Qubits:**
    *   To describe a system of two qubits, we use the **tensor product** ($⊗$) of their individual Hilbert spaces: $H_2 = H_{q1} ⊗ H_{q2} \cong ℂ^2 ⊗ ℂ^2 \cong ℂ^4$.
    *   The dimension of the space is $2 \times 2 = 4$.
    *   The computational basis for the 2-qubit system consists of the tensor products of the single-qubit basis states: $\{|00⟩, |01⟩, |10⟩, |11⟩\}$, where $|ij⟩ = |i⟩ ⊗ |j⟩$.
    *   Explicitly using the Kronecker product rule for vectors:
        $$
        |00⟩ = |0⟩⊗|0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix}⊗\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1(1) \\ 1(0) \\ 0(1) \\ 0(0) \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}
        $$
        $$
        |01⟩ = |0⟩⊗|1⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix}⊗\begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1(0) \\ 1(1) \\ 0(0) \\ 0(1) \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}
        $$
        $$
        |10⟩ = |1⟩⊗|0⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix}⊗\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0(1) \\ 0(0) \\ 1(1) \\ 1(0) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 1 \\ 0 \end{pmatrix}
        $$
        $$
        |11⟩ = |1⟩⊗|1⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix}⊗\begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0(0) \\ 0(1) \\ 1(0) \\ 1(1) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}
        $$
    *   A general 2-qubit state is a superposition in this 4D space:
        $$
        |ψ⟩ = α_{00}|00⟩ + α_{01}|01⟩ + α_{10}|10⟩ + α_{11}|11⟩ = \begin{pmatrix} α_{00} \\ α_{01} \\ α_{10} \\ α_{11} \end{pmatrix}
        $$
    *   Normalization requires $\sum_{i,j \in \{0,1\}} |α_{ij}|^2 = 1$.

*   **Three Qubits:**
    *   The Hilbert space is $H_3 = H_{q1} ⊗ H_{q2} ⊗ H_{q3} \cong ℂ^2 ⊗ ℂ^2 ⊗ ℂ^2 \cong ℂ^8$.
    *   The dimension is $2^3 = 8$.
    *   The computational basis has 8 states: $\{|000⟩, |001⟩, |010⟩, |011⟩, |100⟩, |101⟩, |110⟩, |111⟩\}$, where $|ijk⟩ = |i⟩⊗|j⟩⊗|k⟩$.
    *   The vector for $|000⟩$ is $\begin{pmatrix} 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \end{pmatrix}^T$, for $|001⟩$ it's $\begin{pmatrix} 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \end{pmatrix}^T$, and so on, up to $|111⟩ = \begin{pmatrix} 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \end{pmatrix}^T$. (Using standard binary ordering).
    *   A general state is $|ψ⟩ = \sum_{i,j,k \in \{0,1\}} α_{ijk}|ijk⟩$. Normalization: $\sum |α_{ijk}|^2 = 1$.

*   **N Qubits:**
    *   The Hilbert space $H_N$ is the tensor product of $N$ single-qubit spaces: $H_N \cong (ℂ^2)^{⊗N} \cong ℂ^{2^N}$.
    *   The dimension of the space is $2^N$. This **exponential growth** in the size of the state space with the number of qubits is the fundamental reason why quantum computers can potentially tackle problems intractable for classical computers. However, it also makes simulating quantum systems classically exponentially hard.
    *   The computational basis consists of $2^N$ states, $|x_1 x_2 ... x_N⟩$, where each $x_i \in \{0, 1\}$.
    *   A general state is $|ψ⟩ = \sum_{x \in \{0,1\}^N} α_x |x⟩$, with $\sum |α_x|^2 = 1$.

---

## 2. Inner Product

The inner product is a fundamental operation in Hilbert space that takes two state vectors (kets) and produces a complex scalar. It allows us to define geometry (length, angles, orthogonality) in the state space and is crucial for calculating measurement probabilities.

**Definition:**

Given two states in an N-dimensional Hilbert space:
$|ψ⟩ = \sum_{i=1}^{N} ψ_i |i⟩ = \begin{pmatrix} ψ_1 \\ ψ_2 \\ \vdots \\ ψ_N \end{pmatrix}$
$|φ⟩ = \sum_{j=1}^{N} φ_j |j⟩ = \begin{pmatrix} φ_1 \\ φ_2 \\ \vdots \\ φ_N \end{pmatrix}$
where $\{|i⟩\}$ is an orthonormal basis, and $ψ_i, φ_j$ are complex amplitudes.

The inner product $⟨φ|ψ⟩$ is defined as:
$$
⟨φ|ψ⟩ = |φ⟩^† |ψ⟩ = \begin{pmatrix} φ_1^* & φ_2^* & \cdots & φ_N^* \end{pmatrix} \begin{pmatrix} ψ_1 \\ ψ_2 \\ \vdots \\ ψ_N \end{pmatrix} = \sum_{k=1}^{N} φ_k^* ψ_k
$$
It involves taking the Hermitian conjugate (transpose + complex conjugate) of the first vector (turning the ket $|φ⟩$ into the bra $⟨φ|$) and then performing matrix multiplication with the second vector (the ket $|ψ⟩$).

**Inner Product for Qubit Systems:**

*   **Single Qubit:** $N=2$. Basis $\{|0⟩, |1⟩\}$.
    $|ψ⟩ = α|0⟩ + β|1⟩ = \begin{pmatrix} α \\ β \end{pmatrix}$
    $|φ⟩ = γ|0⟩ + δ|1⟩ = \begin{pmatrix} γ \\ δ \end{pmatrix}$
    $$
    ⟨φ|ψ⟩ = \begin{pmatrix} γ^* & δ^* \end{pmatrix} \begin{pmatrix} α \\ β \end{pmatrix} = γ^*α + δ^*β
    $$
    **Example:** Calculate $⟨+|ψ⟩$ where $|+⟩ = \frac{1}{\sqrt{2}}(|0⟩+|1⟩)$ and $|ψ⟩ = \frac{\sqrt{3}}{2}|0⟩ + \frac{i}{2}|1⟩$.
    $|+⟩ = \begin{pmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \end{pmatrix}$, $|ψ⟩ = \begin{pmatrix} \sqrt{3}/2 \\ i/2 \end{pmatrix}$.
    $⟨+| = \begin{pmatrix} (1/\sqrt{2})^* & (1/\sqrt{2})^* \end{pmatrix} = \begin{pmatrix} 1/\sqrt{2} & 1/\sqrt{2} \end{pmatrix}$.
    $$
    ⟨+|ψ⟩ = \begin{pmatrix} 1/\sqrt{2} & 1/\sqrt{2} \end{pmatrix} \begin{pmatrix} \sqrt{3}/2 \\ i/2 \end{pmatrix} = (1/\sqrt{2})(\sqrt{3}/2) + (1/\sqrt{2})(i/2)
    $$
    $$
    = \frac{\sqrt{3}}{2\sqrt{2}} + \frac{i}{2\sqrt{2}} = \frac{\sqrt{3}+i}{2\sqrt{2}}
    $$
    (This matches the calculation in the Measurement section).

*   **Two Qubits:** $N=4$. Basis $\{|00⟩, |01⟩, |10⟩, |11⟩\}$.
    $|ψ⟩ = α_{00}|00⟩ + α_{01}|01⟩ + α_{10}|10⟩ + α_{11}|11⟩ = \begin{pmatrix} α_{00} \\ α_{01} \\ α_{10} \\ α_{11} \end{pmatrix}$
    $|φ⟩ = β_{00}|00⟩ + β_{01}|01⟩ + β_{10}|10⟩ + β_{11}|11⟩ = \begin{pmatrix} β_{00} \\ β_{01} \\ β_{10} \\ β_{11} \end{pmatrix}$
    $$
    ⟨φ|ψ⟩ = \sum_{i,j \in \{0,1\}} β_{ij}^* α_{ij} = β_{00}^*α_{00} + β_{01}^*α_{01} + β_{10}^*α_{10} + β_{11}^*α_{11}
    $$
    **Example:** Calculate $⟨\Phi^+|\Psi^+⟩$ where $|\Phi^+⟩ = \frac{1}{\sqrt{2}}(|00⟩+|11⟩)$ and $|\Psi^+⟩ = \frac{1}{\sqrt{2}}(|01⟩+|10⟩)$.
    $|\Phi^+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 0 \\ 0 \\ 1 \end{pmatrix}$, $|\Psi^+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 0 \\ 1 \\ 1 \\ 0 \end{pmatrix}$.
    $⟨\Phi^+| = \frac{1}{\sqrt{2}}\begin{pmatrix} 1^* & 0^* & 0^* & 1^* \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 0 & 0 & 1 \end{pmatrix}$.
    $$
    ⟨\Phi^+|\Psi^+⟩ = \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 0 & 0 & 1 \end{pmatrix} \right) \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 0 \\ 1 \\ 1 \\ 0 \end{pmatrix} \right)
    $$
    $$
    = \frac{1}{2} \left( (1)(0) + (0)(1) + (0)(1) + (1)(0) \right) = \frac{1}{2}(0) = 0
    $$
    This confirms that the Bell states $|\Phi^+⟩$ and $|\Psi^+⟩$ are orthogonal, as expected since they form part of an orthonormal basis.

*   **Three Qubits (and N Qubits):** $N=8$ (or $N=2^N$). The principle is identical, summing over all $N$ components.
    $|ψ⟩ = \sum_{x \in \{0,1\}^N} α_x |x⟩$
    $|φ⟩ = \sum_{y \in \{0,1\}^N} β_y |y⟩$
    $$
    ⟨φ|ψ⟩ = \sum_{z \in \{0,1\}^N} β_z^* α_z
    $$

---

## 3. Outer Product

The outer product takes two state vectors (a ket and a bra) and produces a **matrix** (an operator). It's a way to construct operators from vectors.

**Definition:**

Given two states $|ψ⟩$ and $|φ⟩$ in an N-dimensional Hilbert space:
$|ψ⟩ = \begin{pmatrix} ψ_1 \\ \vdots \\ ψ_N \end{pmatrix}$, $⟨φ| = \begin{pmatrix} φ_1^* & \cdots & φ_N^* \end{pmatrix}$

The outer product $|ψ⟩⟨φ|$ is an $N \times N$ matrix defined by standard matrix multiplication of the column vector $|ψ⟩$ with the row vector $⟨φ|$:
$$
|ψ⟩⟨φ| = \begin{pmatrix} ψ_1 \\ \vdots \\ ψ_N \end{pmatrix} \begin{pmatrix} φ_1^* & \cdots & φ_N^* \end{pmatrix} = \begin{pmatrix}
ψ_1 φ_1^* & ψ_1 φ_2^* & \cdots & ψ_1 φ_N^* \\
ψ_2 φ_1^* & ψ_2 φ_2^* & \cdots & ψ_2 φ_N^* \\
\vdots & \vdots & \ddots & \vdots \\
ψ_N φ_1^* & ψ_N φ_2^* & \cdots & ψ_N φ_N^*
\end{pmatrix}
$$
The element at row $i$, column $j$ of the resulting matrix is $(|ψ⟩⟨φ|)_{ij} = ψ_i φ_j^*$.

**Outer Product for Qubit Systems:**

*   **Single Qubit:** $N=2$.
    $|ψ⟩ = \begin{pmatrix} α \\ β \end{pmatrix}$, $|φ⟩ = \begin{pmatrix} γ \\ δ \end{pmatrix} \implies ⟨φ| = \begin{pmatrix} γ^* & δ^* \end{pmatrix}$.
    $$
    |ψ⟩⟨φ| = \begin{pmatrix} α \\ β \end{pmatrix} \begin{pmatrix} γ^* & δ^* \end{pmatrix} = \begin{pmatrix} α γ^* & α δ^* \\ β γ^* & β δ^* \end{pmatrix}
    $$
    **Example: Projection Operator $|+⟩⟨+|$**
    $|+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} \implies ⟨+| = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \end{pmatrix}$.
    $$
    |+⟩⟨+| = \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} \right) \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \end{pmatrix} \right) = \frac{1}{2} \begin{pmatrix} 1 \\ 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \end{pmatrix}
    $$
    $$
    = \frac{1}{2} \begin{pmatrix} (1)(1) & (1)(1) \\ (1)(1) & (1)(1) \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}
    $$
    This operator projects states onto the $|+⟩$ direction.

*   **Two Qubits:** $N=4$.
    **Example: Constructing the CNOT gate using outer products.**
    Recall CNOT maps: $|00⟩→|00⟩$, $|01⟩→|01⟩$, $|10⟩→|11⟩$, $|11⟩→|10⟩$.
    An operator $U$ mapping basis state $|i⟩$ to $|f_i⟩$ can be written as $U = \sum_i |f_i⟩⟨i|$.
    So, CNOT can be written as:
    $$
    \text{CNOT} = |00⟩⟨00| + |01⟩⟨01| + |11⟩⟨10| + |10⟩⟨11|
    $$
    Let's calculate one term, e.g., $|11⟩⟨10|$.
    $|11⟩ = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}$, $⟨10| = \begin{pmatrix} 0 & 0 & 1 & 0 \end{pmatrix}$.
    $$
    |11⟩⟨10| = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix} \begin{pmatrix} 0 & 0 & 1 & 0 \end{pmatrix} = \begin{pmatrix}
    0 & 0 & 0 & 0 \\
    0 & 0 & 0 & 0 \\
    0 & 0 & 0 & 0 \\
    0 & 0 & 1 & 0
    \end{pmatrix}
    $$
    This matrix has a single 1 at row 4, column 3 (mapping the 3rd basis state $|10⟩$ to the 4th basis state $|11⟩$). Calculating the other terms similarly and adding them up reconstructs the full CNOT matrix shown earlier.

*   **Three Qubits (and N Qubits):** $N=8$ (or $N=2^N$). Outer products yield $N \times N$ matrices. The completeness relation (sum of projectors onto basis states equals identity) holds: $\sum_{x \in \{0,1\}^N} |x⟩⟨x| = I_{N}$, where $I_N$ is the $N \times N$ identity matrix.

---

## 4. Basis States for Quantum Systems

A **basis** for a vector space is a set of vectors such that any vector in the space can be written as a unique linear combination of the basis vectors, and the basis vectors are linearly independent. An **orthonormal basis** is a basis where all vectors are mutually orthogonal and normalized (unit length).

**Importance:**

*   **Representation:** Define the coordinates (amplitudes) of a quantum state.
*   **Measurement:** Measurements are defined with respect to a specific basis. The outcomes correspond to the basis states.
*   **Operators:** Matrices representing gates or observables are defined relative to a chosen basis.

**Computational Basis (Z-basis):**

This is the most standard and commonly used basis in quantum computing. It's defined by the eigenstates of the Pauli-Z operator.

*   **Single Qubit:** $\{|0⟩, |1⟩\}$
    $$
    |0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad |1⟩ = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
    $$
    This basis is orthonormal: $⟨0|1⟩=0$, $⟨0|0⟩=1$, $⟨1|1⟩=1$.

*   **Two Qubits:** $\{|00⟩, |01⟩, |10⟩, |11⟩\}$
    These are formed by tensor products: $|ij⟩ = |i⟩⊗|j⟩$.
    Vectors are $\begin{pmatrix} 1\\0\\0\\0 \end{pmatrix}, \begin{pmatrix} 0\\1\\0\\0 \end{pmatrix}, \begin{pmatrix} 0\\0\\1\\0 \end{pmatrix}, \begin{pmatrix} 0\\0\\0\\1 \end{pmatrix}$.
    This basis is also orthonormal. For example: $⟨00|01⟩ = (⟨0|⊗⟨0|) (|0⟩⊗|1⟩) = ⟨0|0⟩ ⟨0|1⟩ = (1)(0) = 0$. And $⟨01|01⟩ = ⟨0|0⟩⟨1|1⟩ = (1)(1) = 1$.

*   **Three Qubits:** $\{|000⟩, |001⟩, |010⟩, |011⟩, |100⟩, |101⟩, |110⟩, |111⟩\}$
    Consists of $2^3=8$ orthonormal states $|ijk⟩ = |i⟩⊗|j⟩⊗|k⟩$.

*   **N Qubits:** $\{|x_1 x_2 ... x_N⟩ \mid x_i \in \{0, 1\}\}$
    Consists of $2^N$ orthonormal states.

**Other Important Bases:**

*   **X-basis (Hadamard basis):** $\{|+⟩, |-⟩\}$ for a single qubit.
*   **Y-basis:** $\{|+i⟩, |-i⟩\}$ for a single qubit.
*   **Bell basis:** $\{|\Phi^+⟩, |\Phi^-⟩, |\Psi^+⟩, |\Psi^-⟩\}$ for two qubits. This is an *entangled* basis.

Changing between bases is achieved by applying specific unitary gates (e.g., the Hadamard gate H changes between the Z and X bases).

---

## 5. Rotational Spin

The concept of "spin" originates from particle physics, describing an intrinsic angular momentum possessed by particles like electrons. Crucially, the mathematical framework developed to describe the spin of a spin-1/2 particle (which has exactly two fundamental states, "spin up" and "spin down") is **identical** to the mathematics of a single qubit.

**Connection to Qubits:**

*   A qubit is fundamentally any quantum system with two distinct, accessible energy levels or states.
*   An electron's spin provides a natural physical realization:
    *   **Spin Up ($|\uparrow⟩$):** Corresponds to the qubit state $|0⟩$.
    *   **Spin Down ($|\downarrow⟩$):** Corresponds to the qubit state $|1⟩$.
*   This analogy allows us to use the well-understood mathematics of spin rotations to describe qubit operations (single-qubit gates).

**Pauli Matrices ($σ_x, σ_y, σ_z$ or $X, Y, Z$):**

These matrices are fundamental in describing spin-1/2 systems and, consequently, single-qubit operations.

*   $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$: Corresponds to measuring spin along the x-axis / flipping spin up $\leftrightarrow$ spin down.
*   $Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}$: Corresponds to measuring spin along the y-axis.
*   $Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$: Corresponds to measuring spin along the z-axis (eigenstates are spin up $|0⟩$ and spin down $|1⟩$).

**Spin & Bloch Sphere:**

The Bloch sphere provides a perfect geometric representation for the state of a spin-1/2 particle (and thus a single qubit).

*   A point $(x, y, z)$ on the surface of the Bloch sphere represents a state where the spin is "pointing" in that direction. This means if we were to measure the spin along the axis defined by the vector $(x, y, z)$, we would get the outcome "+1" (spin aligned with the axis) with 100% probability.
*   The North Pole $(0,0,1)$ is spin up ($|0⟩$).
*   The South Pole $(0,0,-1)$ is spin down ($|1⟩$).
*   Points on the +X axis correspond to state $|+⟩$, etc.

**Rotations on the Bloch Sphere (Single-Qubit Gates):**

Every single-qubit gate (unitary $2 \times 2$ matrix) corresponds to a **rotation** of the state vector on the surface of the Bloch sphere.

*   **General Rotation Operator:** A rotation by an angle $θ$ around an axis defined by the unit vector $\vec{n} = (n_x, n_y, n_z)$ is given by the unitary operator:
    $$
    R_{\vec{n}}(\theta) = e^{-i (\theta/2) (\vec{n} \cdot \vec{\sigma})}
    $$
    where $\vec{\sigma} = (X, Y, Z)$ is the vector of Pauli matrices, and $\vec{n} \cdot \vec{\sigma} = n_x X + n_y Y + n_z Z$.
    Using the property $( \vec{n} \cdot \vec{\sigma} )^2 = I$ (for unit vector $\vec{n}$), the exponential can be expanded using Euler's formula for operators:
    $$
    R_{\vec{n}}(\theta) = \cos(\theta/2) I - i \sin(\theta/2) (\vec{n} \cdot \vec{\sigma})
    $$
    *Note the factor of $\theta/2$!* A rotation by angle $\theta$ in 3D space corresponds to a gate operation involving $\theta/2$. This relates back to the $\theta/2$ in the general state representation $|ψ⟩ = \cos(\theta/2)|0⟩ + e^{i\phi}\sin(\theta/2)|1⟩$.

*   **Examples:**
    *   **Rotation about Z-axis:** $\vec{n} = (0, 0, 1)$. $\vec{n} \cdot \vec{\sigma} = Z$.
        $$
        R_z(\theta) = \cos(\theta/2) I - i \sin(\theta/2) Z
        $$
        $$
        = \cos(\theta/2) \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - i \sin(\theta/2) \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
        $$
        $$
        = \begin{pmatrix} \cos(\theta/2) - i\sin(\theta/2) & 0 \\ 0 & \cos(\theta/2) + i\sin(\theta/2) \end{pmatrix} = \begin{pmatrix} e^{-i\theta/2} & 0 \\ 0 & e^{i\theta/2} \end{pmatrix}
        $$
        *   If $\theta = π$, $R_z(π) = \begin{pmatrix} e^{-iπ/2} & 0 \\ 0 & e^{iπ/2} \end{pmatrix} = \begin{pmatrix} -i & 0 \\ 0 & i \end{pmatrix} = i \begin{pmatrix} -1 & 0 \\ 0 & 1 \end{pmatrix} = -iZ$. This is the Z gate up to a global phase of $-i$. (Often gates are defined only up to a global phase). The actual Z gate is $R_z(\pi)$ multiplied by $i$. A $\pi$ rotation around Z corresponds to the Z gate.
        *   If $\theta = π/2$, $R_z(π/2) = \begin{pmatrix} e^{-iπ/4} & 0 \\ 0 & e^{iπ/4} \end{pmatrix} = e^{-iπ/4} \begin{pmatrix} 1 & 0 \\ 0 & e^{iπ/2} \end{pmatrix} = e^{-iπ/4} \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix} = e^{-iπ/4} S$. This is the S gate up to a global phase.
    *   **Rotation about X-axis:** $\vec{n} = (1, 0, 0)$. $\vec{n} \cdot \vec{\sigma} = X$.
        $$
        R_x(\theta) = \cos(\theta/2) I - i \sin(\theta/2) X
        $$
        $$
        = \cos(\theta/2) \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} - i \sin(\theta/2) \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}
        $$
        $$
        = \begin{pmatrix} \cos(\theta/2) & -i\sin(\theta/2) \\ -i\sin(\theta/2) & \cos(\theta/2) \end{pmatrix}
        $$
        *   If $\theta = π$, $R_x(π) = \begin{pmatrix} \cos(π/2) & -i\sin(π/2) \\ -i\sin(π/2) & \cos(π/2) \end{pmatrix} = \begin{pmatrix} 0 & -i(1) \\ -i(1) & 0 \end{pmatrix} = -i \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = -iX$. The X gate is a $\pi$ rotation about X (up to global phase).
    *   **Hadamard Gate:** $H = \frac{1}{\sqrt{2}}(X+Z)$. This corresponds to a rotation by $\pi$ around the axis $\vec{n} = (1, 0, 1)/\sqrt{2}$, which points halfway between the +X and +Z axes.

Understanding gates as rotations on the Bloch sphere provides powerful geometric intuition for visualizing and reasoning about single-qubit operations.

Okay, let's continue building upon the mathematical foundations we've established. We'll now explore operators, observables, expectation values, and how operators act on multi-qubit systems in more detail.

---

## 6. Operators and Observables in Quantum Mechanics

In quantum mechanics, physical properties that can be measured (like position, momentum, energy, spin along an axis) are called **observables**. Each observable is associated with a mathematical **operator** that acts on the state vectors in the Hilbert space.

**What are Operators?**

Mathematically, an operator $A$ is essentially a function that takes a state vector $|ψ⟩$ as input and outputs another state vector $|φ⟩ = A|ψ⟩$. In finite-dimensional Hilbert spaces (like those for qubits), operators are represented by **matrices**.

*   **Linear Operators:** The operators relevant to quantum mechanics are **linear**. This means for any vectors $|ψ⟩, |φ⟩$ and complex scalars $α, β$:
    $$
    A(α|ψ⟩ + β|φ⟩) = α(A|ψ⟩) + β(A|φ⟩)
    $$
    Matrix multiplication inherently satisfies linearity.

*   **Adjoint (Hermitian Conjugate) of an Operator:** Just like we defined the adjoint (dagger, $†$) for kets (vectors), we can define it for operators (matrices). The adjoint $A^†$ of an operator $A$ is its **conjugate transpose**.
    *   If $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, then $A^† = \begin{pmatrix} a^* & c^* \\ b^* & d^* \end{pmatrix}$.
    *   Property: $(AB)^† = B^† A^†$ (order reverses).

**Hermitian Operators (Observables):**

A special class of operators is crucial because they correspond to physical observables. An operator $A$ is **Hermitian** (or self-adjoint) if it is equal to its own adjoint:
$$
A = A^†
$$
*   **Why Hermitian for Observables?**
    1.  **Real Eigenvalues:** The possible outcomes of measuring a physical quantity must be real numbers. It's a mathematical theorem that the **eigenvalues** of a Hermitian operator are always **real**.
    2.  **Orthogonal Eigenvectors:** The **eigenvectors** of a Hermitian operator corresponding to *distinct* eigenvalues are always **orthogonal**. These eigenvectors form a complete orthonormal basis for the Hilbert space, representing the possible states the system can collapse into upon measurement of that observable.

*   **Eigenvalue Equation:** If $|a⟩$ is an eigenvector of operator $A$ with eigenvalue $a$, it satisfies:
    $$
    A|a⟩ = a|a⟩
    $$
    This means applying the operator $A$ to its eigenvector $|a⟩$ simply scales the eigenvector by the corresponding eigenvalue $a$, without changing its "direction" in Hilbert space.

*   **Examples:**
    *   **Pauli Matrices:** $X, Y, Z$ are Hermitian operators. Let's check $X$:
        $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$. $X^† = \begin{pmatrix} 0^* & 1^* \\ 1^* & 0^* \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = X$. So, X is Hermitian. (Similarly for Y and Z).
    *   **Eigenvalues/Eigenvectors of Z:**
        $Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$
        $Z|0⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} = (+1)|0⟩$. Eigenvalue $a=+1$, Eigenvector $|0⟩$.
        $Z|1⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 0 \\ -1 \end{pmatrix} = (-1)|1⟩$. Eigenvalue $a=-1$, Eigenvector $|1⟩$.
        The eigenvalues (+1, -1) are real, and the eigenvectors ($|0⟩, |1⟩$) form the orthonormal computational basis. Measuring the observable associated with Z (spin along z) yields +1 or -1, collapsing the state to $|0⟩$ or $|1⟩$.
    *   **Eigenvalues/Eigenvectors of X:**
        $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$
        Eigenvectors are $|+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}$ and $|-⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}$.
        $X|+⟩ = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = (+1)|+⟩$. Eigenvalue $a=+1$.
        $X|-⟩ = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} -1 \\ 1 \end{pmatrix} = (-1)\frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = (-1)|-⟩$. Eigenvalue $a=-1$.
        Again, real eigenvalues (+1, -1) and orthogonal eigenvectors ($|+⟩, |-⟩$) which form the X-basis.

**Unitary Operators (Quantum Gates):**

As discussed, quantum gates represent the evolution of a closed system. They must be **unitary** operators ($U^† U = I$).

*   **Relationship to Hermitian Operators:** Any unitary operator $U$ can be written in terms of a Hermitian operator $H$ (called the generator) as $U = e^{i \gamma H}$ for some real number $\gamma$. For time evolution described by the Schrödinger equation with a time-independent Hamiltonian $H$ (the energy observable), the evolution operator is $U(t) = e^{-iHt/\hbar}$, where $\hbar$ is the reduced Planck constant.
*   **Pauli matrices as Generators:** The rotation operators $R_{\vec{n}}(\theta)$ were generated by the Hermitian Pauli matrices.
*   **Unitary operators are NOT generally Hermitian** (unless they are also Hermitian, like the Pauli matrices themselves which square to Identity). For example, the S gate is unitary but not Hermitian:
    $S = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}$, $S^† = \begin{pmatrix} 1 & 0 \\ 0 & -i \end{pmatrix}$. $S \neq S^†$.
    $S^† S = \begin{pmatrix} 1 & 0 \\ 0 & -i \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & (-i)(i) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$.

## 7. Expectation Values

When we measure an observable $A$ on a system in state $|ψ⟩$, we get one of the eigenvalues $a_i$ of $A$ with probability $P(a_i) = |⟨a_i|ψ⟩|^2$, where $|a_i⟩$ is the corresponding eigenvector.

The **expectation value** of the observable $A$ for the state $|ψ⟩$, denoted $⟨A⟩_{ψ}$ or simply $⟨A⟩$, is the *average* outcome we would expect if we prepared the system in state $|ψ⟩$ many times and measured $A$ each time.

**Calculation:**

The expectation value is calculated as the sum of each possible outcome (eigenvalue $a_i$) weighted by its probability $P(a_i)$:
$$
⟨A⟩_{ψ} = \sum_i a_i P(a_i) = \sum_i a_i |⟨a_i|ψ⟩|^2
$$

A more compact and often easier way to calculate the expectation value uses the operator $A$ directly:
$$
⟨A⟩_{ψ} = ⟨ψ| A |ψ⟩
$$

**Derivation of the Compact Formula:**

Let's show these two formulas are equivalent. We use the **spectral decomposition** of the Hermitian operator $A$, which states that $A$ can be written as a sum over its eigenvalues and projectors onto its eigenspaces: $A = \sum_i a_i |a_i⟩⟨a_i|$. (This assumes non-degenerate eigenvalues for simplicity, but generalizes).

Substitute this into $⟨ψ| A |ψ⟩$:
$$
⟨ψ| A |ψ⟩ = ⟨ψ| \left( \sum_i a_i |a_i⟩⟨a_i| \right) |ψ⟩
$$
Using linearity, move $⟨ψ|$ inside the sum:
$$
= \sum_i a_i ⟨ψ| a_i⟩⟨a_i |ψ⟩
$$
Recognize that $⟨ψ|a_i⟩$ is a complex number, and $⟨a_i|ψ⟩$ is its complex conjugate, so $⟨ψ|a_i⟩⟨a_i|ψ⟩ = (⟨a_i|ψ⟩)^* ⟨a_i|ψ⟩ = |⟨a_i|ψ⟩|^2$.
$$
= \sum_i a_i |⟨a_i|ψ⟩|^2
$$
This is exactly the definition of the expectation value based on probabilities. So, $⟨A⟩_{ψ} = ⟨ψ| A |ψ⟩$.

**Examples:**

*   **Expectation value of Z for state $|+⟩$:**
    $A = Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$, $|ψ⟩ = |+⟩ = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} \implies ⟨ψ| = ⟨+| = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \end{pmatrix}$.
    $$
    ⟨Z⟩_{+} = ⟨+| Z |+⟩ = \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \end{pmatrix} \right) \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} \right)
    $$
    First, apply Z to $|+⟩$: $Z|+⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix} = |-⟩$.
    $$
    ⟨Z⟩_{+} = ⟨+ | -⟩
    $$
    We know $⟨+|-⟩ = 0$ because they are orthogonal basis states.
    $$
    ⟨Z⟩_{+} = 0
    $$
    *Interpretation:* The state $|+⟩$ is an equal superposition of $|0⟩$ (eigenvalue +1 for Z) and $|1⟩$ (eigenvalue -1 for Z). If measured many times, we'd get +1 half the time and -1 half the time. The average (expectation value) is $(1/2)(+1) + (1/2)(-1) = 0$.

*   **Expectation value of X for state $|0⟩$:**
    $A = X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$, $|ψ⟩ = |0⟩ = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \implies ⟨ψ| = ⟨0| = \begin{pmatrix} 1 & 0 \end{pmatrix}$.
    $$
    ⟨X⟩_{0} = ⟨0| X |0⟩ = \begin{pmatrix} 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix}
    $$
    First, apply X to $|0⟩$: $X|0⟩ = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 1 \end{pmatrix} = |1⟩$.
    $$
    ⟨X⟩_{0} = ⟨0 | 1⟩ = 0
    $$
    *Interpretation:* The state $|0⟩$ can be written in the X-basis as $|0⟩ = \frac{1}{\sqrt{2}}(|+⟩ + |-⟩)$. Measuring X yields +1 (state $|+⟩$) with probability $|⟨+|0⟩|^2 = 1/2$, and -1 (state $|-⟩$) with probability $|⟨-|0⟩|^2 = 1/2$. The average is $(1/2)(+1) + (1/2)(-1) = 0$.

*   **Expectation value of Z for state $|ψ⟩ = \frac{\sqrt{3}}{2}|0⟩ + \frac{i}{2}|1⟩$:**
    $A = Z$, $|ψ⟩ = \begin{pmatrix} \sqrt{3}/2 \\ i/2 \end{pmatrix}$, $⟨ψ| = \begin{pmatrix} \sqrt{3}/2 & -i/2 \end{pmatrix}$.
    $$
    ⟨Z⟩_{ψ} = ⟨ψ| Z |ψ⟩ = \begin{pmatrix} \sqrt{3}/2 & -i/2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} \sqrt{3}/2 \\ i/2 \end{pmatrix}
    $$
    First, $Z|ψ⟩ = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} \sqrt{3}/2 \\ i/2 \end{pmatrix} = \begin{pmatrix} \sqrt{3}/2 \\ -i/2 \end{pmatrix}$.
    $$
    ⟨Z⟩_{ψ} = \begin{pmatrix} \sqrt{3}/2 & -i/2 \end{pmatrix} \begin{pmatrix} \sqrt{3}/2 \\ -i/2 \end{pmatrix}
    $$
    $$
    = (\sqrt{3}/2)(\sqrt{3}/2) + (-i/2)(-i/2) = 3/4 + (i^2/4) = 3/4 - 1/4 = 2/4 = 1/2
    $$
    *Interpretation:* Probability of measuring 0 (eigenvalue +1) is $P(0) = |⟨0|ψ⟩|^2 = |\sqrt{3}/2|^2 = 3/4$. Probability of measuring 1 (eigenvalue -1) is $P(1) = |⟨1|ψ⟩|^2 = |i/2|^2 = 1/4$. Expectation value = $P(0)(+1) + P(1)(-1) = (3/4)(1) + (1/4)(-1) = 3/4 - 1/4 = 2/4 = 1/2$. Matches.

---

## 8. Operators on Multi-Qubit Systems

Operators acting on composite systems (like two or more qubits) are constructed using the tensor product.

**Operators Acting on One Subsystem:**

If an operator $A$ acts only on the first qubit (subsystem 1) of a two-qubit system, and the identity operator $I$ acts on the second qubit (subsystem 2), the combined operator acting on the total Hilbert space $H_1 ⊗ H_2$ is $A ⊗ I$.

*   **Example:** Apply the $X$ gate to the first qubit of a two-qubit system. The operator is $X_1 \equiv X ⊗ I$.
    We need the matrix representation of $X ⊗ I$.
    $X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$, $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$.
    Using the Kronecker product definition:
    $$
    X ⊗ I = \begin{pmatrix} 0 \otimes I & 1 \otimes I \\ 1 \otimes I & 0 \otimes I \end{pmatrix} = \begin{pmatrix} 0 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} & 1 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \\ 1 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} & 0 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \end{pmatrix}
    $$
    $$
    = \begin{pmatrix} 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \\ 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \end{pmatrix}
    $$
    Let's apply this to a state $|01⟩ = |0⟩⊗|1⟩ = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}$. We expect the first qubit to flip ($|0⟩ \rightarrow |1⟩$), leaving the second as $|1⟩$, resulting in $|11⟩$.
    $$
    (X ⊗ I)|01⟩ = \begin{pmatrix} 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \\ 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \end{pmatrix}
    $$
    The result is the vector for $|11⟩$, as expected.

*   Similarly, an operator $B$ acting only on the second qubit is represented by $I ⊗ B$.
    **Example:** Apply Z to the second qubit: $Z_2 \equiv I ⊗ Z$.
    $$
    I ⊗ Z = \begin{pmatrix} 1 \otimes Z & 0 \otimes Z \\ 0 \otimes Z & 1 \otimes Z \end{pmatrix} = \begin{pmatrix} 1 \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} & 0 \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \\ 0 \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} & 1 \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} \end{pmatrix}
    $$
    $$
    = \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & -1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1 \end{pmatrix}
    $$

**Operators Acting on Both Subsystems:**

If operator $A$ acts on qubit 1 and operator $B$ acts on qubit 2 simultaneously, the combined operator is $A ⊗ B$.

*   **Example:** Apply H to both qubits: $H_1 H_2 = H ⊗ H$.
    $$
    H ⊗ H = \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \right) ⊗ \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \right)
    $$
    $$
    = \frac{1}{2} \begin{pmatrix} 1 \otimes H & 1 \otimes H \\ 1 \otimes H & -1 \otimes H \end{pmatrix} = \frac{1}{2} \begin{pmatrix} H & H \\ H & -H \end{pmatrix}
    $$
    $$
    = \frac{1}{2} \begin{pmatrix}
    1/\sqrt{2} & 1/\sqrt{2} & 1/\sqrt{2} & 1/\sqrt{2} \\
    1/\sqrt{2} & -1/\sqrt{2} & 1/\sqrt{2} & -1/\sqrt{2} \\
    1/\sqrt{2} & 1/\sqrt{2} & -1/\sqrt{2} & -1/\sqrt{2} \\
    1/\sqrt{2} & -1/\sqrt{2} & -1/\sqrt{2} & 1/\sqrt{2}
    \end{pmatrix}
    = \frac{1}{2\sqrt{2}} \begin{pmatrix} % Incorrect calculation in previous line, let's redo carefully
    1(1) & 1(1) & 1(1) & 1(1) \\
    1(1) & 1(-1) & 1(1) & 1(-1) \\
    1(1) & 1(1) & -1(1) & -1(1) \\
    1(1) & 1(-1) & -1(1) & -1(-1)
    \end{pmatrix} \text{ Incorrect expansion, use block structure: }
    $$
    $$
    H \otimes H = \frac{1}{2} \begin{pmatrix}
    1 \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} & 1 \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \\
    1 \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} & -1 \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}
    \end{pmatrix}
    = \frac{1}{2} \begin{pmatrix}
    1 & 1 & 1 & 1 \\
    1 & -1 & 1 & -1 \\
    1 & 1 & -1 & -1 \\
    1 & -1 & -1 & 1
    \end{pmatrix}
    $$
    This $H⊗H$ operator transforms the 2-qubit computational basis states into equal superpositions of all four basis states (with varying signs). E.g., $(H⊗H)|00⟩ = \frac{1}{2}(|00⟩+|01⟩+|10⟩+|11⟩)$.

**Two-Qubit Gates (e.g., CNOT):**

Gates like CNOT inherently act on the combined 2-qubit (or multi-qubit) space and cannot generally be written as a simple tensor product $A ⊗ B$. Their $4 \times 4$ (or larger) matrix representation, like the one derived earlier for CNOT, must be used.

---