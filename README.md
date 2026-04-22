# Phishing-URL-Detector
The project aims is to detect malicious websites and developing an incremental learning framework to identify malicious websites.


## Requirements

| Library | Use |
|---|---|
| `torch` | DNN training |
| `scikit-learn` | Random Forest, Logistic Regression, preprocessing |
| `pandas` / `numpy` | Data loading and manipulation |
| `matplotlib` / `seaborn` | Visualizations |
| `joblib` | Saving scaler and models |
```bash
pip install pandas numpy scikit-learn torch joblib matplotlib seaborn
```

## How to Run

1. Start with `DeepLearning.ipynb` — DNN training (256 → 128 → 64 → 2, BatchNorm, Dropout)
2. Run `Logistic Regression.ipynb` for the baseline comparison
3. Run `ML_Project.ipynb` for the Random Forest model and Gradient Boosting

## Dataset
 
**PhiUSIIL Phishing URL Dataset** — 235,795 URLs, binary labels (0 = legit, 1 = phishing). Only URL-extractable features are used; HTML/page-level columns are dropped.
