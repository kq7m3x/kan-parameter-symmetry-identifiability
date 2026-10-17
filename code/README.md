# Code

B-spline KAN implemented from scratch, plus experiment scripts for each stage of the study. The network is written by hand without `pykan`; backpropagation and optimizers come from PyTorch (autograd, `torch.optim`).

## Structure

- `src/` — the implementation
  - `bspline.py` — B-spline basis on an extended grid (Cox–de Boor recursion)
  - `kan.py` — KAN layer and network
  - `hessian.py` — Hessian and eigenvalue utilities
- `experiments/` — one folder per stage, one script per experiment
  - `00-foundation/` — basis checks, gradient checks, function fitting
  - `01-exact-symmetries/`
  - `02-approximate-symmetries/`
  - `03-symbolic-extraction/`

## Conventions

- Every script fixes and records its random seed(s).
- Outputs go to the matching folder in [`../results/`](../results): figures to `figures/`, raw numbers to `raw/`.
- Every experiment is kept, including ones whose result is negative or unexpected.

## Reproduction

```bash
pip install -r requirements.txt
python code/experiments/<layer>/<script>.py
```
