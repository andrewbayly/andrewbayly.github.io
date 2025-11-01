# In Standard Wireworld, XOR is a Universal Gate Primitive

At first, the title may seem surprising. Surely not — we know that in **Boolean Logic**, the symmetric $\text{XOR}$ operation is **not universal**. That's true, but Wireworld is a **Cellular Automaton**, and the physics of signal propagation and collision are just as important as the abstract Boolean functions. We must consider how logic elements are **synchronized in time**.

Our discovery is that the physics of the **Standard Wireworld** ruleset allows a $\text{XOR}$ gate pattern to function as a universal primitive when combined with precise timing.

We demonstrate this by building an **AND-NOT** gate ($A \land \neg B$), a known universal gate, using only **two $\text{XOR}$ primitives** and simple conductive wires (delay lines).



## The Minimal Universal Circuit

The circuit above is composed of two $\text{XOR}$ gates: the lower gate ($\mathbf{p}$) and the upper gate ($\mathbf{q}$). The signal splitter for $\mathbf{B}$ is a trivial wire fork, which is considered part of the routing infrastructure, not a dedicated logic gate.

Here is the breakdown of the logic for the **AND-NOT** function:

| Inputs | Desired $\text{AND-NOT}$ Output | Circuit Behavior |
| :---: | :---: | :--- |
| $\mathbf{A=H}, \mathbf{B=L}$ | **HIGH** | $\mathbf{B}$ is **LOW**. Signal $\mathbf{A}$ is unimpeded. It passes through $\mathbf{p}$ and $\mathbf{q}$, and arrives at the output **HIGH**. |
| $\mathbf{A=L}, \mathbf{B=L}$ | **LOW** | No signals are present. Output is **LOW**. |
| $\mathbf{A=H}, \mathbf{B=H}$ | **LOW** | $\mathbf{B}$ is **HIGH**. $\mathbf{B}$ splits into $\mathbf{B_1}$ and $\mathbf{B_2}$. At gate $\mathbf{p}$, $\mathbf{B_1}$ arrives first and passes through, simultaneously **blocking $\mathbf{A}$** due to the timing offset. The passing $\mathbf{B_1}$ signal then meets $\mathbf{B_2}$ at gate $\mathbf{q}$. The synchronous arrival of $\mathbf{B_1}$ and $\mathbf{B_2}$ at $\mathbf{q}$ results in **$\text{XOR}$ cancellation** ($\text{HIGH} \oplus \text{HIGH} = \text{LOW}$), and the output is **LOW**. |
| $\mathbf{A=L}, \mathbf{B=H}$ | **LOW** | Only $\mathbf{B}$ is **HIGH**. As above, $\mathbf{B}$ splits into $\mathbf{B_1}$ and $\mathbf{B_2}$. $\mathbf{B_1}$ passes through $\mathbf{p}$ and meets $\mathbf{B_2}$ at $\mathbf{q}$. As above, the precise synchronous arrival of the $\mathbf{B}$ signals at $\mathbf{q}$ causes them to **cancel out**. Output is **LOW**. |

---

### The Power of $\text{XOR}$

This circuit works because our $\text{XOR}$ gate, when constructed in Wireworld, is engineered to utilize two essential, timing-dependent modes:

1.  **Timing-Dependent Blocking (Inhibition):** When inputs are offset by a precise time (e.g., $\mathbf{B_1}$ arrives before $\mathbf{A}$ at gate $\mathbf{p}$), the first signal passes through and puts the gate into a **refractory state**, causing the second signal ($\mathbf{A}$) to be completely **blocked** (annihilated) or diverted by the gate's internal geometry.
2.  **$\text{XOR}$ Mode (Cancellation):** When inputs ($\mathbf{B_1}$ and $\mathbf{B_2}$) are precisely synchronized, the gate acts as an **Inhibitor**, converting the $\text{HIGH} \oplus \text{HIGH}$ state into a physical **LOW** output via signal collision/annihilation. This is crucial for the $\neg B$ part of the logic.

This is what makes the $\text{XOR}$ gate **special**: the necessary informational asymmetry (the $\text{NOT}$ operation) is not a separate gate, but a **mode of operation** inherent in the gate's physical construction and timing sensitivity.

---

## Conclusion

We have shown that in the canonical **Standard Wireworld** CA, the $\text{XOR}$ gate — when combined with precise signal timing — is sufficient to build an **AND-NOT** gate using only two instances. In this way, we prove that the $\text{XOR}$ primitive can be considered **Universal**, a major step toward establishing the absolute minimal logical basis for Turing Completeness in Standard Wireworld.