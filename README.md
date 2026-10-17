# CreditWise Loan Approval Analysis

An exploratory data analysis project for a sample loan approval dataset. The current notebook inspects applicant and loan attributes, fills missing values, and visualizes approval outcomes and selected financial attributes.

## Project files

- `credit_wise_loan.ipynb` — Jupyter notebook containing the analysis.
- `loan_approval_data.csv` — input dataset (1,000 rows and 20 columns).

## Requirements

Python 3 and Jupyter Notebook or JupyterLab, with these packages:

- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn

Install dependencies with:

```bash
python -m pip install pandas numpy seaborn matplotlib scikit-learn jupyter
```

## Run the notebook

From the project directory, start Jupyter:

```bash
jupyter notebook
```

Open `credit_wise_loan.ipynb` and run the cells from top to bottom. The notebook reads `loan_approval_data.csv` by a relative path, so keep the CSV in the project directory (or update the path in the notebook).

## Current analysis

The notebook:

1. Loads the CSV into a pandas DataFrame and inspects its structure, summary statistics, and missing values.
2. Separates numeric and categorical columns.
3. Imputes numeric columns with their mean and categorical columns with their most frequent value.
4. Plots the loan approval class distribution, education level counts, applicant income distribution, applicant income by approval, and boxplots comparing income, credit score, debt-to-income ratio, and savings by approval.

The available fields cover applicant income, co-applicant income, employment, age, marital status, dependents, credit score, existing loans, debt-to-income ratio, savings, collateral, loan amount and term, loan purpose, property area, education, gender, employer category, and the approval outcome. `Applicant_ID` is also present as an identifier.

## Data handling note

The dataset contains missing values, including 50 missing `Loan_Approved` labels. The current notebook imputes every categorical column, including the target label, using the most frequent value. This can create artificial training labels and bias any later analysis. Before modeling or reporting approval rates, handle missing target labels separately (usually exclude rows without a known outcome) and fit imputers on training data only to avoid data leakage.

## Scope

This is an exploratory notebook at its current stage. It imports `train_test_split` but does not yet create a train/test split, train a model, or report predictive performance. No model results should be inferred from the visualizations alone.
