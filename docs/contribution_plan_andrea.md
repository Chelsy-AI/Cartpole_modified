# Contribution Plan

**Team:** TeamTwo  
**Created:** W19D2  
**Last Updated:** 2026-02-06

---

## Problem Statement

The baseline PPO agent provides a reference performance on CartPole, but we aim to improve and validate performance through systematic hyperparameter optimization using Optuna.

---

## Scope

### What We WILL Do
- [x] Run PPO hyperparameter optimization using Optuna
- [x] Compare trial performance using mean reward
- [x] Export leaderboard and best configuration
- [x] Document rationale for selected ship candidate

### What We WON'T Do
- [ ] Modify PPO architecture
- [ ] Add new algorithms beyond PPO
- [ ] Tune environment dynamics

---

## Files We Touched

| File | Change Type | Owner |
|------|------------|-------|
| `notebooks/W19D4_hpo.ipynb` | Run | Andrea C |
| `results/hpo_leaderboard.csv` | Create / Update | Andrea C |
| `results/best_config.json` | Create / Update | Andrea C |
| `docs/ship_candidate.md` | Create | Andrea C |

---

## Definition of Done

- [x] HPO notebook runs end-to-end without errors
- [x] 25+ Optuna trials completed
- [x] Results exported to `results/`
- [x] Ship candidate documented
- [ ] PR reviewed and merged by maintainer

---

## Evidence Artifacts Produced

1. `results/hpo_leaderboard.csv` — ranked Optuna trial results  
2. `results/best_config.json` — selected ship candidate hyperparameters  
3. `docs/ship_candidate.md` — explanation of why this config won  

---

## Risks

| Risk | Mitigation |
|------|------------|
| Environment saturation (500 cap) | Acknowledge limitation; evaluate across seeds in W20 |
| Lucky evaluation runs | Use A/B testing with confidence intervals |
| Coordination delays | Keep work isolated in feature branch |

---

## Timeline

| Day | Milestone |
|-----|-----------|
| W19D4 | Initial HPO run |
| W19 Weekend | Expanded to 25 trials |
| W19 Sunday | Ship candidate documented |