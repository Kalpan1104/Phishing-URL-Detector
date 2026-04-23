# Phishing URL Detector

Classifies URLs as legitimate or phishing using only URL-extractable features — no page rendering, no HTML parsing. Four models are compared: a DNN, Random Forest, Gradient Boosting, and Logistic Regression. The project also includes an incremental learning setup so models can be updated as new phishing patterns show up, without retraining from scratch.

---

## Table of Contents

- [Architecture](#architecture)
- [Dataset](#dataset)
- [Models](#models)
- [Setup](#setup)
- [How to Run](#how-to-run)
- [License](#license)

---

## Dataset

**PhiUSIIL Phishing URL Dataset**

| Property | Value |
|---|---|
| Total URLs | 235,795 |
| Label 0 (Legitimate) | ~134,850 |
| Label 1 (Phishing) | ~100,945 |
| Feature source | URL-extractable only |
| Dropped columns | HTML/page-level features |

Included as `PhiUSIIL_Phishing_URL_Dataset.zip`. Unzip it into `Final Phase/` before running any notebooks.


---

## Models

| Model | Notebook | Notes |
|---|---|---|
| Deep Neural Network | `DeepLearning.ipynb` | 4-layer DNN, BatchNorm + Dropout, PyTorch |
| Logistic Regression | `Logistic Regression.ipynb` | Baseline; useful for sanity-checking the feature set |
| Random Forest | `ML_Project.ipynb` | Handles feature interactions; good interpretability via importance scores |
| Gradient Boosting | `ML_Project.ipynb` | Generally the strongest performer on tabular data |


---

## Setup

### Dependencies

| Library | Purpose |
|---|---|
| `torch` | DNN training and inference |
| `scikit-learn` | RF, GBM, LR, preprocessing, metrics |
| `pandas` / `numpy` | Data loading and manipulation |
| `matplotlib` / `seaborn` | Plots and evaluation curves |

```bash
pip install pandas numpy scikit-learn torch matplotlib seaborn
```

### Data Preparation

```bash
# From the repo root
unzip PhiUSIIL_Phishing_URL_Dataset.zip -d "Final Phase/"
```

---

## How to Run

**1. DNN**
```
DeepLearning.ipynb
```
Trains the 4-layer network (256 → 128 → 64 → 2).

**2. Logistic Regression**
```
Logistic Regression.ipynb
```
Baseline classifier. Run this after the DNN to have a comparison point.

**3. Random Forest & Gradient Boosting**
```
ML_Project.ipynb
```
Both ensemble models in one notebook, with feature importance analysis.

---

## License

MIT. See `LICENSE` for details.
