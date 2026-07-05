# Project 02 — Titanic Survival Prediction (ML Model Comparison)

**Pluto Academy AI & ML Internship — Project 02**

## Dataset
[Titanic — Machine Learning from Disaster — Kaggle](https://www.kaggle.com/c/titanic)
Files used: `train.csv` (891 labeled passengers — used for modeling). `test.csv` and `gender_submission.csv` are included for completeness but not used (no ground-truth labels available for our own evaluation; those files are only for Kaggle's leaderboard).

## Files in this repo
- `Titanic_ML_Project.ipynb` — the complete, already-executed ML notebook
- `train.csv` — labeled training data (used by the notebook)
- `test.csv` — official Kaggle test set (unlabeled, included for completeness)
- `gender_submission.csv` — official Kaggle sample submission (included for completeness)
- `README.md` — this file

## Data Flow / Workflow
1. **Load** `train.csv` → inspect shape and missing values (`Age`, `Cabin`, `Embarked`).
2. **Preprocess** — fill `Age` with median, engineer `HasCabin` from `Cabin`, fill `Embarked` with mode, label-encode `Sex`, one-hot encode `Embarked`, engineer `FamilySize`, drop `PassengerId`/`Name`/`Ticket`/`Cabin`.
3. **Feature engineering** — correlation heatmap against `Survived` to confirm which features matter (`Sex`, `Pclass`, `Fare`, `HasCabin`).
4. **Split** 80/20 train/test, scale features for Logistic Regression and KNN.
5. **Train 3 models** — Logistic Regression, Random Forest, K-Nearest Neighbors.
6. **Evaluate** — Accuracy, Precision, Recall, F1 in a comparison table + bar chart.
7. **Best model analysis** — confusion matrix for the winning model (Logistic Regression, 81.6% accuracy), Random Forest feature importance chart, and a 5-line written conclusion.

## Model Comparison Results
| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| **Logistic Regression** | **0.8156** | **0.7903** | 0.7101 | **0.7481** |
| Random Forest | 0.7877 | 0.7246 | 0.7246 | 0.7246 |
| K-Nearest Neighbors | 0.7933 | 0.7500 | 0.6957 | 0.7218 |

## Checklist Mapping
| Requirement | Where it is |
|---|---|
| GitHub repo (public, README, dataset source mentioned) | This repo (dataset source above) |
| Colab link (Anyone with link can view) | You generate this after uploading — see posting steps below |
| Comparison table of all 3 models | "Step 4 — Evaluate & Compare" cell + table above |
| Confusion matrix / residual plot for best model | "Step 5" cell, Logistic Regression confusion matrix |
| 5-line written conclusion | Final markdown cell of the notebook |

## How to Post
1. Upload `Titanic_ML_Project.ipynb` to Google Colab.
2. In Colab's **Files** panel, upload `train.csv` (this is the only file the notebook reads).
3. Run **Runtime → Run all**, confirm the comparison table, confusion matrix, and feature importance chart all render with no errors.
4. Click **Share → Anyone with the link → Viewer** → copy the link.
5. Create a public GitHub repo → upload `Titanic_ML_Project.ipynb`, `train.csv`, `test.csv`, `gender_submission.csv`, and this `README.md`.
6. Screenshot the comparison table cell for the submission form.
7. Submit both links via the Google Form.
