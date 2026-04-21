# Product Analytics – User Retention & Experimentation

## Predictive Modeling Extension

This section extends the product analytics project with predictive modeling. The goal is to predict whether a user will be retained on Day 7 using early engagement features.

## Business Question
Can early user behaviors such as completing onboarding, activation, purchase, and experiment assignment help predict short-term retention?

## Data Source
Kaggle Database: https://www.kaggle.com/datasets/utsab5740/customer-cohort-analysis/data/code

## Hypotheses

### Product Experiment Hypothesis
- **H0:** The treatment variant does not improve activation or retention.
- **H1:** The treatment variant improves activation or retention.

### Predictive Modeling Hypothesis
- Users with stronger early engagement signals are more likely to be retained on Day 7.

## Models Used
1. **Logistic Regression** as a baseline interpretable classifier
2. **Random Forest** as a more flexible nonlinear model

## Evaluation Metrics
- Accuracy
- Confusion Matrix
- Precision / Recall / F1-score
- ROC Curve
- AUC

## Cohort Analysis
![Retention Heatmap](cohort.png)

Key insight:
The cohort retention analysis shows a sharp drop in user retention after the first purchase. Most cohorts experience a significant decline from Month 0 to Month 1, indicating that many users do not return after their initial transaction.

Earlier cohorts, such as October 2020, show relatively stronger retention compared to later cohorts like January and February 2021. This suggests that user retention performance may be deteriorating over time.

Long-term retention beyond 6 months is consistently low across all cohorts, generally falling below 10%. This indicates that the business struggles to maintain sustained customer engagement.

Overall, the results highlight a critical need to improve early-stage user retention, particularly in the first one to two months after acquisition.

The sharp drop in retention after the first purchase suggests that the onboarding and early user experience may not be sufficiently engaging to encourage repeat behavior.

Product teams should focus on improving the first 30-day experience, including personalized recommendations, promotions, or follow-up engagement strategies to increase repeat purchases.

Additionally, the decline in retention across newer cohorts suggests that recent changes in acquisition channels, pricing, or product experience may be negatively impacting user quality.
