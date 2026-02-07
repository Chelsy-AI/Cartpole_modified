Evaluation Protocol – Andrea Churchwell

Team: TeamTwo
Created: W19
Last Updated: 2026-02-06

Metric
| Field                | Value                                                          |
| -------------------- | -------------------------------------------------------------- |
| **Primary Metric**   | Mean evaluation episodic return                                |
| **How Measured**     | Average reward over fixed evaluation episodes (no exploration) |
| **Higher is Better** | Yes                                                            |

Seeds
| Field               | Value                                                                                                      |
| ------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Number of Seeds** | 1 (W19 exploratory phase)                                                                                  |
| **Seed Strategy**   | Base seed + trial offset                                                                                   |
| **Why This Many**   | Initial work focused on understanding variance and HPO behavior. Multi-seed validation is deferred to W20. |

Clarification:
Single-seed results are treated as directional, not final proof.

Training Budget
| Field                   | Value                                |
| ----------------------- | ------------------------------------ |
| **Episodes per Run**    | 601–1200 (varied during experiments) |
| **Evaluation Episodes** | 50                                   |
| **Environment Cap**     | 500 steps per episode                |

Rationale:
Higher episode counts were required for convergence. Increasing the training budget materially improved stability and final performance.

Stopping Rule
- Training stops after a fixed episode budget
- No early stopping
- “Solved” is logged when rolling average ≥195, but training may continue
- Evaluation is always run at the end of training
Comparison Rules
- Compare mean evaluation return, not single episode peaks
- Rank configurations by evaluation mean
- Treat very high scores (near 500) as suspect unless repeatable
When scores are close, prefer:
- smoother learning curves
- reasonable hyperparameter values
- consistent convergence behavior

Known Sources of Variance
- Discretization granularity (number of bins)
- Reward shaping scale
- Episode budget length
- Exploration decay schedule
- These were explicitly explored via Optuna HPO.

Limitations (W19)
- No multi-seed A/B testing yet
- Some high scores were likely “lucky” runs
- Results are not yet statistically validated

Planned Improvements (W20)
- Re-run best configuration across multiple seeds
- Compare against fixed baseline under identical conditions
- Report mean ± variance
- Lock protocol before final A/B decision

Agreement

[ ]Full team sign-off pending

[x]Protocol reflects experiments actually run

[x]No mid-experiment metric changes were made