# Ship Candidate

**Team:** Team Two 
**Created:** W19D4  
**Last Updated:** 2-6-26

---

## Selected Configuration

```json
{
  "learning_rate": 0.000684792009557478,
  "n_steps": 256,
  "gamma": 0.9500582921874066,
  "ent_coef": 0.0001402497132660034,
  "clip_range": 0.11393512381599932
}
```

---

## Why This Config Won

| Metric      | Baseline | Ship Candidate | Improvement      |
| ----------- | -------- | -------------- | ---------------- |
| Mean Return | ~247     | **500.0**      | +100%            |
| Std Dev     | ~15      | **0.0**        | Reduced variance |
| Trial #     | N/A      | **2**          | —                |


This configuration consistently achieved the maximum possible reward (500) during evaluation, indicating stable and reliable policy performance rather than a single lucky run.

---

## Evidence Summary
Evidence Summary
- Total trials run: 25
- Leaderboard location: results/hpo_leaderboard.csv
- Config location: results/best_config.json

Multiple hyperparameter combinations achieved perfect performance, demonstrating PPO’s robustness on CartPole. This configuration was selected because it reached peak reward with moderate, non-extreme hyperparameter values, reducing risk of instability.

---

## Remaining Risks

| Risk                    | Severity | Mitigation Plan                                     |
| ----------------------- | -------- | --------------------------------------------------- |
| Environment saturation  | Medium   | Perform multi-seed A/B evaluation in W20            |
| Lucky evaluation runs   | Medium   | Compare against baseline using confidence intervals |
| Overfitting to CartPole | Low      | Accepted limitation of benchmark environment        |

---

## Next Steps

1. [ ] Package config for reproducibility (W20D1)
2. [ ] Run A/B evaluation with baseline (W20D4)
3. [ ] Document uncertainty in final report

