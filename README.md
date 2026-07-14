# Trainability-as-differential-information-transmission-in-variational-quantum-circuits

Code and numerical experiments accompanying the paper:

F. Ailabouni and R. Casado,
"Trainability as differential information transmission in variational quantum circuits."

The paper develops a differential-geometric framework for trainability in variational quantum circuits based on the variational Jacobian. It derives an exact modal decomposition of gradient generation in terms of Jacobian singular directions and their alignment with the learning task, and shows numerically that task-alignment diagnostics predict optimization performance far better than purely spectral quantities (Jacobian rank, largest singular value, total spectral weight).

CONTENTS

- trainability_jacobian_diagnostics.ipynb
  Single notebook that reproduces all numerical results and figures (Section 5 of the paper). It implements a lightweight NumPy state-vector simulator, the Jacobian/Fubini–Study–Hilbert–Schmidt metric tensor, the modal decomposition diagnostics, and the six validation experiments (Validation 0–V).

- figures_jacobian_qfim/
  Generated on first run; contains all figures (.pdf/.png).

- data_jacobian_qfim/
  Generated on first run; contains the data used to generate the figures (.csv).

NOTEBOOK ↔ PAPER CORRESPONDENCE

Validation 0
    Numerical-engine consistency check (Eq. 12)
    Output: sanity-check figure

Validation I
    Section 5.2
    Spectral vs. alignment suppression
    Output: Figure 1

Validation II
    Section 5.3
    DLA-equivalent circuits and Jacobian geometry
    Output: Figures 2–3

Validation III
    Section 5.4
    Scaling of spectral accessibility and alignment
    Output: Figure 4

Validation IV
    Section 5.5
    Predictive power of Jacobian diagnostics
    Output: Figure 5 and Table 1

Validation V
    Section 5.6
    Second-order effects (Hessian decomposition)
    Output: Figure 6

RUNNING THE NOTEBOOK

Google Colab

Open the notebook in Google Colab and run all cells from top to bottom. The first cell installs any missing dependencies automatically.

Tested with:

- Python 3.11
- NumPy 2.0
- SciPy 1.14
- Qiskit 1.2

REPRODUCIBILITY

- Exact noiseless state-vector simulations (no shot noise and no hardware-noise model).
- Global random seed = 1234 together with experiment-specific seeds for each validation block.
- Gradients and metric tensor computed using centered finite differences (eps = 1e-6).
- Hilbert–Schmidt metric on density-matrix tangent vectors throughout the paper. The Fubini–Study metric on pure-state derivatives is rescaled by a factor of four to match the Hilbert–Schmidt convention (METRIC_SCALE = 4.0 in the notebook).

Running the notebook from beginning to end regenerates every figure and CSV file reported in the paper. Sample sizes coincide with those described in the experimental setup (Section 5.1). Increasing the number of samples produces smoother statistics at the expense of longer execution times.

CONTACT

Roberto Casado
rober@usal.es

BISITE Research Group
Universidad de Salamanca
