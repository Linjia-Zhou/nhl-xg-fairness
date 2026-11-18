# NHL expected goals with a fairness audit

Build an xG model that estimates the probability any NHL shot becomes a goal, then test whether its errors are systematically different across arenas, shot types, or game situations.

## Scope

- **Shots:** unblocked shot attempts (shots on goal plus missed shots). Empty-net shots, shootouts, and penalty shots are excluded.
- **Seasons:** four to five recent NHL seasons.
- **Success criteria:** well-calibrated probabilities matter more than raw accuracy. Goals are rare (roughly 6–8% of shots), so log loss and calibration are the primary checks. ROC-AUC is secondary.

## Status

Phase 0 (problem framing) and Phase 1 (repo setup) are done. Data collection has not started.

| Phase | What | Status |
| --- | --- | --- |
| 0 | Problem statement and scope | Done |
| 1 | Repo, environment, README | Done |
| 2 | NHL play-by-play pull and MoneyPuck shots | Not started |
| 3 | Cleaning, coordinate normalization, sanity checks | Not started |
| 4 | Features available at the moment of the shot | Not started |
| 5 | Time-based split, logistic regression, gradient boosting, calibration | Not started |
| 6 | Log loss, AUC, calibration, MoneyPuck comparison | Not started |
| 7 | Arena, shot-type, and situation bias audit | Not started |
| 8 | SHAP and hockey-sense checks | Not started |
| 9 | Write-up | Not started |

## Results

_None yet. Lead with the finding once the audit is done._

## Cleaning decisions

_None yet. Record every coordinate, missing-data, and exclusion decision here as the pipeline is built._

## Layout

```
data/raw/         NHL API JSON and MoneyPuck downloads (not committed)
data/processed/   DuckDB database and derived tables (not committed)
sql/              Cleaning and feature queries; raw tables stay untouched
notebooks/        Exploration and evaluation
src/nhl_xg/       Reusable pull, feature, and model code
reports/          Figures and the written summary
```

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Stack: pandas, scikit-learn, LightGBM, matplotlib, seaborn, SHAP, DuckDB, Jupyter.

## Reproducibility

_Add the season list, API pull command, and train/validation/test season split when those exist._
