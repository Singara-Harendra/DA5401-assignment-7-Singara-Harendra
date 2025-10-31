
👨‍💻 Author
Name : Singara Harendra

Roll Number : DA25M028

# DA5401 — A7: Multi-Class Model Selection using ROC & PRC

## Overview

This project compares multiple classification models on the **UCI Satimage (Landsat)** dataset using multi-class evaluation techniques — **ROC-AUC** and **Precision-Recall (PRC)**.  
The objective is to identify the most reliable model based on different evaluation metrics such as **Accuracy**, **Weighted F1**, **Macro-AUC**, and **Macro-AP**.

---

## Models Trained

**Baseline Models (6):**
- K-Nearest Neighbors (KNN)  
- Decision Tree  
- Dummy Classifier (Prior)  
- Logistic Regression  
- Gaussian Naive Bayes  
- Support Vector Classifier (SVC)

**Additional Models (2):**
- Random Forest  
- XGBoost  

---

## Results Summary

| Model | Accuracy | F1_weighted | Macro_AUC | Macro_AP |
|-------|----------:|------------:|-----------:|----------:|
| XGBoost | 0.942484 | 0.942009 | 0.995192 | 0.979952 |
| RandomForest | 0.950980 | 0.950537 | 0.994789 | 0.979285 |
| SVC | 0.943137 | 0.942075 | 0.992947 | 0.970261 |
| KNN | 0.947059 | 0.947022 | 0.987735 | 0.957290 |
| LogisticRegression | 0.899346 | 0.896333 | 0.978372 | 0.917057 |
| GaussianNB | 0.844444 | 0.848007 | 0.970475 | 0.899265 |
| DecisionTree | 0.898039 | 0.897923 | 0.930490 | 0.812592 |
| DummyPrior | 0.301307 | 0.139531 | 0.500000 | 0.200000 |

---

## Interpretation

### 1. Without RandomForest & XGBoost
- **Top Performers:** SVC and KNN.  
- **SVC** achieved the highest Macro-AUC (0.993) and Macro-AP (0.970), showing excellent ranking and precision–recall balance.  
- **KNN** followed closely with strong F1 and accuracy.  
- **DummyPrior** served as a random baseline (AUC ≈ 0.5), confirming other models’ meaningful learning.  

**Recommendation (Baseline Only):**  
- **SVC** is the best overall among the six baseline models due to its consistent high scores across all metrics.

---

### 2. Including RandomForest & XGBoost
- **Top Models:** XGBoost and RandomForest clearly outperform all others.  
- **XGBoost** achieved the highest Macro-AUC (0.995) and Macro-AP (0.980), slightly ahead of RandomForest.  
- These ensemble models capture non-linear relationships and offer superior probabilistic calibration.  
- SVC and KNN remain strong but marginally below the ensembles.

**Final Recommendation:**  
- **Best Overall Model:** ✅ **XGBoost** — best trade-off between accuracy, F1, AUC, and AP.  
- **Runner-up:** RandomForest — slightly less calibrated but highly accurate and interpretable.  

---

## Key Takeaways

- **ROC-AUC** measures overall ranking ability across thresholds.  
- **PRC-AP** emphasizes the balance between precision and recall — crucial for imbalanced classes.  
- Combining both metrics gives a robust understanding of classifier performance.  
- **XGBoost** demonstrates the strongest, most stable performance across all measures.

---


