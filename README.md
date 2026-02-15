# QST_All_Files
# Quantum State Tomography and Algorithm Validation Framework

## Overview

This project consolidates Assignments 1–5 into a reproducible quantum algorithm validation pipeline. 

The work explores:

1. Quantum State Tomography (QST)
2. Scalable surrogate modelling for multi-qubit systems
3. Quantum channel classification
4. HHL linear system solving
5. Tomography-assisted verification of quantum algorithms

The objective is to build an auditable workflow that connects state reconstruction, scalability benchmarking, channel calibration, and algorithm verification.

---

## Project Structure

data/ → Measurement datasets and benchmark CSVs
models/ → Serialized checkpoints (.pt)
notebooks/ → Cleaned assignment notebooks
src/ → Modular Python implementations
results/ → Plots, tables, and figures
README.md → Primary documentation


---

## Methodology

### 1. Quantum State Tomography
Implemented Pauli-based tomography for single and multi-qubit systems. 
Reconstructed density matrices from simulated measurement statistics.

Metrics used:
- Fidelity
- Trace distance
- L2 norm error

---

### 2. Scalable Surrogate Model
Developed an extendable n-qubit surrogate to benchmark scalability.
Measured:
- Mean fidelity vs qubits
- Runtime growth
- Variance across seeds

Observed exponential state dimension growth limits beyond 5 qubits.

---

### 3. Quantum Channel Classification
Built a lightweight Choi-matrix feature extractor.
Trained a classical model to classify:
- Depolarizing channels
- Amplitude damping channels

Demonstrated calibration-time inference workflow.

---

### 4. HHL Linear System Solver
Rebuilt HHL via explicit eigen-decomposition (modern Qiskit deprecates built-in HHL).
Compared:
- Classical solution
- Simulated HHL output
- Tomography-based reconstruction

Metrics:
- L2 vector error
- Relative error
- Residual norm

---

## Results Summary

Scaling trends:
- Fidelity decreases with increasing qubit count.
- Runtime increases due to exponential Hilbert space growth.
- Tomography overhead must remain efficient to preserve algorithmic advantage.

HHL validation:
- Simulated HHL aligns with classical baseline.
- Tomography surrogate reconstructs solution within tolerance.

---

## Key Takeaways

- Efficient tomography is critical for validating quantum algorithms.
- Exponential scaling remains the primary bottleneck.
- Hybrid quantum-classical workflows are currently the most practical path forward.

---

## Future Directions

- Classical shadows for reduced measurement overhead
- Noise-aware reconstruction models
- Hardware calibration integration
- Sparse system HHL extensions
