### What is Superdense Coding?
Superdense coding is a fascinating quantum protocol. At its core, it achieves something that seems impossible classically:

*   **Goal:** To transmit **two (2) classical bits** of information (like 00, 01, 10, or 11).
*   **Method:** By sending only **one (1) qubit** over a quantum channel.
*   **Requirement:** The sender (Alice) and receiver (Bob) must **pre-share an entangled pair** of qubits (specifically, a Bell state).

**Key Idea:** Superdense coding leverages the power of quantum entanglement to "pack" two classical bits worth of information into a single qubit.

#### Relationship to Quantum Teleportation
> Superdense Coding is the **"Reverse process of Quantum Teleportation"**.

Let's quickly recall Quantum Teleportation:
*   **Goal:** Send 1 *qubit* of quantum information.
*   **Method:** Uses 2 *classical bits* (measurement results) sent over a classical channel, along with a pre-shared entangled pair.

Now, compare this to Superdense Coding:
*   **Goal:** Send 2 *classical bits* of information.
*   **Method:** Uses 1 *qubit* sent over a quantum channel, along with a pre-shared entangled pair.

You can see the reversal:
*   Teleportation: 1 qubit → 2 classical bits (channel: classical)
*   Superdense Coding: 2 classical bits → 1 qubit (channel: quantum)

---

### The Superdense Coding Protocol (Conceptual Steps)

While the video jumps into the circuit, let's outline the conceptual steps involving our usual characters, Alice (sender) and Bob (receiver):

1.  **Preparation:** Someone (often a third party, or Alice/Bob themselves earlier) creates an entangled pair of qubits, typically the Bell state $|\beta_{00}\rangle $. One qubit is given to Alice, and the other to Bob. They might be physically separated.
2.  **Encoding (Alice):** Alice decides which two classical bits (00, 01, 10, or 11) she wants to send to Bob. Based on her choice, she applies a *specific quantum gate* (I, X, Z, or Y=iXZ, or ZX as used later in the video) *only to her qubit*. This operation changes the *overall* state of the entangled pair into one of the four Bell states.
3.  **Transmission:** Alice sends *her* manipulated qubit to Bob using a **quantum channel**.
4.  **Decoding (Bob):** Bob now possesses both qubits (his original one and the one received from Alice). He performs a specific sequence of quantum operations (essentially the reverse of Bell state creation: CNOT followed by Hadamard) on the two qubits.
5.  **Measurement:** Bob measures both qubits in the computational basis. The outcomes of these measurements directly correspond to the two classical bits Alice originally intended to send.

---

### Circuit Implementation and Mathematical Details

1.  **Bell State Preparation:**
    *   We start with two qubits in the state $|00\rangle$.
    *   Apply a Hadamard (H) gate to the first qubit.
    *   Apply a CNOT gate with the first qubit as control and the second as target.

    ```
    |0⟩ --- H --- ● --- (Alice's qubit)
               |
    |0⟩ -------⊕ --- (Bob's qubit)
    ```

    *   The resulting state is the Bell state $|\beta_{00}\rangle $:
        $$
        |\beta_{00}\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)
        $$

