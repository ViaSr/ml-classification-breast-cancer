# Breast Cancer Classification — ML Practice Project

A supervised-learning project that classifies tumors as malignant or benign
from cell-measurement data, built to apply data-science fundamentals
end-to-end: exploration, feature scaling, model training, and rigorous
evaluation. Includes a designed (not-yet-deployed) LLM summarization layer.

## Problem
Given 30 numeric features from digitized cell-nuclei images (Wisconsin Breast
Cancer dataset), predict whether a tumor is malignant or benign. This is a
high-stakes medical context where a missed malignant case (false negative)
carries far more cost than a false alarm — so the evaluation prioritizes
**recall on the malignant class**, not just overall accuracy.

## Approach
- Exploratory analysis: feature distributions and class balance (~37% malignant).
- Proper train/test split (stratified, 80/20) with scaling fit on training
  data only to avoid leakage.
- A **logistic regression** baseline (interpretable) compared against a
  **random forest** (higher-capacity), evaluated on held-out data.
- Feature-importance analysis for interpretability.

## Results
- [Model] achieved **[XX]% recall on malignant cases** and [XX]% precision
  on the held-out test set.
- The random forest showed a train/test accuracy gap of [X], illustrating
  mild overfitting relative to the logistic baseline.
- Top predictive features were [worst perimeter, worst radius, ...] —
  clinically sensible measures, which supports trust in the model.

[embed your confusion matrix image here]

## Designed: AI-assisted reporting (in progress)
Architecture is in the notebook for an LLM layer that translates model output
into a plain-language summary for non-technical stakeholders. Implementation
is scoped pending API capacity; the ML pipeline is fully functional without it.

## What I'd do next
Cross-validation (via a leakage-safe Pipeline) for a more robust performance
estimate; ROC-AUC; threshold tuning to maximize malignant-case recall for a
screening use-case; hyperparameter search on the random forest.

## Stack
Python, pandas, scikit-learn, matplotlib/seaborn. Built in Google Colab.

## Run it
Open in Colab → Runtime → Restart and run all. No API key required for the
core pipeline.
