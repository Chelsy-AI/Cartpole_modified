# Evaluation Protocol

**Team:** TeamTwo  
**Created:** W19D1  
**Last Updated:** 2026-02-06

---

## Metric

| Field | Value |
|-------|-------|
| **Primary Metric** | Mean episodic return |
| **How Measured** | `evaluate_policy()` from Stable-Baselines3 |
| **Higher is Better** | Yes |

---

## Seeds

| Field | Value |
|-------|-------|
| **Number of Seeds** | 1 (W19), expanding to 5 (W20) |
| **Seed Values** | 42 |
| **Why This Many** | Single-seed evaluation is sufficient for initial HPO ranking. Multi-seed evaluation will be used in W20 A/B testing to address variance. |

---

## Training Budget

| Field | Value |
|-------|-------|
| **Timesteps per Run** | 20,000 (HPO), 50,000 (baseline) |
| **Episodes for Eval** | 10 |

---

## Stopping Rule

- Training stops after a fixed number of timesteps
- No early stopping is used
- Evaluation is run only after training completes

---

## Comparison Rules

1. Compare mean episodic return across trials
2. Use leaderboard ranking from Optuna HPO
3. A configuration is considered better if it achieves a higher mean return than the baseline
4. Ties at maximum return (500) are resolved by selecting non-extreme, stable hyperparameter values

---

## Agreement

- [ ] All team members reviewed this protocol
- [x] Runner confirmed feasibility via baseline and HPO runs
- [ ] Protocol will not change mid-experiment without team discussion