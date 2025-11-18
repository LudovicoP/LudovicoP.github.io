---
---
title: "Credit Scoring: ML Approach"
excerpt: "XGBoost-based credit scoring with PCA and fairness checks (ROC AUC ≈ 0.86)."
collection: portfolio
---

This project presents a machine-learning pipeline for credit scoring focused on predictive accuracy and fairness. The workflow includes data cleaning, feature engineering (income per dependent, delinquency ratios), PCA for dimensionality reduction, and ensemble models. XGBoost produced the best performance (ROC AUC ~0.86), with careful attention to outlier treatment and legal/ethical constraints on protected attributes.

PDF: <a href="/pdfs/ML-creditscoring.pdf" target="_blank" rel="noopener">View PDF</a>

## Methods

- Feature engineering and imputation
- PCA for dimensionality reduction
- Model comparison: XGBoost, Random Forest, ensembles
- Fairness checks and legal/ethical review
