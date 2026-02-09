# W19 Ship Candidate — PPO CartPole

📋 COPY FOR docs/ship_candidate.md:
==================================================
Total trials: 10
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

Leaderboard saved to: ../results/hpo_leaderboard.csv
Best config saved to: ../results/best_config.json

## Summary
We ran an Optuna hyperparameter sweep (10 trials) to improve PPO performance on **CartPole-v1** compared to the default baseline configuration.

## Baseline
- Algorithm: PPO (Stable-Baselines3)
- Environment: CartPole-v1
- Training timesteps: 50,000
- Seed: 42
- Evaluation: 10 episodes
- Baseline mean reward: 500

## HPO Results (Optuna)
- Total trials: 10
- Best trial: #2
- Best mean reward: **500.00**
- Evaluation: 10 episodes

## Best Hyperparameter Configuration
The best-performing configuration from the sweep was:

```json
{
  "learning_rate": 0.000684792009557478,
  "n_steps": 256,
  "gamma": 0.9500582921874066,
  "ent_coef": 0.0001402497132660034,
  "clip_range": 0.11393512381599932
}
