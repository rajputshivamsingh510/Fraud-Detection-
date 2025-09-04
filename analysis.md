# 🛡️ Fraud Detection -- Analysis Report

## 1. Data Cleaning

-   Dropped ID-like columns: `nameOrig`, `nameDest`.
-   Dropped `isFlaggedFraud` (leakage risk).
-   Winsorized extreme values in `amount` and balance columns.
-   Checked for missing values (none found).
-   Verified multicollinearity with VIF.

## 2. Feature Selection & Engineering

-   Kept transaction details: `step`, `type`, `amount`, balances.
-   Engineered features:
    -   `err_orig`, `err_dest` (consistency between balances and
        amounts)
    -   `amt_to_orig_bal`, `amt_to_dest_bal` (ratio features)
    -   Flags for suspicious balance mismatches.

## 3. Models

-   **Logistic Regression**:
    -   Linear, interpretable.
    -   Handles imbalance with `class_weight="balanced"`.
-   **Random Forest**:
    -   Non-linear, captures complex patterns.
    -   Tuned with fewer trees (`n_estimators=50`) and depth to manage
        runtime.

## 4. Model Performance

-   Both models evaluated using ROC-AUC, PR-AUC, Precision, Recall,
    F1-score.
-   Random Forest generally performed better in recall & ROC-AUC.
-   Logistic Regression gave interpretable coefficients.

*(Insert metrics & plots from notebook here.)*

## 5. Key Predictors

-   Top predictors: `type` (TRANSFER / CASH_OUT), `amount`, `err_orig`,
    `err_dest`, balance ratios.
-   These align with expected fraud behaviors (large suspicious
    transfers, mismatched balances).

## 6. Interpretation

-   Fraudulent transactions often involve:
    -   Transfer or cash-out types.
    -   Amounts inconsistent with balances.
    -   Sudden zero balances after transactions.

## 7. Business Recommendations

-   Flag transactions with:
    -   Large transfers/cash-outs relative to balance.
    -   Balance inconsistencies (orig/dest).
-   Require 2FA for high-risk transaction types.
-   Monitor device/IP velocity to detect unusual patterns.

## 8. Measuring Success

-   Track fraud rate (before vs after).
-   Monitor precision & recall in production.
-   A/B test intervention strategies.
-   Use ROC/PR curves to adjust thresholds for optimal recall.
