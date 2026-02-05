# W19 + W20 CartPole Mini Project

Train a reinforcement learning agent to balance a pole, then prove your improvements with evidence.

---

## What You're Building

A complete ML experimentation workflow:

```
Week 19: Train baseline → Learn PR workflow → Tune hyperparameters → Submit best config
Week 20: Package for reproducibility → Get reviewed → Run A/B test → Make final decision
```

---

## Your Team Roles

Assign these on Day 1 and write them in `docs/runbook.md`:

| Role | Who Does What |
|------|---------------|
| **Runner** (1 person) | Runs the notebooks, exports CSV/JSON files |
| **Maintainer** | Manages branches, merges PRs |
| **Analyst** | Writes experiment docs, interprets results |
| **Reviewer** | Reviews teammate PRs, ensures quality |

> **Note:** Everyone writes their own individual Google Doc reflection.

---

## Quick Start (Do This First)

### Using Google Colab (Recommended)

1. Click any `.ipynb` file in this repo
2. Click **"Open in Colab"** button (or File → Open in Colab)
3. Run cells top to bottom
4. Save your work: **File → Save a copy to GitHub**

### Using Local Python (Optional)

```bash
# Check Python version (must be 3.10+)
python --version

# Install packages
pip install gymnasium stable-baselines3 tensorboard optuna

# IMPORTANT: Run notebooks from the notebooks/ directory
cd notebooks
jupyter notebook W19D1_baseline.ipynb
```

---

# 📅 WEEK 19

---

## W19D1 — Train Your Baseline

**Goal:** Get a working PPO agent and agree on how you'll measure success.

### Step-by-Step

| Step | Action | Where |
|------|--------|-------|
| 1 | Open `notebooks/W19D1_baseline.ipynb` | GitHub → Colab |
| 2 | Run all cells (takes ~5-10 min) | Colab |
| 3 | Write down your mean reward (e.g., "Mean: 245.3") | Notebook output |
| 4 | Open `docs/eval_protocol.md` and fill in as a team | GitHub |
| 5 | Open `docs/runbook.md` and assign team roles | GitHub |
| 6 | Post your baseline mean to Canvas | Canvas |

### What You'll See

```
Training for 50,000 timesteps...
==================================================
BASELINE RESULTS
==================================================
Mean reward: 247.30 (+/- 15.42)
Eval episodes: 10
==================================================
```

### End of Day Checklist

- [ ] Notebook runs without errors
- [ ] Baseline mean reward recorded
- [ ] `docs/eval_protocol.md` filled in (metric, seeds, timesteps)
- [ ] `docs/runbook.md` filled in (Runner name, environment choice)
- [ ] Posted to Canvas

---

## W19D2 — Learn the PR Workflow

**Goal:** Practice the branch → PR → review → merge cycle you'll use for real contributions.

### Step-by-Step

| Step | Action | Where |
|------|--------|-------|
| 1 | Create a new branch: `feature/your-name-update` | GitHub |
| 2 | Edit any doc file (small change is fine) | GitHub |
| 3 | Open a Pull Request to `main` | GitHub |
| 4 | Request a review from a teammate | GitHub |
| 5 | Review another team's PR (leave 1 comment) | GitHub |
| 6 | Fill in `docs/contribution_plan.md` | GitHub |

### How to Create a Branch (GitHub Web)

1. Click the branch dropdown (says "main")
2. Type your new branch name
3. Click "Create branch: feature/..."

### How to Open a PR

1. After pushing changes, click "Compare & pull request"
2. Write a clear title and description
3. Click "Create pull request"
4. Click "Reviewers" → add a teammate

### End of Day Checklist

- [ ] Created a feature branch
- [ ] Opened a PR
- [ ] Requested review from teammate
- [ ] Reviewed another team's PR
- [ ] `docs/contribution_plan.md` filled in

---

## W19D4 — Hyperparameter Optimization

**Goal:** Use Optuna to find better hyperparameters than the baseline.

### Step-by-Step

| Step | Action | Where |
|------|--------|-------|
| 1 | Open `notebooks/W19D4_hpo.ipynb` | GitHub → Colab |
| 2 | Set `N_TRIALS = 10` (for in-class) | Colab |
| 3 | Run all cells (~30-45 min) | Colab |
| 4 | Look at the leaderboard output | Colab |
| 5 | Download `hpo_leaderboard.csv` → commit to `results/` | GitHub |
| 6 | Download `best_config.json` → commit to `results/` | GitHub |
| 7 | Fill in `docs/ship_candidate.md` | GitHub |

### What You'll See

```
Top 10 Trials:
 trial  mean_reward  learning_rate  n_steps   gamma    ent_coef  clip_range
    7       487.20       0.000312      128  0.9901    0.000045        0.25
    3       421.50       0.000891       64  0.9856    0.000123        0.31
   ...
```

### End of Day Checklist

- [ ] HPO notebook runs without errors
- [ ] `results/hpo_leaderboard.csv` committed (10+ trials)
- [ ] `results/best_config.json` committed
- [ ] `docs/ship_candidate.md` filled in (why this config won)

---

## 📝 W19 Weekend Assignment (Due Sunday)

### Team Tasks

| Task | Owner | What to Do |
|------|-------|------------|
| Expand HPO sweep | **Runner** | Change `N_TRIALS = 25`, run again, commit updated CSV |
| Finalize PR | **Maintainer** | Make sure PR is merge-ready |
| Update docs | **Analyst** | Ensure all docs are complete |

### Individual Task (Everyone)

Write a **1-2 page Google Doc** answering:

1. What hyperparameters did you tune and why?
2. What does the evidence (CSV) show?
3. What's one limitation you observed?

Then add your link to `reports/individual_links.md`:

```markdown
| Your Name | [Your Google Doc](https://docs.google.com/...) |
```

### W19 Submission Checklist

- [ ] `results/hpo_leaderboard.csv` has **25+ trials**
- [ ] `results/best_config.json` exists
- [ ] PR is merge-ready or merged
- [ ] Your Google Doc link is in `reports/individual_links.md`

