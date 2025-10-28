# 🧬 Machine Learning in Bioinformatics – Project Portfolio

This repository contains **four end-to-end machine learning projects** in bioinformatics and healthcare data analysis.  
Each project covers data preprocessing, exploratory data analysis (EDA), feature selection, model building, evaluation, and interpretation.  
## 📁 Projects Overview

| No. | Project | Dataset Summary | Model Used | Accuracy | Highlights |
|-----|----------|-----------------|-------------|-----------|-------------|
| 1 | **Gene Expression Classification (ALL vs AML)** | 38 samples × 7,129 genes | SVM (RBF) | **91%** | Feature reduction from 7,129 → 11 genes using MI + LinearSVC |
| 2| **Asthma Prediction** | 10,000 samples × 17 features | XGBoost | **99.94%** | Family history, smoking, and BMI as top predictors |
| 3| **BRCA Multi-Omics Pipeline** | 705 samples × 1,941 features | Random Forest | **89%** | SMOTE improved minority recall; top 50 features retained |
| 4 | **Brain Cancer Classification** | 130 samples × 54,677 features | SVM (RBF) | **95.4%** | Feature reduction to 336 genes; class imbalance challenge

## 🧠 1. Gene Expression Classification (ALL vs AML)
**Objective:** Classify leukemia samples (ALL vs AML) using gene expression data.  
**Key Steps:**
- Removed non-informative columns (e.g., "call" indicators, gene descriptions).  
- Feature selection via Mutual Information and LinearSVC (L1) → reduced to 11 genes.  
- Model: SVM with RBF kernel (γ = 0.01, class_weight = "balanced").  
- **Performance:** 91% accuracy, ROC-AUC = 0.97.

--
---

## 🌬️ 2. Asthma Prediction
**Objective:** Predict asthma presence using demographic and lifestyle features.  
**Key Steps:**
- 10,000 samples, 17 features, balanced target (`Has_Asthma`).  
- Ordinal encoding for ordered features, one-hot encoding for categorical ones.  
- Models: Logistic Regression, Random Forest, SVM (RBF), XGBoost.  
- **Best Model:** XGBoost (99.94% accuracy).  
- **Cross-Validation:** Reliable results with low std deviation.  
- **Key Predictors:** Family history, smoking, BMI, and pollution level.

---

## 🧫 3. BRCA Multi-Omics Pipeline
**Objective:** Predict patient survival status (alive/deceased) using BRCA multi-omics data.  
**Key Steps:**
- 705 samples, 1,941 features → reduced to top 50 via Random Forest importance.  
- Handled imbalance (86.7% alive) using SMOTE.  
- Models: Random Forest, Logistic Regression, SVM (RBF).  
- **Best Model:** Random Forest (89% accuracy after SMOTE).  
- **Insight:** Ensemble models best handle class imbalance in molecular data.

---

## 🧩 4. Brain Cancer Classification
**Objective:** Classify brain tumor types from gene expression profiles.  
**Key Steps:**
- 130 samples × 54,677 gene probes, no missing data.  
- Mutual Information + KneeLocator → selected 336 top genes.  
- Models: SVM (RBF), Random Forest, Logistic Regression.  
- **Best Model:** SVM (RBF) → 95.4% accuracy (strong diagonal confusion matrix).  
- **Issue:** Some minority classes (e.g., pilocytic astrocytoma) underrepresented.

- ## 🧰 Tools & Libraries Used
- **Python:** pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn  
- **Feature Selection:** Mutual Information, LinearSVC, Random Forest importance  
- **Balancing:** SMOTE (imbalanced-learn)  
- **Visualization:** Correlation heatmaps, boxplots, ROC curves  

---

## 📊 Key Takeaways
- Feature selection is essential for high-dimensional bioinformatics data.  
- Ensemble methods (Random Forest, XGBoost) excel with complex biological data.  
- Imbalanced data remains a major challenge despite resampling (SMOTE).  
- SVM performed exceptionally well in small-sample, high-dimensional datasets
