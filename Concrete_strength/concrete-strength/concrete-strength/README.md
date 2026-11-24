# Concrete Compressive Strength Prediction

Predict concrete compressive strength (MPa) from mixture composition and curing age, compare linear vs non-linear models, analyse residuals, and discuss why predictive association is not causation.

## Contents
- `concrete_strength.ipynb` – full analysis (EDA, preparation, baseline, models, residuals, causal discussion)
- `data/` – `Concrete_Data.csv` (1,030 mixes) and its data dictionary
- `figures/` – exported plots

## Run
```bash
pip install -r requirements.txt
jupyter notebook concrete_strength.ipynb
```

## Key results (held-out test set, 80/20 split, seed 42)
| Model | RMSE (MPa) | R² |
|---|---|---|
| Mean baseline | 17.30 | -0.003 |
| Linear (raw) | 11.19 | 0.580 |
| Linear (log-age) | 7.65 | 0.804 |
| Gradient boosting | 4.33 | 0.937 |

Weakest predictions: high-strength mixes (60-90 MPa), where both models under-predict.

## Publish to GitHub
```bash
git init
git add .
git commit -m "Concrete strength analysis"
git branch -M main
git remote add origin https://github.com/<your-username>/concrete-strength.git
git push -u origin main
```
(Create the empty repository `concrete-strength` on github.com first.)
