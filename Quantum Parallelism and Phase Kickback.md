## Introduction to Quantum Algorithms

1.  **Quantum Parallelism & Phase Kickback**

Before diving into specific algorithms, we'll start with two crucial features that are used in many of them:
*   **Quantum Parallelism**
*   **Phase Kickback**

---

## Quantum Parallelism:

**What is it?**

Quantum Parallelism is the ability of a quantum computer to **execute multiple computations or evaluate a function for many different inputs simultaneously** within a single quantum state.

> **Simpler Explanation:** Imagine you have a task, like calculating a mathematical function `f(x)`, and you want to find the answer for many different values of `x` (say, x=0, x=1, x=2, ... up to x=7). A classical computer would usually calculate `f(0)`, then `f(1)`, then `f(2)`, and so on, one after the other. A quantum computer, using parallelism, can effectively calculate `f(x)` for *all* these `x` values *at the same time* using the principles of superposition.

**Why is it important?**

This allows quantum computers to potentially solve certain complex problems **exponentially faster** than classical computers.

**How does it work (Setup)?**

The key is the **Hadamard gate (H)** and the principle of **superposition**.

1.  **Input State:** We often start with multiple qubits initialized to the state `|0⟩`. If we have `n` qubits, the state is $ |0⟩ \otimes |0⟩ \otimes ... \otimes |0⟩ $, which we can write compactly as $|0⟩^{\otimes n}$ or simply $|00...0\rangle$.

2.  **Applying Hadamard Gates:** We apply a Hadamard gate to *each* of the `n` qubits. This operation is represented by $H^{\otimes n}$.

    *   **Circuit Diagram:**
        ```
           |0⟩ ---- H ----
           |0⟩ ---- H ----
            .       .
            .       .
           |0⟩ ---- H ----
        ```
        Or more compactly:
        ```
           |0⟩^n --- H^⊗n --- Output State
        ```
3.  **Output State (Superposition):** Applying $H^{\otimes n}$ to $|0\rangle^{\otimes n}$ creates an **equal superposition** of *all* $N = 2^n$ possible computational basis states.

    *   The resulting state is:
        $$ |\psi\rangle = \frac{1}{\sqrt{N}} \sum_{x=0}^{N-1} |x\rangle $$
        where $N = 2^n$, and $|x\rangle$ represents each basis state from $|00...0\rangle$ to $|11...1\rangle$.

    *   **Example (n=2 qubits):**
        *   Input: $|00\rangle$
        *   Operation: $H \otimes H$
        *   Output:
            $$ \frac{1}{\sqrt{4}} \sum_{x=0}^{3} |x\rangle = \frac{1}{2} (|0\rangle + |1\rangle + |2\rangle + |3\rangle)_{\text{decimal}} = \frac{1}{2} (|00\rangle + |01\rangle + |10\rangle + |11\rangle)_{\text{binary}} $$
        *(Decimal notation 0, 1, 2, 3 as shorthand for the binary states 00, 01, 10, 11)*.

**The Parallelism Part:**

Once you have this superposition state $\frac{1}{\sqrt{N}} \sum |x\rangle$, if you apply a quantum operation (Unitary gate $U_f$) that computes a function $f(x)$ (usually acting like $|x\rangle|y\rangle \xrightarrow{U_f} |x\rangle|y \oplus f(x)\rangle$), this single operation $U_f$ acts on the *entire superposition* simultaneously. The result encodes $f(x)$ for all values of $x$ present in the superposition. This is the essence of quantum parallelism.

**General Hadamard Transformation (Important Concept):**

What if the input isn't $|0\rangle^{\otimes n}$ but some other basis state $|x\rangle$? (Where $|x\rangle$ is an n-qubit binary string like $|101\rangle$).

