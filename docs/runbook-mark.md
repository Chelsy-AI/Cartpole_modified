# Runbook

**Team:** [Team Two]  
**Last Updated:** [2026-02-08]

---

## Team Roles

| Role | Name |
|------|------|
| **Runner** | Mark |
| **Maintainer** | [Name] |
| **Analyst** | [Name] |
| **Reviewer** | [Name] |

---

## Primary Environment

- [X] **Google Colab** (recommended)
- [ ] **Local Python**

If Local, document:
- Python version: [e.g., 3.10.12]
- OS: [e.g., Ubuntu 22.04 / macOS 14 / Windows 11]

---

## Setup Instructions

### Colab Setup
1. Open notebook from GitHub
2. Runtime → Run all (or run cells sequentially)
3. Save: File → Save a copy to GitHub

### Local Setup (if applicable)
```bash
# Check Python version
python --version  # Must be 3.10+

# Create virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or: venv\Scripts\activate  # Windows

# Install dependencies
pip install gymnasium stable-baselines3 tensorboard optuna
```

---

## How to Run Each Notebook

### W19D1_baseline.ipynb
```
Purpose: Train PPO baseline, log to TensorBoard
Run time: ~5-10 minutes
Output: 
  - TensorBoard logs in ./logs/
  - Baseline mean reward printed
```

### W19D4_hpo.ipynb
```
Purpose: Optuna HPO sweep
Run time: ~30-60 min (25 trials)
Output:
  - results/hpo_leaderboard.csv
  - results/best_config.json
```

---

## Artifact Locations

| Artifact | Path |
|----------|------|
| Baseline notebook | `notebooks/W19D1_baseline.ipynb` |
| HPO notebook | `notebooks/W19D4_hpo.ipynb` |
| TensorBoard logs | `./logs/` (gitignored) |
| HPO leaderboard | `results/hpo_leaderboard.csv` |
| Best config | `results/best_config.json` |
| Final eval | `results/final_eval.csv` |

---

## PR Workflow

1. Create branch: `git checkout -b feature/description`
2. Make changes, commit with clear messages
3. Push: `git push origin feature/description`
4. Open PR on GitHub
5. Request review from teammate
6. Address feedback with new commits
7. Merge after approval

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Colab disconnects | Re-run from last checkpoint, save frequently |
| Package not found | Run install cell again |
| Out of memory | Reduce batch size or timesteps |
| TensorBoard not loading | Check log path matches |
