Contribution Plan – Andrea Churchwell

Team: TeamTwo
Created: W19D2
Last Updated: 2026-02-06

Personal Focus

My focus this week was understanding why CartPole results change, not just how to make the number go up. I worked primarily on hyperparameter tuning, result interpretation, and connecting observed performance back to training dynamics (episodes, trials, variance).

Problem Context

Early results showed that single runs could produce deceptively high rewards. The main problem I focused on was distinguishing stable improvement from lucky runs, and learning how systematic hyperparameter optimization (HPO) helps reduce that uncertainty.

Scope of My Work
What I DID

 Ran multiple CartPole experiments to understand baseline variance

 Observed and documented the impact of “lucky” high-reward runs

 Ran Optuna-based HPO to search hyperparameter space

 Increased episode count and trial count to allow learning to stabilize

 Interpreted HPO outputs to identify reliable configurations

 Saved best-performing configurations and trial results for review

What I DID NOT Do

 Modify algorithm architecture

 Introduce new RL algorithms

 Claim baseline improvements without validation

 Finalize team-wide A/B comparisons

Files I Worked With
| File                               | Description                                       |
| ---------------------------------- | ------------------------------------------------- |
| `w19d4_starter.py`                 | Ran fixed and HPO modes, adjusted episodes/trials |
| `hpo_results/*/best_params.json`   | Saved best-performing configurations              |
| `hpo_results/*/all_trials.csv`     | Reviewed Optuna trial distributions               |
| `hpo_results/progress_report.html` | Visualized learning and comparison history        |


Best HPO configuration achieving consistent high evaluation scores

Optuna trial logs showing performance spread across trials

Progress report comparing multiple runs and configurations

These artifacts support conclusions about stability vs variance rather than a single “best run.”

Key Learnings

High rewards early on can be misleading without repetition.

Increasing episodes allows the agent time to converge.

Increasing trials allows Optuna to find better regions of the search space.

HPO is most effective when paired with sufficient training budget.

A solved environment (≥195) does not automatically imply optimal or stable performance.

Current Limitations

Results have not yet been validated across multiple fixed seeds.

No formal baseline vs ship-candidate A/B test has been completed.

Team PR workflow needs further practice and standardization.

Next Steps

Re-run best configuration across multiple seeds

Compare against a fixed baseline under identical conditions

Document evaluation protocol clearly

Support team-level merge and PR cleanup as needed

Reflection

This week shifted my understanding from “getting a high score” to understanding what the score actually means. The work done here sets the foundation for more rigorous evaluation in Week 20.