*   **Input:** $|x\rangle$ (an n-qubit basis state or *string*)
*   **Operation:** $H^{\otimes n}$
*   **Output:**
    $$ H^{\otimes n} |x\rangle = \frac{1}{\sqrt{N}} \sum_{z=0}^{N-1} (-1)^{x \cdot z} |z\rangle $$

    *   Here, $N=2^n$ again.
    *   The sum is over all $N$ possible output basis states $|z\rangle$.
    *   $(-1)^{x \cdot z}$ is a **phase factor** (+1 or -1).
    *   $x \cdot z$ is the **binary dot product modulo 2**.

        > **Binary Dot Product (Modulo 2):**
        > To calculate $x \cdot z$:
        > 1. Write both $x$ and $z$ as n-bit binary strings (e.g., if n=3, $x=5 \rightarrow 101$, $z=6 \rightarrow 110$).
        > 2. Multiply them bitwise: $(101) \cdot (110) \rightarrow (1*1, 0*1, 1*0) = (1, 0, 0)$.
        > 3. Sum the results: $1 + 0 + 0 = 1$.
        > 4. Take the sum modulo 2: $1 \pmod 2 = 1$.
        > So, for $x=5, z=6$, $x \cdot z = 1$. The phase factor is $(-1)^1 = -1$.

**Connecting the two forms:**

*   If the input is $x = 0$ (i.e., $|00...0\rangle$), then $x \cdot z = 0 \cdot z = 0$ for all $z$.
*   The phase factor becomes $(-1)^0 = +1$.
*   The formula reduces to $H^{\otimes n} |0\rangle^{\otimes n} = \frac{1}{\sqrt{N}} \sum_{z=0}^{N-1} (+1) |z\rangle$, which is the equal superposition we saw first.

**Why is the general form important?**

The phase factor $(-1)^{x \cdot z}$ is critical. It shows how the input state $|x\rangle$ influences the *phases* of the terms in the output superposition. This phase encoding is heavily used in algorithms like Deutsch-Jozsa, Bernstein-Vazirani, and Simon's algorithm.

---

## Phase Tables (Tool for understanding $H^{\otimes n}$)

Calculating $(-1)^{x \cdot z}$ for every term can be tedious. We are introducing "Phase Tables" as a visual aid, especially for small numbers of qubits (n=2 and n=3 shown).

**Table Structure:**

*   **Rows:** Represent the input state $|x\rangle$. Labeled with decimal value and its binary string.
*   **Columns:** Represent the output basis state $|z\rangle$. Labeled with decimal value.
*   **Entries:** The sign (+ or -) corresponding to the phase factor $(-1)^{x \cdot z}$.

**How to Fill the Table (Recursive Method):**

Let's focus on filling row `x` (input state).

1.  **LSB Rule:** Look at the *Least Significant Bit* (rightmost bit) of the binary representation of `x`.
    *   If LSB is 0, the row starts `++` (two entries).
    *   If LSB is 1, the row starts `+-`.
2.  **Next Bit Rule:** Move to the *next bit to the left* in `x`.
    *   If this bit is 0: **Repeat** the pattern of signs you've generated so far.
    *   If this bit is 1: **Repeat** the pattern, but **flip all the signs** in the repeated part.

**Example: $H^{\otimes 2}$ Table (Inputs/Outputs 0 to 3)**

| x (binary) | x (dec) | z=0 | z=1 | z=2 | z=3 | How it's built                               |
| :--------- | :------ | :-: | :-: | :-: | :-: | :----------------------------------------- |
| 00         | 0       | +   | +   | +   | +   | LSB=0 -> `++`. Next=0 -> repeat `++`.        |
| 01         | 1       | +   | -   | +   | -   | LSB=1 -> `+-`. Next=0 -> repeat `+-`.        |
| 10         | 2       | +   | +   | -   | -   | LSB=0 -> `++`. Next=1 -> repeat `++` flipped (`--`). |
| 11         | 3       | +   | -   | -   | +   | LSB=1 -> `+-`. Next=1 -> repeat `+-` flipped (`-+`). |



**Example: $H^{\otimes 3}$ Table (Inputs/Outputs 0 to 7)**

