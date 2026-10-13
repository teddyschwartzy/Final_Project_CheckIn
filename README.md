# Predicting Mortality Outcomes in HIV/AIDS Patients

## Project Overview

This project develops an automated analytical pipeline for predicting mortality outcomes in patients from the AIDS Clinical Trials Group Study 175 (ACTG 175). Building on earlier refactoring work, the analysis was transformed from a sequence of linear notebook cells into a modular, class-based workflow that supports the full data science process, including data ingestion, data validation, exploratory analysis, statistical testing, feature engineering, and machine learning evaluation.

The primary objective was to create a reproducible workflow that can consistently identify clinical factors associated with mortality while demonstrating the value of structured programming practices in health data science.

---

## Dataset Description

**Dataset:** AIDS Clinical Trials Group Study 175 (ACTG 175)

**Source:** UCI Machine Learning Repository

**Target Variable:** Mortality Outcome (Deceased vs. Alive/Censored)

**Predictor Variables:**
- Age
- Weight
- CD4 T-cell counts
- Treatment indicators
- Additional baseline clinical and demographic characteristics

**Clinical Objective:** Identify baseline clinical characteristics associated with patient survival and evaluate their ability to predict mortality outcomes.

---

## Pipeline Architecture

The analysis is organized within a `HealthAnalysisPipeline` class that manages each stage of the workflow in a structured and reproducible manner.

Key design features include:

- Centralized management of data, preprocessing objects, and model outputs.
- Consistent execution order across all stages of analysis.
- Separation of training and testing data to reduce the risk of data leakage.
- Reproducible model development through fixed random seeds and stratified sampling methods.
- Flexible architecture that can be extended to other clinical datasets and prediction problems.

### Pipeline Workflow

1. Data Ingestion and Validation
2. Data Preprocessing and Feature Engineering
3. Exploratory Data Analysis
4. Inferential Statistical Analysis
5. Machine Learning Model Development
6. Model Comparison and Evaluation

---

## Pipeline Enhancements

Several enhancements were implemented to strengthen the analytical workflow beyond the baseline project requirements:

### 1. Modular Pipeline Refactoring

The original notebook structure was refactored into a class-based pipeline to improve organization, maintainability, and reproducibility.

### 2. Automated Data Quality Validation

A validation step was added to summarize missing values and class distributions before modeling begins, helping identify potential issues early in the workflow.

### 3. Feature Engineering Integration

The pipeline automatically handles categorical encoding and generates interaction terms, including interactions between age and CD4 counts, to better capture complex clinical relationships.

### 4. Automated Model Selection

Three machine learning models are evaluated and compared using a common evaluation framework. The best-performing model is automatically identified based on F1-score performance.

### 5. Expanded Performance Evaluation

The evaluation process was extended beyond accuracy to include ROC-AUC analysis, classification metrics, and model comparison summaries, providing a more complete assessment of predictive performance.

---

## Statistical Analysis

An independent t-test was conducted to evaluate whether age differed significantly between patients who survived and those who did not.

**Result:** p = 0.0011

Because the p-value was below the 0.05 significance threshold, age was identified as a statistically significant predictor of mortality within the ACTG 175 cohort. This finding supports its inclusion in predictive modeling efforts.

---

## Machine Learning Results

Three supervised machine learning algorithms were evaluated:

- Logistic Regression
- Decision Tree
- Random Forest

### Best Performing Model: Random Forest

| Metric | Value |
|----------|----------|
| Accuracy | 89.1% |
| F1 Score | 0.757 |
| ROC-AUC | 0.928 |

The Random Forest model demonstrated the strongest overall performance across all evaluation metrics and was selected as the final model.

The superior performance of the Random Forest compared to Logistic Regression suggests that mortality outcomes are influenced by non-linear relationships among clinical predictors such as age, CD4 counts, and weight.

---

## Key Findings

- Age was significantly associated with mortality outcomes (p = 0.0011).
- Random Forest achieved the best predictive performance among all evaluated models.
- Baseline clinical characteristics provided strong predictive value for mortality classification.
- Ensemble-based methods were more effective than simpler linear approaches for this dataset.
- The modular pipeline provides a reproducible framework that can be adapted to similar clinical prediction problems.

---

## Installation and Execution

### Requirements

- Python 3.x
- Google Colab or Jupyter Notebook

### Required Libraries

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
ucimlrepo
```

### Running the Analysis

1. Clone the repository.
2. Open `Final_Project_Checkin.ipynb` in Google Colab or Jupyter Notebook.
3. Run all notebook cells.
4. The dataset will be automatically retrieved from the UCI repository and the full pipeline will execute from data ingestion through model evaluation.

---

## Repository Structure

```text
├── Final_Project_Checkin.ipynb
├── actg175_dataset.csv
└── README.md
```

---

## Author

**Hunter Schwarz**

**Program:** Dartmouth College, Health Data Science

**Date:** October 13, 2026

---

## Disclaimer

This project was developed for educational and instructional purposes. The ACTG 175 dataset is used solely to demonstrate statistical and machine learning methods within a reproducible analytical workflow.
