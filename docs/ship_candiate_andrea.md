Ship Candidate – Andrea Churchwell

Team: Team Two
Created: W19D4
Last Updated: 2026-02-06

Selected Configuration

Algorithm: Tabular Q-Learning (CartPole-v1)
```
{
  "learning_rate": 0.351159658203541,
  "reward_shaping_scale": 0.1903872219557893,
  "num_bins": 9,
  "epsilon_decay_episodes": 1043,
  "discount_factor": 0.9863165063678174
}
```

Enabled Improvements
- Adaptive learning rate
- Smart exploration
- Custom state discretization bins
- Reward shaping
- Optuna HPO (120 trials)

Why This Config Was Selected

This configuration was selected after extended hyperparameter optimization (120 trials) and sufficient training budget (up to 1200 episodes), which allowed the agent to fully converge rather than relying on short or lucky runs.

Earlier experiments showed that high rewards (200–300+) could occur due to variance when episode budgets were too small. Increasing the episode budget and number of trials revealed which configurations consistently converged.

This configuration:
- Reached the maximum environment reward (500) during evaluation
- Achieved convergence at episode ~966
- Used non-extreme hyperparameter values
- Showed stable learning behavior rather than a single lucky spike

Performance Summary
| Metric              | Baseline (Fixed Params) | Ship Candidate           |
| ------------------- | ----------------------- | ------------------------ |
| Mean Eval Return    | ~120–150                | **500.0**                |
| Episodes to Solve   | Did not solve           | **966**                  |
| Evaluation Episodes | 50                      | 50                       |
| Stability           | High variance           | Stable after convergence |


Important note:
Perfect scores are expected once CartPole is solved; the key signal here is convergence behavior, not just the final number.

Evidence Summary
- Total HPO trials: 120
- Best trial: #18

Artifacts saved:
- hpo_results/<timestamp>/best_params.json
- hpo_results/<timestamp>/all_trials.csv
- progress_report.html

Multiple configurations reached near-maximum reward, but this one was chosen due to:
- smoother training curve
- reasonable exploration decay
- balanced discretization granularity

Known Limitations
| Limitation             | Impact                             |
| ---------------------- | ---------------------------------- |
| Single-seed evaluation | Results may reflect variance       |
| Discrete state space   | Limits generalization              |
| CartPole reward cap    | Saturation hides small differences |


High scores alone are not treated as sufficient proof.

Next Steps (W20)
- Run best configuration across multiple seeds
- Compare against fixed baseline using mean ± variance
- Lock protocol before final A/B decision
- Document uncertainty explicitly in final report

