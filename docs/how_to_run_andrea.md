# How to Reproduce Our Ship Candidate (Andrea)

## What this is
This document explains how to reproduce the results for our ship candidate using the saved config in `results/best_config.json`.

## Requirements
- Python 3.10+
- Install dependencies (see `requirements.txt`) OR run in Colab

## Option A: Run in Google Colab (recommended)
1. Open the repo in GitHub.
2. Open the notebook used for HPO runs (example: `notebooks/W19D4_hpo.ipynb`).
3. Click **Open in Colab**.
4. Run the install/dependency cell at the top.
5. Confirm these files exist in the repo:
   - `results/best_config.json`
   - `results/hpo_leaderboard.csv`
6. Run the cell that loads and evaluates the best config.

### Expected output
- Mean reward should be high and stable (same ballpark as the best trial shown in `results/hpo_leaderboard.csv`).

## Option B: Run locally (terminal)
1. From the repo root:
   ```bash
   pip install -r requirements.txt
   ```
Open the notebook:
```
cd notebooks
jupyter notebook
```
Run the HPO notebook and confirm it loads:

../results/best_config.json

Expected output
- Mean reward should be similar to the best trial in results/hpo_leaderboard.csv.

Notes / Known Issues
- If results differ, confirm the evaluation settings (seed count, timesteps, eval episodes) match the team eval protocol.