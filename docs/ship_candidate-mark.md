# Ship Candidate

**Team:** [Team Two]  
**Created:** W19D4  
**Last Updated:** [2026-02-08]

---

COPY FOR docs/ship_candidate.md:
==================================================
Total trials: 25
Best trial: #2
Best mean reward: 500.00

Best config JSON:
{
  "learning_rate": 0.000684792009557478,
  "n_steps": 256,
  "gamma": 0.9500582921874066,
  "ent_coef": 0.0001402497132660034,
  "clip_range": 0.11393512381599932
}
==================================================



---

## Why This Config Won

| Metric | Baseline | Ship Candidate | Improvement |
|--------|----------|----------------|-------------|
| Mean Return | 500.00 | 500 |  | 0% (matches max performance)
| Std Dev | 0.00 | 0.00 | |
| Trial # | N/A | 2 | | Best Optuna Trial

[1-2 sentences explaining why you trust this result]
This config matches the baseline’s max return (CartPole reward cap), so it “wins” by being a validated best trial from the HPO sweep. We’ll confirm it’s not a lucky run by evaluating across multiple seeds in Week 20.---

## Evidence Summary

- Total trials run: 10
- Leaderboard location: `results/hpo_leaderboard.csv`
- Config location: `results/best_config.json`

---

## Remaining Risks

| Risk | Severity | Mitigation Plan |
|------|----------|-----------------|
| Variance (lucky run) | Medium | Multi-seed eval in W20 |
| Reward cap limits comparison | Low | use multi-seed |
| Overfitting to CartPole | Low | Out of scope for this unit |

---

## Next Steps

1. [X] Package config for reproducibility (W20D1)
2. [X] Run A/B evaluation with baseline (W20D4)
3. [X] Document uncertainty in final report