2.  **Encoding (Alice's Operations on her qubit):**
    *   Alice and Bob share the $|\beta_{00}\rangle $ state. Alice has the first qubit, Bob has the second.
    *   Alice wants to send two classical bits, `xy`, where `x, y ∈ {0, 1}`.
    *   She applies a gate to *her* qubit (the first one).

    | Classical Bits Alice wants to send (xy) | Gate Alice applies to her qubit (Gate ⊗ I) | Resulting Entangled State (Shared by Alice & Bob) | Bell State Name | Decimal Notation (State) |
    | :--------------------------------------: | :-----------------------------------------: | :-----------------------------------------------------: | :---------------: | :------------------------: |
    |                    00                    |                  <```math I \otimes I ```>                  |   <```math \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle) ```>    | <```math |\beta_{00}\rangle ```> |  <```math \frac{1}{\sqrt{2}} (|0\rangle + |3\rangle) ```>   |
    |                    01                    |                  <```math X \otimes I ```>                  |   <```math \frac{1}{\sqrt{2}} (|10\rangle + |01\rangle) ```>    | <```math |\beta_{01}\rangle ```> |  <```math \frac{1}{\sqrt{2}} (|2\rangle + |1\rangle) ```>   |
    |                    10                    |                  <```math Z \otimes I ```>                  |   <```math \frac{1}{\sqrt{2}} (|00\rangle - |11\rangle) ```>    | <```math |\beta_{10}\rangle ```> |  <```math \frac{1}{\sqrt{2}} (|0\rangle - |3\rangle) ```>   |
    |                    11                    |                 <```math ZX \otimes I ```>                 |   <```math \frac{1}{\sqrt{2}} (|10\rangle - |01\rangle) ```>    | <```math |\beta_{11}\rangle ```> |  <```math \frac{1}{\sqrt{2}} (|2\rangle - |1\rangle) ```>   |

    *   *Explanation:* Applying the identity `I` leaves the state as <```math |\beta_{00}\rangle ```>. Applying `X` to the first qubit transforms <```math |00\rangle \rightarrow |10\rangle ```> and <```math |11\rangle \rightarrow |01\rangle ```>, resulting in <```math |\beta_{01}\rangle ```>. Applying `Z` to the first qubit transforms <```math |00\rangle \rightarrow |00\rangle ```> and <```math |11\rangle \rightarrow -|11\rangle ```>, resulting in <```math |\beta_{10}\rangle ```>. Applying `Z` then `X` (or `Y=iXZ`) results in <```math |\beta_{11}\rangle ```>.
    *   The speaker uses the notation `I`, `X`, `Z`, `XZ` for the operations and shows the resulting Bell states.

3.  **Transmission:** Alice sends her qubit (the first qubit of the pair) to Bob.

4.  **Decoding (Bob's Operations):**
    *   Bob now has both qubits. He applies the *reverse* of the Bell state preparation circuit to the pair.
    *   Apply CNOT gate (Alice's received qubit is control, Bob's original qubit is target).
    *   Apply Hadamard (H) gate to Alice's received qubit.

    ```
    (Alice's qubit) --- ● --- H --- Measure (x)
                      |
    (Bob's qubit) -----⊕------- Measure (y)
    ```

5.  **Measurement:**
    *   Bob measures both qubits.
    *   If the initial state sent by Alice (after her encoding) was <```math |\beta_{00}\rangle ```>, Bob measures `00`.
    *   If the state was <```math |\beta_{01}\rangle ```>, Bob measures `01`.
    *   If the state was <```math |\beta_{10}\rangle ```>, Bob measures `10`.
    *   If the state was <```math |\beta_{11}\rangle ```>, Bob measures `11`.

    *(Video Reference: 13:11 - 17:34 provides the step-by-step derivation of these decoding results for each initial Bell state).*

    **Example (Decoding β₀₁):**
    *   Bob receives <```math |\beta_{01}\rangle = \frac{1}{\sqrt{2}} (|10\rangle + |01\rangle) ```>
    *   Apply CNOT: <```math \frac{1}{\sqrt{2}} (|11\rangle + |01\rangle) = \frac{1}{\sqrt{2}} (|1\rangle + |0\rangle) \otimes |1\rangle = \frac{1}{\sqrt{2}} (|+\rangle + |-\rangle) \otimes |1\rangle ```>.
    * β₀₁ <```math \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \otimes |1\rangle ```>
    *   Apply H to the first qubit: <```math H \frac{1}{\sqrt{2}} (|0\rangle + |1\rangle) \otimes |1\rangle = \frac{1}{\sqrt{2}} (H|0\rangle + H|1\rangle) \otimes |1\rangle = \frac{1}{\sqrt{2}} (\frac{|0\rangle+|1\rangle}{\sqrt{2}} + \frac{|0\rangle-|1\rangle}{\sqrt{2}}) \otimes |1\rangle = \frac{1}{2} (2|0\rangle) \otimes |1\rangle = |01\rangle ```>
    *   Measurement yields `01`.

### Decimal State Notation Approach

The speaker also introduces solving the circuit using decimal notation, which can be simpler for tracking states in simulations or specific analyses.

*   States: <```math |00\rangle \rightarrow |0\rangle, |01\rangle \rightarrow |1\rangle, |10\rangle \rightarrow |2\rangle, |11\rangle \rightarrow |3\rangle ```>.
*   Initial Bell State: <```math |\beta_{00}\rangle = \frac{1}{\sqrt{2}} (|0\rangle + |3\rangle) ```>.
*   Encoding Gates (as matrices acting on basis states 0, 1, 2, 3 or using permutation notation):
    *   `I`: Identity (0→0, 1→1, 2→2, 3→3)
    *   `X ⊗ I`: Flips the first qubit (0→2, 1→3, 2→0, 3→1). Notation: `X(0,2)X(1,3)`
    *   `Z ⊗ I`: Applies phase to states where the first qubit is 1 (0→0, 1→1, 2→-2, 3→-3). Notation: `Z(0,2)Z(1,3)` where Z(a,b) applies a phase flip to state b.
    *   `ZX ⊗ I`: Combined operation.
*   Decoding Gates:
    *   CNOT (control=1st, target=2nd): Flips second bit if first is 1 (0→0, 1→1, 2→3, 3→2). Notation: `X(2,3)`
    *   Hadamard (on 1st qubit): Applies H transformation. Notation: `H(0,2)H(1,3)`

This allows tracking the state transformation through the circuit using these decimal permutations and phase changes. For example, sending `01`:

1.  Start with <```math \frac{1}{\sqrt{2}} (|0\rangle + |3\rangle) ```>
2.  Apply `X = X(0,2)X(1,3)`: <```math \frac{1}{\sqrt{2}} (X|0\rangle + X|3\rangle) = \frac{1}{\sqrt{2}} (|2\rangle + |1\rangle) = |\beta_{01}\rangle ```>
3.  Bob receives this. Apply CNOT `X(2,3)`: <```math \frac{1}{\sqrt{2}} (X(2,3)|2\rangle + X(2,3)|1\rangle) = \frac{1}{\sqrt{2}} (|3\rangle + |1\rangle) ```> (Note: This differs from the video's derivation at 15:42, sticking to the decimal method here).
4.  Apply Hadamard `H(0,2)H(1,3)`: Requires applying the Hadamard transformation rules. This method confirms the final state corresponds to the classical bits sent.

---

### Summary

Superdense coding demonstrates how a single qubit, when part of an entangled pair, can carry two classical bits of information from Alice to Bob. This is achieved by Alice locally manipulating her qubit based on the classical bits she wants to send (effectively selecting one of the four Bell states) and then sending that single qubit to Bob, who performs joint operations and measurements to decode the information. It's a powerful example of how quantum resources enable communication advantages.