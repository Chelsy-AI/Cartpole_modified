# CartPole Team Repo (W19)

👥 Team Roles
| Name                  | Role       | Responsibilities                          |
| --------------------- | ---------- | ----------------------------------------- |
| **Mark Young**        | Runner     | Runs notebooks, exports CSV/JSON results  |
| **Drashti Patel**     | Maintainer | Manages branches, PRs, and merges         |
| **Andrea Churchwell** | Analyst    | Documents experiments, interprets results |
| **Tashoy Miller**     | Reviewer   | Reviews PRs and checks quality            |

***Quick goal: keep our team repo clean while each of us completes our personal checklist + contributions.***

## Team Branch Rules (PLEASE READ)
- **Do not push to `main` directly**
- Everyone works on their own branch:
  - `feature/andrea`
  - `feature/mark`
  - `feature/drashti`
  - `feature/tashoy`

## Standard Workflow (Branch → PR → Merge)
1) **Sync your local repo**
```bash
git checkout main
git pull origin main
```
2) Create/switch to your feature branch
```
git checkout -b feature/your-name
# OR if it already exists:
git checkout feature/your-name
```
3) Make your changes (docs/results/etc.)
4) Commit + push
```
git add .
git commit -m "Short message about what you changed"
git push -u origin feature/your-name
```
5)Open a PR from feature/your-name → main
- Request a reviewer
- Fix comments if needed
- Maintainer merges after approval

## ✅ What We Need This Week (W19)
- Baseline notebook runs successfully
- Baseline mean reward recorded

Docs updated:
- docs/runbook.md (roles)
- docs/eval_protocol.md (metric, timesteps, seeds)
- docs/contribution_plan.md

HPO artifacts committed:
- results/hpo_leaderboard.csv (25+ trials by Sunday)
- results/best_config.json

Individual work:
- reports/individual_links.md updated with each person’s Google Doc link