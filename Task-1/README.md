## Task 1 CNN vs ViT
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
