# Logistic Regression on U.S. Census Data: Investigating the Relationship Between Education and Income

**Author**: Cindy Chen  
**Course**: ST518 – Final Project  
**Date**: Spring 2025

---

## 📄 Overview

This project analyzes the 1994 U.S. Census "Adult" dataset to examine the relationship between education level and income using logistic regression. Through data cleaning, exploratory data analysis (EDA), and predictive modeling, we assess how education and other socioeconomic variables influence the likelihood of earning over \$50,000 per year.

---

## 🧠 Objectives

- Investigate the role of **education** in predicting income using logistic regression.
- Control for **confounding variables** like age, marital status, occupation, and work hours.
- Evaluate model **performance** using classification metrics, residual analysis, and ROC/AUC.
- Use **visualization** to communicate findings effectively.

---

## 📊 Dataset Description

The dataset comes from the UCI Machine Learning Repository and includes 45,222 cleaned observations. Key features include:

- **Target**: `income` (binary; >50K or <=50K)
- **Predictors**: 
  - Demographics: `age`, `sex`, `race`, `native-country`
  - Socioeconomic: `education`, `education-num`, `marital-status`, `occupation`, `hours-per-week`, `capital-gain`, `capital-loss`

For the full attribute list, see the [Appendix](#appendix).

---

## 🔍 Methodology

### 1. Data Preparation

- Removed missing values and duplicates
- Encoded categorical variables as factors
- Scaled numeric features
- Train-test split: 80% training / 20% testing

### 2. Exploratory Data Analysis (EDA)

- Correlation matrix to identify multicollinearity
- Visualizations of income by education level and other covariates
- Identified confounding effects from `sex`, `age`, and `hours-per-week`

### 3. Modeling

- **Simple Logistic Regression**:
  - Predictor: `education-num`
- **Multiple Logistic Regression**:
  - Predictors: `education-num`, `marital-status`, `occupation`, `hours-per-week`, `age`

### 4. Model Evaluation

| Metric       | Train Set | Test Set |
|--------------|-----------|----------|
| Accuracy     | 84.2%     | 83.5%    |
| Precision    | 71.4%     | 70.2%    |
| Recall       | 59.0%     | 58.7%    |
| F1 Score     | 64.6%     | 63.8%    |
| AUC (Test)   | —         | 0.88     |

- ROC curve showed high discriminatory power.
- Residual analysis indicated good fit, with minor heteroskedasticity at extremes.

---

## 📈 Visualizations

- Correlation heatmap of numeric variables
- Line plots of income by education level
- PCA biplot for dimensionality assessment
- **Dot-and-whisker plot** of odds ratios for education levels (colorblind-friendly)

---

## ✅ Key Findings

- **Education is a strong, statistically significant predictor** of income.
- Individuals with higher education levels have **increased odds** of earning >\$50K.
- Additional covariates (e.g., age, work hours, marital status) contribute meaningfully but do not fully explain the effect of education.

---

## 🔬 Future Work

- Apply **penalized logistic regression** (Lasso, Ridge) to improve generalization.
- Test **tree-based models** (e.g., random forests) for nonlinear interactions.
- Explore **interaction terms** and **longitudinal patterns** with panel data.

---

