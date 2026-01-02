# Emergent Holonomy from Local Field Mismatch

This repository accompanies the paper  
**“Emergent Holonomy from Local Field Mismatch”** (Zenodo preprint, 2026).

It implements a fully classical, self-consistent transport mechanism on a
two-dimensional alpha / hexagonal tessellation, demonstrating how **local
field mismatch generates coherent closed-loop holonomy**, with **integer-selective
resonance** emerging from purely geometric feedback.

No randomness, quantum postulates, or stochastic assumptions are introduced.

---

## Core Result

We demonstrate that:

- Local **radial (spoke) mismatch** predicts **closed-loop (ring) holonomy**
  in a *cross-channel* manner.
- A self-consistent **fixed-point torsion–holonomy closure** converts mismatch
  into coherent loop transport.
- The response exhibits a **non-monotone optimum** in the feedback strength α.
- **Integer-selective resonance** emerges when the path-ordered transport axis
  winds by an integer \(N_\star\) along the loop perimeter.
- The integer **\(N_\star = 777\)** produces the strongest, sharpest, and most
  reproducible enhancement across seeds and lattice realizations.

These effects persist under:
- Full Lloyd-relaxed hexagonal lattices
- Cross-channel controls (spoke mismatch → ring holonomy)
- Multiple random seeds
- Neutral integer controls

---

## Conceptual Structure

At each lattice site:

1. A complex internal field \( \phi_i \) is relaxed on the Voronoi graph.
2. Residual mismatch defines a **local incoherence measure**.
3. Transport along edges is represented by **SU(2) rotations**.
4. Closed-loop holonomy is accumulated along neighbor rings.
5. Transport is updated self-consistently via under-relaxed fixed-point iteration.

Crucially, mismatch and holonomy are **measured on distinct geometric channels**,
eliminating tautological feedback.

---

## Repository Contents

- `hex_ew_toy.py` (or equivalent main script)  
  Core simulation harness.
- CSV outputs  
  Per-loop and aggregated statistics (Pearson/Spearman correlations, holonomy,
  coherence diagnostics).
- Paper figures are generated directly from these outputs.

(Exact filenames may evolve; see code comments.)

---

## How to Run

### Requirements
- Python ≥ 3.9
- `numpy`, `scipy`, `pandas`, `matplotlib`

### Example Run
```bash
python hex_ew_toy.py \
  --N 300 \
  --alpha 1.10 \
  --Nstar 777 \
  --seeds 41 42 43 \
  --lloyd-iters 180 \
  --fp-iters 8 \
  --under-relax 0.35