| x (binary) | x (dec) | z=0 | z=1 | z=2 | z=3 | z=4 | z=5 | z=6 | z=7 | How it's built                                                              |
| :--------- | :------ | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-------------------------------------------------------------------------- |
| **000**    | **0**   | +   | +   | +   | +   | +   | +   | +   | +   | LSB $x_0=0 \rightarrow$ `++`. Next $x_1=0 \rightarrow$ repeat `++` $\rightarrow$ `++++`. Next $x_2=0 \rightarrow$ repeat `++++` $\rightarrow$ `++++++++`. |
| **001**    | **1**   | +   | -   | +   | -   | +   | -   | +   | -   | LSB $x_0=1 \rightarrow$ `+-`. Next $x_1=0 \rightarrow$ repeat `+-` $\rightarrow$ `+-+-`. Next $x_2=0 \rightarrow$ repeat `+-+-` $\rightarrow$ `+-+-+-+-`. |
| **010**    | **2**   | +   | +   | -   | -   | +   | +   | -   | -   | LSB $x_0=0 \rightarrow$ `++`. Next $x_1=1 \rightarrow$ repeat `++` flipped $\rightarrow$ `++--`. Next $x_2=0 \rightarrow$ repeat `++--` $\rightarrow$ `++--++--`. |
| **011**    | **3**   | +   | -   | -   | +   | +   | -   | -   | +   | LSB $x_0=1 \rightarrow$ `+-`. Next $x_1=1 \rightarrow$ repeat `+-` flipped $\rightarrow$ `+--+`. Next $x_2=0 \rightarrow$ repeat `+--+` $\rightarrow$ `+--++--+`. |
| **100**    | **4**   | +   | +   | +   | +   | -   | -   | -   | -   | LSB $x_0=0 \rightarrow$ `++`. Next $x_1=0 \rightarrow$ repeat `++` $\rightarrow$ `++++`. Next $x_2=1 \rightarrow$ repeat `++++` flipped $\rightarrow$ `++++----`. |
| **101**    | **5**   | +   | -   | +   | -   | -   | +   | -   | +   | LSB $x_0=1 \rightarrow$ `+-`. Next $x_1=0 \rightarrow$ repeat `+-` $\rightarrow$ `+-+-`. Next $x_2=1 \rightarrow$ repeat `+-+-` flipped $\rightarrow$ `+-+--+-+`. |
| **110**    | **6**   | +   | +   | -   | -   | -   | -   | +   | +   | LSB $x_0=0 \rightarrow$ `++`. Next $x_1=1 \rightarrow$ repeat `++` flipped $\rightarrow$ `++--`. Next $x_2=1 \rightarrow$ repeat `++--` flipped $\rightarrow$ `++----++`. |
| **111**    | **7**   | +   | -   | -   | +   | -   | +   | +   | -   | LSB $x_0=1 \rightarrow$ `+-`. Next $x_1=1 \rightarrow$ repeat `+-` flipped $\rightarrow$ `+--+`. Next $x_2=1 \rightarrow$ repeat `+--+` flipped $\rightarrow$ `+--+-++-`. |


**Using the Table:**

To find the state $H^{\otimes n} |x\rangle$, look at row `x`. The signs in that row give you the phase factors for the corresponding $|z\rangle$ terms in the superposition $\frac{1}{\sqrt{N}} \sum_{z} (\text{sign}) |z\rangle$.

*   Example: $H^{\otimes 2} |3\rangle$: Look at row 3 (11). Signs are `+ - - +`.
    $$ H^{\otimes 2} |3\rangle = \frac{1}{\sqrt{4}} [ (+1)|0\rangle + (-1)|1\rangle + (-1)|2\rangle + (+1)|3\rangle ] = \frac{1}{2} (|00\rangle - |01\rangle - |10\rangle + |11\rangle) $$

**Shortcut for Binary Dot Product:**

Another way to find the sign $(-1)^{x \cdot z}$:

