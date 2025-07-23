# 🧠 Problem 01: Grover's Search Algorithm

## 🧩 Problem Description

Grover’s algorithm solves unstructured search problems faster than any classical algorithm. Given a function that returns `1` for the correct item and `0` for all others, Grover’s algorithm finds the marked item in `O(√N)` time.

In this example, we use Grover's algorithm on a 2-qubit system to find the target state `|11⟩` (decimal 3).

---

## 🧠 Quantum Steps

1. **Initialization**: Apply Hadamard gates to all qubits to create superposition.
2. **Oracle**: Flip the phase of the target state `|11⟩`.
3. **Diffuser**: Invert about the average amplitude.
4. **Measurement**: Collapse the system and observe the target with high probability.

---

## 🔧 Tools Used

- Qiskit
- Aer simulator (`qasm_simulator`)
- matplotlib for result visualization

---

## 🖼️ Quantum Circuit

Here’s the circuit structure for a single iteration of Grover’s algorithm (for `|11⟩`):

![Grover Circuit](images/grover_circuit.png)

> Oracle = `CZ` gate  
> Diffuser = Hadamard + X + multi-controlled Z + X + Hadamard

---

## 📈 Simulation Result

The histogram below shows that the state `|11⟩` is observed with the highest probability after one Grover iteration.

> Run the notebook in Colab to reproduce this.

---

## 📎 Files

- `grover_search.ipynb` – Complete Qiskit code
- `images/grover_circuit.png` – Quantum circuit diagram
- `requirements.txt` – Required Python packages

---

## 🚀 Run in Google Colab

Click below to open and run this notebook in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/quantum-computing-portfolio/blob/main/problems/01_grover_search/grover_search.ipynb)

> Replace `your-username` with your GitHub ID.

---

## 📚 References

- [Qiskit Textbook – Grover’s Algorithm](https://qiskit.org/textbook/ch-algorithms/grover.html)
- [IBM Quantum Lab](https://quantum-computing.ibm.com/)
