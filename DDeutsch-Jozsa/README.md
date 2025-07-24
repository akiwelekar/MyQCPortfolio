# 🧠 Deutsch–Jozsa Algorithm

## 🔍 Problem Statement

The **Deutsch–Jozsa Algorithm** determines whether a Boolean function  
`f(x): {0,1}^n → {0,1}` is:

- **Constant**: same output for all inputs  
- **Balanced**: outputs 0 for half inputs, 1 for the other half

Classically, it may require up to `2^(n-1) + 1` evaluations.  
**Quantum algorithm does it with a single query.**

---

## ⚙️ Algorithm Overview

1. Initialize input qubits to `|0⟩` and one output qubit to `|1⟩`.
2. Apply Hadamard gates to all qubits.
3. Apply the oracle `Uf`, which flips phase based on `f(x)`.
4. Apply Hadamard to input qubits again.
5. Measure the input qubits.

---

## 🧪 2-Qubit Example

- Function `f(x)` is **balanced**: `f(00)=0, f(01)=1, f(10)=1, f(11)=0`

Oracle:  
```python
oracle.cx(0, 2)
oracle.cx(1, 2)

     ┌───┐                     ┌───┐                     ┌───┐     ┌─┐
q_0: ┤ H ├──■──────────────────┤ H ├─────────────────────┤ M ├─────┤0├
     ├───┤  │                  ├───┤                     └─┬─┘     └╥┘
q_1: ┤ H ├──┼────■─────────────┤ H ├───────────────────────┼───────╫─
     ├───┤  │    │             ├───┤                       │       ║
q_2: ┤ X ├──┼────┼────■────────┤   ├───────────────────────┼───────╫─
     └───┘┌─┴─┐┌─┴─┐  │        │   │                       │       ║
         ┤ H ├┤ X ├───■────────┤   ├───────────────────────┼───────╫─
         └───┘└───┘            └───┘                       │       ║
                                                        ┌─┴─┐   ┌─╨─┐
c: 2/═══════════════════════════════════════════════════╡ 0 ╞═══╡ 1 ╞
                                                        └───┘   └───┘