1.  Write `x` and `z` as sums of powers of 2 (e.g., $13 = 8+4+1$).
2.  Identify the powers of 2 that are present in *both* sums (common ON states).
3.  Count the number of common terms, let it be `k`.
4.  The phase is $(-1)^k$.

*   Example: $x=12 = 8+4$, $z=15 = 8+4+2+1$. Common terms are 8 and 4 (two terms, k=2). Phase = $(-1)^2 = +1$.
*   Example: $x=13 = 8+4+1$, $z=10 = 8+2$. Common term is 8 (one term, k=1). Phase = $(-1)^1 = -1$.

---

## Phase Kickback

**What is it?**

Phase kickback is a phenomenon where the phase information resulting from a controlled quantum operation, which naturally seems to affect the *target* qubit(s), gets transferred ("kicked back") to the *control* qubit(s).

**Simple Example: CNOT Gate**

*   **Setup:**
    *   Control/Data qubit: $|x\rangle$
    *   Target qubit: Prepared in state $|-\rangle = H|1\rangle = \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle)$.
    *   Circuit:
        ```
          |x⟩ -------•-------
                   |
          |1⟩ ----H--⊕----
        ```

*   **Input State:** $|x\rangle \otimes |-\rangle = \frac{1}{\sqrt{2}} |x\rangle (|0\rangle - |1\rangle)$

*   **After CNOT:**
    *   If $x=0$ (control is 0), CNOT does nothing: Output is $|0\rangle \otimes |-\rangle$.
    *   If $x=1$ (control is 1), CNOT flips the target:
        *   Input was $\frac{1}{\sqrt{2}} |1\rangle (|0\rangle - |1\rangle) = \frac{1}{\sqrt{2}} (|10\rangle - |11\rangle)$.
        *   CNOT flips target: $\frac{1}{\sqrt{2}} (|11\rangle - |10\rangle)$.
        *   Rearrange: $-\frac{1}{\sqrt{2}} (|10\rangle - |11\rangle) = -|1\rangle \otimes \frac{1}{\sqrt{2}}(|0\rangle - |1\rangle) = -|1\rangle \otimes |-\rangle$.

*   **Combined Result:** The output state can be written as:
    $$ (-1)^x |x\rangle \otimes |-\rangle $$

**Observation:**

*   The target qubit state $|-\rangle$ is unchanged (it's an eigenstate of the X operation performed by CNOT).
*   The control qubit $|x\rangle$ has acquired a phase factor $(-1)^x$ that depends on its own value. The phase was "kicked back" from the target interaction to the control.

**Generalization:**

This works for any controlled unitary $U_f$ that maps $|x\rangle|y\rangle \to |x\rangle|y \oplus f(x)\rangle$. If the target register starts in $|-\rangle$:

$$ U_f (|x\rangle \otimes |-\rangle) = (-1)^{f(x)} |x\rangle \otimes |-\rangle $$

*   **Circuit:**
    ```
        |x⟩ --------•-------- (-1)^{f(x)}|x⟩
                   |
        |-\rangle -----F--------- |-\rangle
    ```
    *(Here F represents the controlled operation based on the function f)*

**Key Idea:** The information about the function $f(x)$ is encoded as a phase factor $(-1)^{f(x)}$ on the *data register* $|x\rangle$, while the target register $|-\rangle$ remains unchanged. This is crucial for algorithms that need to extract properties of $f(x)$ without necessarily knowing the individual output values.

---

This covers the introductory concepts of Quantum Parallelism (using Hadamard gates to create superpositions for simultaneous computation) and Phase Kickback (transferring functional information as a phase onto the control/data register). These are building blocks for understanding many quantum algorithms.

## References
https://www.youtube.com/watch?v=RqNDAu1cCJg&list=PLxhaPrr4aQ9mtopjwgcYaZHndp5gvjP_V
https://learning.quantum.ibm.com/course/fundamentals-of-quantum-algorithms/quantum-query-algorithms#further-remarks-on-the-phase-kickback