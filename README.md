# Paisabazaar Credit Score Analysis

This project explores customer data and classifies `Credit_Score` as Good, Standard, or Poor. Although the original project title mentions fraud, the dataset target is credit score—not fraud.

## Dataset
- 100,000 records and 28 columns
- 12,500 customers, with 8 monthly records each
- Credit score distribution: Standard 53.2%, Poor 29.0%, Good 17.8%
- The raw CSV is not included in this repository.

## Analysis
The notebook checks data quality and explores income, age groups, credit utilization, credit card count, payment delays, monthly trends, and numeric correlations. It also builds a baseline classifier using a customer-grouped holdout.

## Run the notebook
Open the `.ipynb` file in Google Colab and provide `dataset (1).csv` when prompted. Run the cells from top to bottom. Model metrics are produced when the notebook runs.
