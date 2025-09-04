# 🛡️ Fraud Detection Project

This repository contains the solution for the fraud detection internship assignment.

## 📂 Files Included
- **fraud_detection_updated.ipynb** – Jupyter Notebook with complete preprocessing, feature engineering, model training (Logistic Regression & Random Forest), evaluation, and plots.
- **analysis.md** – Business and technical analysis answering the assignment questions (data cleaning, feature selection, models, performance, interpretation, and recommendations).
- **README.md** – Project overview and instructions.

## ⚙️ How to Run
1. Clone or download this repository.
2. Place the dataset CSV (e.g., `fraud.csv`) in the project folder.
3. Open `fraud_detection_updated.ipynb` in Jupyter Notebook or JupyterLab.
4. Update the line:
   ```python
   DATA_PATH = "your_dataset.csv"
  with the correct path to your dataset file.
5. Run all cells to reproduce results.

🧾 Project Summary

Preprocessing: Dropped ID-like columns, encoded categorical type, scaled numerical features.

Models: Logistic Regression (interpretable, linear) and Random Forest (non-linear, robust).

Evaluation: ROC-AUC, PR-AUC, Precision, Recall, F1-score, Confusion Matrices, ROC & PR curves.

Feature Importance: Highlighted key predictors such as transaction type, amount, and balance inconsistencies.

Business Recommendations: Suggested fraud prevention measures (e.g., balance validation, transaction limits, 2FA, anomaly monitoring).

📊 Deliverables

Notebook with models and results.

Analysis report with answers to assignment questions.

This README as documentation.
