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

## RESULT

## Cohort Analysis
![Cohort Heatmap](Cohort.png)

Key insight:
The cohort retention analysis shows a sharp drop in user retention after the first purchase. Most cohorts experience a significant decline from Month 0 to Month 1, indicating that many users do not return after their initial transaction.

Earlier cohorts, such as October 2020, show relatively stronger retention compared to later cohorts like January and February 2021. This suggests that user retention performance may be deteriorating over time.

Long-term retention beyond 6 months is consistently low across all cohorts, generally falling below 10%. This indicates that the business struggles to maintain sustained customer engagement.

Overall, the results highlight a critical need to improve early-stage user retention, particularly in the first one to two months after acquisition.

The sharp drop in retention after the first purchase suggests that the onboarding and early user experience may not be sufficiently engaging to encourage repeat behavior.

Product teams should focus on improving the first 30-day experience, including personalized recommendations, promotions, or follow-up engagement strategies to increase repeat purchases.

Additionally, the decline in retention across newer cohorts suggests that recent changes in acquisition channels, pricing, or product experience may be negatively impacting user quality.

## Funnel Analysis
![Funnel](Funnel.png)

The largest drop occurs between first purchase and repeat purchase, indicating weak early retention. This aligns with the cohort analysis, which showed a sharp decline after the first month.

Improving repeat purchase behavior should be a key priority, as it directly impacts long-term customer value.

## A/B Test Simulation
Chi-square: 0.8027413620085994
P-value: 0.37027500917862355

The chi-square test was conducted to evaluate whether the treatment group had a higher repeat purchase rate than the control group.

The resulting p-value is 0.37, which is significantly greater than the 0.05 threshold. Therefore, we fail to reject the null hypothesis.

This indicates that there is no statistically significant difference in repeat purchase behavior between the control and treatment groups.

The simulated treatment does not appear to improve user retention. This suggests that the change being tested may not have a meaningful impact on customer behavior.

Further experimentation or alternative product interventions may be required to drive improvements in retention.

## Machine Learning Model
![Confusion Matrix](Confusion_Matrix.png)
Both models perform well in predicting repeat purchase behavior. However, the Random Forest model shows a clear improvement in identifying repeat customers.

Specifically, Random Forest significantly reduces false negatives, meaning it is better at detecting users who are likely to return.

From a business perspective, this is critical because missing a repeat customer (false negative) means losing an opportunity to reinforce engagement or increase lifetime value.

Therefore, Random Forest is the preferred model when the goal is to identify and retain high-value returning customers.
The Random Forest model shows that total quantity purchased is by far the most important predictor of repeat behavior, accounting for nearly 75% of the model’s decision-making.

This indicates that deeper engagement, measured by the number of items purchased, is a stronger signal of retention than monetary value alone.

While total spending also contributes to predicting repeat behavior, its impact is significantly smaller. Additionally, average order value has limited importance, suggesting that high-value purchases do not necessarily translate into long-term customer retention.

Finally, the experimental variant has negligible importance, reinforcing earlier findings that the tested treatment does not significantly influence user behavior.

![ROC Curve](ROC_Curve.png)
Both Logistic Regression and Random Forest models achieve near-perfect AUC scores (0.995 and 0.999 respectively), indicating excellent ability to distinguish between repeat and non-repeat customers.

The ROC curves show that both models maintain a high true positive rate while keeping the false positive rate very low across thresholds. This suggests strong separability in the dataset.

However, the high performance is likely driven by the use of aggregated behavioral features such as total quantity purchased and total spending, which are closely correlated with repeat behavior.

Therefore, while the models perform extremely well, their predictive power may be optimistic compared to real-world scenarios where only early-stage user signals are available.

