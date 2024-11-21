# Identification and Analysis of Code Technical Debt with Machine Learning

This repository contains the code, datasets, and artifacts developed for the project **"Identification and Analysis of Code Technical Debt Using Machine Learning"**, as part of my undergraduate thesis.

## 📋 Table of Contents

- [Project Description](#project-description)
- [Repository Structure](#repository-structure)
- [Datasets](#datasets)
- [Pipeline and Model](#pipeline-and-model)

---

## Project Description

Technical Debt (TD) management is essential due to the growing complexity of software systems and the demand for rapid deliveries. This project applies Machine Learning (ML) techniques to:

1. **Detect TD:** Identify whether a software class contains TD.
2. **Analyze TD Severity:** Categorize the severity level (low, medium, high) using a scoring system.

The **Random Forest** model was the most effective in the experiments, achieving:
- **F2-score:** 0.77
- **Accuracy:** 94%
- **AUC:** 0.78

A severity scoring metric was also developed to prioritize TD resolution. The datasets used primarily consisted of Java projects.

---

## Repository Structure

- **`tcc_phaab.ipynb`**: Main Jupyter notebook with the model development and experimentation process.
- **`best_pipeline.pkl`**: Serialized pipeline containing the trained model and preprocessing steps.
- **`dataset_with_project_names.csv`**: Original dataset with project names.
- **`dataset_final.csv`**: Preprocessed dataset used for the ML models.
- **`results/`**: Directory containing result tables.

---

## Datasets

### Summary

The datasets include 25 Java projects extracted from GitHub. Metrics were generated using tools like **SonarQube**, **CAST**, **PyDriller**, and others.

### Features

Some key features:
- **Code Complexity:** `ncloc`, `wmc`, `cbo`
- **Modification History:** `commits_count`, `refactorings`
- **Team Contributions:** `contributors_count`, `contributors_experience`
- **Class Interactions:** `rfc`, `dit`

The target variable `Max-Ruler` is binary (`1` for TD presence, `0` for absence). The final dataset contains 17,797 instances with 19 columns.

---

## Pipeline and Model

### Overview

The pipeline automates:
1. **Preprocessing:** Normalizing data and handling class imbalance using techniques like **SMOTE**.
2. **Training:** Model development using various ML algorithms.
3. **Evaluation:** Metrics such as **F2-score** and **ROC-AUC** to assess performance.

### Algorithms

- **Random Forest (Best Performing)**
- Support Vector Machine (SVM)
- Extreme Gradient Boosting (XGBoost)
- Decision Tree (DT)
- K-Nearest Neighbors (KNN)

The **Random Forest** was chosen for its balance between precision and recall.