# W20D4 Experiment Brief (Andrea)

## Goal
Compare baseline (A) vs ship candidate (B) using the same evaluation protocol.

## Variants
- **A (Baseline):** W19 baseline configuration (from baseline notebook / baseline run)
- **B (Ship Candidate):** `results/best_config.json`

## Primary Metric
Mean episodic return (average reward over evaluation episodes).

## Evaluation Plan
- Run **A** with **5 seeds**
- Run **B** with **5 seeds**
- Record results to `results/final_eval.csv` with columns:
  - variant (A or B)
  - seed
  - mean_reward

## Decision Rule
Compute a confidence interval for **(B − A)**:
- If CI is entirely **> 0** → **SHIP**
- If CI includes **0** → **ITERATE** (need more data)
- If CI is entirely **< 0** → **REVERT**

## Notes
Keep eval settings consistent with `docs/eval_protocol_andrea.md` (timesteps, eval episodes, etc.).
