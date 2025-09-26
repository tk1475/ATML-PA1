# ATML-PA1

This repository contains coursework for CS6304 (ATML) — Programming Assignment 1. It is organized into tasks, each with separate notebooks, scripts, and outputs.

## Repository Structure

- `Task-1/` — Task 1: Fine-tuning and analysis on CIFAR-10
  - `task1.ipynb` — Main notebook for model fine-tuning (ResNet-50, ViT-S/16) and analysis.
  - `results/` — Generated figures and CSVs (ignored by git); populated when you run the notebook.
  - `*.pth` — Model checkpoints (ignored by git); saved locally when you run training can be obtained via email.
- `Task-2/` — Task 2: Additional experiments/analysis (see notebook inside for details)
  - `task2.ipynb` — Main notebook for Task 2.
- `Task-3/` — Task 3: Additional experiments/analysis (see notebook inside for details)
- `Assignment 1.pdf` — Assignment instructions.

> Note: Large artifacts (model checkpoints `*.pth`, `Task-1/results/`) are ignored by git to keep the repository lightweight. If you need to version these, consider using Git LFS.

## Environment Setup

Recommended: Python 3.9.

Create and activate a virtual environment (macOS/Linux):

```bash
python3 -m venv atml_env
source atml_env/bin/activate
```

Install dependencies:

```bash
pip install torch torchvision timm scikit-learn matplotlib numpy
```

(Optional) Apple Silicon acceleration test:

```python
import torch
print("MPS available:", torch.backends.mps.is_available())
```

## Data

- CIFAR-10 is downloaded automatically by `torchvision` when running the notebooks (default download folder inside the task directory or as set in the notebook).

## How to Run

1. Activate the environment:
   ```bash
   source atml_env/bin/activate
   ```
2. Launch Jupyter/VS Code and open the notebook of interest (e.g., `Task-1/task1.ipynb`).
3. Run all cells. The notebook will:
   - Download CIFAR-10 (if needed)
   - Build models (ResNet-50, ViT-S/16)
   - Train and evaluate
   - Save checkpoints (`*.pth`) and analysis outputs under `Task-1/results/`

## Checkpoints and Results

- Checkpoints (`*.pth`) are saved under `Task-1/` and are ignored by git.
- Plots and CSVs are saved under `Task-1/results/` and are ignored by git.
- To share results, export figures/CSVs manually or use a cloud link.

## Git Tips

- The repository is configured to ignore:
  - `Task-1/results/`
  - `Task-1/*.pth` and `Task-1/*.pt`
  - Virtual environments (e.g., `atml_env/`, `.venv/`)
  - Jupyter checkpoints and common temp files
- If you need to version large files, set up Git LFS:
  ```bash
  brew install git-lfs   # macOS
  git lfs install
  git lfs track "*.pth"
  git add .gitattributes
  git commit -m "Track checkpoints with Git LFS"
  ```

## Troubleshooting

- Torch not found inside notebook: ensure the notebook kernel uses the same virtual environment where you installed packages.
- Divergent branches error on pull: use `git pull --rebase origin main` after committing/stashing local changes.
- Large file push errors: ensure `.pth` and `Task-1/results/` remain ignored, or use Git LFS for those artifacts.
