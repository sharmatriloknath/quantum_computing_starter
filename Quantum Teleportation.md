## Quantum Teleportation Protocol (Method 1: Standard Qubit Notation)

This is one of the fundamental protocols in quantum information, distinct from algorithms like Shor's or Grover's, as it focuses on *transmitting* quantum information rather than computation.

**Goal:** Alice (A) wants to send an arbitrary quantum state (qubit) |ψ⟩ to Bob (B). This state is unknown to Alice beforehand, meaning she doesn't know the specific values of α and β.

```math
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
```

where α and β are complex numbers such that |α|² + |β|² = 1 (normalization condition).

**Key Resources:**

1.  **The Quantum State:** The qubit |ψ⟩ that Alice possesses initially.
2.  **Shared Entangled Pair:** Alice and Bob share a pair of entangled qubits, typically prepared in one of the Bell states. In this explanation, we use the Bell state |β₀₀⟩:
    ```math
    |\beta_{00}\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)
    ```
    *   Alice holds the *first* qubit of this pair.
    *   Bob holds the *second* qubit of this pair.
3.  **Classical Communication Channel:** A regular channel (like a phone line or internet) to send classical bits (0s and 1s).

**Important Note:** Quantum teleportation transmits the *state* (the information α and β) of the qubit, not the physical qubit particle itself. Alice's original qubit will be destroyed (due to measurement) in the process.

### The Setup

*   Alice has **two** qubits:
    1.  The original qubit |ψ⟩ she wants to send.
    2.  Her half of the shared Bell pair |β₀₀⟩.
*   Bob has **one** qubit:
    1.  His half of the shared Bell pair |β₀₀⟩.

