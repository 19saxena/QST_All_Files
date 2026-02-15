# Appendix A — Numerical Diagnostics and Metrics

This appendix summarises the quantitative metrics used to compare
classical solutions, simulated HHL outputs, and tomography-based reconstructions.

---

## Linear System Setup

We consider a Hermitian system:

A x = b

where:
- A ∈ ℂ^{4×4}, Hermitian
- b ∈ ℂ^4
- x_classical = A^{-1} b
- x_q denotes the quantum (HHL or tomography) estimate

All vectors are normalised when computing state-level comparisons.

---

## 1. L2 Vector Error

Measures absolute deviation between classical and quantum solutions:

‖x_q − x_classical‖₂

Smaller values indicate better amplitude-level agreement.

---

## 2. Relative Error

Normalised deviation:

‖x_q − x_classical‖₂ / ‖x_classical‖₂

Useful for scale-invariant comparison across different systems.

---

## 3. Residual Norm

Measures how well the quantum solution satisfies the linear system:

‖A x_q − b‖₂

This is a physically meaningful diagnostic since HHL aims to approximate A^{-1}b.

---

## 4. Fidelity (State Reconstruction)

For normalised states ψ_est and ψ_true:

F = |⟨ψ_est | ψ_true⟩|²

Fidelity ranges from 0 to 1.
Values close to 1 indicate near-identical quantum states up to global phase.

Before computing fidelity, global phase alignment is performed.

---

## 5. Phase Alignment

Since quantum states are defined up to a global phase,
the estimate x_q is aligned using:

x_q ← x_q · exp(−i arg(⟨x_q | x_classical⟩))

This ensures fair amplitude-level comparison.

---

## Interpretation

- Low L2 and residual norms confirm correct inversion behaviour.
- High fidelity confirms accurate state reconstruction.
- Discrepancies indicate numerical instability, scaling limitations,
  or tomography reconstruction errors.
