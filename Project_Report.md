# Paisabazaar Credit Score Analysis — Project Report

## Problem statement
The brief describes predicting `Credit_Score` (Good, Standard, Poor). Despite “fraud analysis” in the project title, the supplied dataset target is credit score, not fraud. The analysis is therefore scoped to credit-score EDA and classification.

## Dataset overview
The supplied CSV contains 100,000 rows and 28 columns. It has 12,500 unique customers with exactly eight monthly records per customer. There are no exact duplicate rows and pandas detects no null cells. The target distribution is Standard 53,174 (53.2%), Poor 28,998 (29.0%), and Good 17,828 (17.8%).

## Main findings
- Median annual income is 44,927.86 for Good, 36,824.18 for Standard, and 32,064.86 for Poor records.
- Median delay from due date is 10 days for Good, 18 for Standard, and 27 for Poor. Median delayed-payment counts are 8, 14, and 17 respectively. These are descriptive associations.
- Median credit-history age is 288 months for Good, 227 for Standard, and 161 for Poor. Median outstanding debt is 801.26 for Good and 2,081.47 for Poor.
- Median number of credit cards is 4 for Good, 5 for Standard, and 7 for Poor. Median credit utilization differs less across classes (32.74%, 32.33%, and 32.01%).
- Standard is the largest group every month. Good-score share rises from approximately 15.8–16.1% in months 1–3 to approximately 19.3% in months 7–8. Eight months are insufficient to establish seasonality.

## Handling and method
Pandas reports zero nulls and zero duplicate rows. The notebook reviews types, missingness, unique counts, and per-customer record counts. For readable visualization only, annual income is capped at its 99th percentile in the box-plot display; source values remain intact. Numeric-like text is parsed before visualizing.

The notebook creates more than five visual types: class count/share plots, stacked age-band composition, income box plot, utilization grouped bar plot, credit-card composition, delayed-payment box plots, monthly trend line, correlation heatmap, and a normalized confusion matrix. The baseline is a Random Forest pipeline with imputation/encoding and an 80/20 customer-grouped holdout. It excludes IDs, name, SSN, and the high-cardinality loan-description field. Run it in Colab to produce measured test metrics.

## Stakeholder implications and limitations
Payment delays, credit-history age, debt, and card count show marked descriptive differences across score classes and may help guide customer education and internal risk review. Income also varies across classes. These patterns do not establish causation. Credit utilization is relatively similar by class in this sample.

Repeated monthly observations create leakage risk; grouping by customer addresses this for a holdout, but a chronological test would be stronger. Validate feature timing and bureau provenance, check subgroup performance and calibration, and assess class-specific error costs before any operational use. Predictions should not replace validated credit decision processes.