The total initial state of the three-qubit system (Qubit 1: Alice's |ψ⟩, Qubit 2: Alice's |β₀₀⟩ half, Qubit 3: Bob's |β₀₀⟩ half) is:

```math
|\Psi_{initial}\rangle = |\psi\rangle \otimes |\beta_{00}\rangle
```

Let's expand this:

```math
|\Psi_{initial}\rangle = (\alpha|0\rangle_1 + \beta|1\rangle_1) \otimes \frac{1}{\sqrt{2}}(|00\rangle_{23} + |11\rangle_{23})
```

```math
|\Psi_{initial}\rangle = \frac{1}{\sqrt{2}} \left[ \alpha|0\rangle_1(|00\rangle_{23} + |11\rangle_{23}) + \beta|1\rangle_1(|00\rangle_{23} + |11\rangle_{23}) \right]
```

```math
|\Psi_{initial}\rangle = \frac{1}{\sqrt{2}} \left[ \alpha|000\rangle_{123} + \alpha|011\rangle_{123} + \beta|100\rangle_{123} + \beta|111\rangle_{123} \right]
```

*(Simpler Explanation: We've just written down the combined state of Alice's two qubits and Bob's one qubit before any operations begin. The subscripts 1, 2, 3 denote the first, second, and third qubit, respectively. Qubits 1 and 2 belong to Alice, Qubit 3 belongs to Bob).*

### The Protocol Steps
>Image[TODO]
1.  **Alice's CNOT Gate:** Alice applies a Controlled-NOT (CNOT) gate.
    *   Control Qubit: Her original qubit |ψ⟩ (Qubit 1).
    *   Target Qubit: Her half of the Bell pair (Qubit 2).
    *(Simpler Explanation: This gate entangles Alice's original qubit with her part of the shared entangled pair. If her first qubit is |1⟩, it flips her second qubit.)*

    Applying CNOT<0xE2><0x82><0x91A (CNOT on Alice's qubits 1 and 2) to $|\Psi_{initial}\rangle$:
    *   |000⟩ → |000⟩ (Control 0, target unchanged)
    *   |011⟩ → |011⟩ (Control 0, target unchanged)
    *   |100⟩ → |110⟩ (Control 1, target 0 flips to 1)
    *   |111⟩ → |101⟩ (Control 1, target 1 flips to 0)

    The state becomes $|\Psi_1\rangle$:
    ```math
    |\Psi_1\rangle = \frac{1}{\sqrt{2}} \left[ \alpha|000\rangle + \alpha|011\rangle + \beta|110\rangle + \beta|101\rangle \right]
    ```

2.  **Alice's Hadamard Gate:** Alice applies a Hadamard (H) gate to her *first* qubit (the original |ψ⟩ qubit).
    *(Simpler Explanation: This transforms her first qubit, preparing it for measurement in a way that helps reveal information about the original state |ψ⟩).*

    Applying H on the first qubit (H ⊗ I ⊗ I) to $|\Psi_1\rangle$:
    *   H|0⟩ = (1/√2)(|0⟩ + |1⟩)
    *   H|1⟩ = (1/√2)(|0⟩ - |1⟩)

    The state becomes $|\Psi_2\rangle$:
    ```math
    \begin{align*} |\Psi_2\rangle = \frac{1}{\sqrt{2}} \bigg[ &\alpha \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)|00\rangle + \alpha \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)|11\rangle \\ + &\beta \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)|10\rangle + \beta \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)|01\rangle \bigg] \end{align*}
    ```
    *(Combining the 1/√2 factors)*
    ```math
    \begin{align*} |\Psi_2\rangle = \frac{1}{2} \bigg[ &\alpha(|000\rangle + |100\rangle) + \alpha(|011\rangle + |111\rangle) \\ + &\beta(|010\rangle - |110\rangle) + \beta(|001\rangle - |101\rangle) \bigg] \end{align*}
    ```

3.  **Rearrange Terms:** Now, the crucial step is to regroup the terms based on the state of *Alice's two qubits* (Qubits 1 and 2). This will show us what state Bob's qubit (Qubit 3) is left in for each possible measurement outcome for Alice.

    ```math
    \begin{align*} |\Psi_2\rangle = \frac{1}{2} \bigg[ &|00\rangle_{12} (\alpha|0\rangle_3 + \beta|1\rangle_3) \\ + &|01\rangle_{12} (\alpha|1\rangle_3 + \beta|0\rangle_3) \\ + &|10\rangle_{12} (\alpha|0\rangle_3 - \beta|1\rangle_3) \\ + &|11\rangle_{12} (\alpha|1\rangle_3 - \beta|0\rangle_3) \bigg] \end{align*}
    ```
    *(Simpler Explanation: We've rewritten the same state, but now we've grouped it by the possible states Alice might measure on her two qubits: |00⟩, |01⟩, |10⟩, or |11⟩. Notice how Bob's qubit (the third one) looks different depending on what Alice has.)*

4.  **Alice's Measurement:** Alice measures her two qubits (Qubit 1 and Qubit 2). She will get one of four possible classical results: 00, 01, 10, or 11, each with a probability of 1/4 (assuming |ψ⟩ is normalized). The act of measurement collapses the state of Bob's qubit (Qubit 3) as follows:

    *   If Alice measures **00**: Bob's qubit is in state $(\alpha|0\rangle + \beta|1\rangle)$. This is exactly $|\psi\rangle$.
    *   If Alice measures **01**: Bob's qubit is in state $(\alpha|1\rangle + \beta|0\rangle)$. This is like $|\psi\rangle$ but with the basis states flipped (Pauli-X operation).
    *   If Alice measures **10**: Bob's qubit is in state $(\alpha|0\rangle - \beta|1\rangle)$. This is like $|\psi\rangle$ but with a phase flip on the |1⟩ component (Pauli-Z operation).
    *   If Alice measures **11**: Bob's qubit is in state $(\alpha|1\rangle - \beta|0\rangle)$. This requires both a basis flip (X) and a phase flip (Z).

5.  **Classical Communication:** Alice sends her two classical bits (the result of her measurement) to Bob over the classical channel.

6.  **Bob's Correction Operations:** Bob receives the two classical bits from Alice and performs a specific operation on *his* qubit (Qubit 3) to recover the original state |ψ⟩.

    *   If Bob receives **00**: He does nothing (applies the Identity gate, I). His state is already $\alpha|0\rangle + \beta|1\rangle = |\psi\rangle$.
    *   If Bob receives **01**: He applies the Pauli-X gate (bit flip). $X(\alpha|1\rangle + \beta|0\rangle) = \alpha|0\rangle + \beta|1\rangle = |\psi\rangle$.
    *   If Bob receives **10**: He applies the Pauli-Z gate (phase flip). $Z(\alpha|0\rangle - \beta|1\rangle) = \alpha|0\rangle - (-\beta|1\rangle) = \alpha|0\rangle + \beta|1\rangle = |\psi\rangle$.
    *   If Bob receives **11**: He applies first Z then X (or X then Z, as XZ = iY, ZY = -iY; the order matters up to a global phase, which is usually irrelevant). $X[Z(\alpha|1\rangle - \beta|0\rangle)] = X[\alpha|1\rangle - (-\beta|0\rangle)] = X(\alpha|1\rangle + \beta|0\rangle) = \alpha|0\rangle + \beta|1\rangle = |\psi\rangle$.

**Outcome:** After Bob performs the appropriate correction based on Alice's classical message, his qubit is now in the exact state $|\psi\rangle$ that Alice originally intended to send. The quantum information has been teleported!

## Method 2: Decimal State Notation (Brief Overview)

An alternative way to track the state using decimal notation, which can sometimes simplify calculations involving multiple qubits.

*   Assign weights to qubit lines, usually starting from the bottom (Least Significant Bit - LSB):
    *   Bottom line: Weight 1 (2⁰)
    *   Middle line: Weight 2 (2¹)
    *   Top line: Weight 4 (2²)
    *   (And so on: 8, 16...)
*   A state like |110⟩ (binary) would be represented as decimal 6 (since 4\*1 + 2\*1 + 1\*0 = 6). So we'd write |6⟩.
*   Quantum gates then have specific actions on these decimal states. For example:
    *   **Hadamard on qubit 'k' (weight 2^k):** Acts as $H(|j\rangle) = \frac{1}{\sqrt{2}}(|j\rangle + (-1)^{j_k}|j \oplus 2^k\rangle)$, where $j_k$ is the k-th bit of j. In the decimal notation, H on weight `w` acts on state `|j⟩` to produce a superposition involving `|j⟩` and `|j XOR w⟩` with potential phase flips.
    *   **CNOT (control 'c', target 't'):** Acts as $CNOT |j\rangle = |j \oplus (j_c \cdot 2^t)\rangle$. In decimal notation, if the control qubit `c` (weight `wc`) is ON in state `|j⟩`, then the state transforms to `|j XOR wt⟩`, where `wt` is the weight of the target qubit.

The operations for CNOT and Hadamard in this decimal form (e.g., X(4,6) for CNOT, H(0,4) for Hadamard). While powerful, fully applying this to the teleportation circuit requires careful tracking of the decimal states and how they transform under each gate, which can be complex for beginners compared to the standard notation shown above. However, it confirms the same final result.

**Summary Table:**

| Alice Measures | Bob's State Before Correction | Bob Applies | Bob's Final State |
| :------------- | :---------------------------- | :---------- | :---------------- |
| 00             | α|0⟩ + β|1⟩                  | I           | α|0⟩ + β|1⟩ (= |ψ⟩) |
| 01             | α|1⟩ + β|0⟩                  | X           | α|0⟩ + β|1⟩ (= |ψ⟩) |
| 10             | α|0⟩ - β|1⟩                  | Z           | α|0⟩ + β|1⟩ (= |ψ⟩) |
| 11             | α|1⟩ - β|0⟩                  | X then Z    | α|0⟩ + β|1⟩ (= |ψ⟩) |