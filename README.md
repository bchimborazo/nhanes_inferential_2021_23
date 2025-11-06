# nhanes_inferential_2021_23
## Project Overview
- Name: Blanca Chimborazo-Reyes
- This project analyzes NHANES 2021-2023 data to explore relationships between demographic, health, and behavioral variables.

## Files
- R Google Colab Notebook: [r_nhanes_inferential_2021_23](https://colab.research.google.com/drive/11o3KmsRsOp7kHzS5WUHPRoVU6tiiw7u9?usp=sharing)
- Python Google Colab Notebook: [python_nhanes_inferential_2021_23](https://colab.research.google.com/drive/155R-8ZUvN-lovCOcoRcEqGPT2YFG-hDO?usp=sharing)
- Data source: [NHANES 2021-2023](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023)


### Summary of Results:

| Question | Test        | Result |
|-----------|-------------|--------|
| Question 1: Is there an association between marital status and education level? | Chi-square | Married individuals are more likely to have a bachelor's degree or higher compared to those who are not married. |
| Question 2: Is there a difference in mean sedentary behavior time between married and not married individuals? | T-test | Non-married individuals spend MORE time in sedentary behavior (approximately 19 minutes more per day on average) compared to married individuals. |
| Question 3: How do age and marital status affect systolic blood pressure? | Multiple Linear Regression | Age is the stronger predictor of the two variables. |
| Question 4: Is there a correlation between self-reported weight and minutes of sedentary behavior? | Simple Regression | Weight IS a statistically significant predictor of sedentary behavior (p < 0.001). As weight increases, sedentary behavior time also increases. |
| Question 5 Interpretation: Does mean sedentary behavior time differ across education levels? | ANOVA | Sedentary behavior time INCREASES with higher education levels. |

## Explanation of Results

### Question 1: Is there an association between marital status (married or not married) and education level (bachelor’s degree or higher vs. less than a bachelor’s degree)?
- Method of analysis: Chi-Square test
- Method Justification: Since marital status and education level are categorical variables, a Chi-Square test is best
- IV = Marital Status (categorical)
- DV = Education Level (categorical)
- Results: X-squared = 129.17, df = 1, p-value < 2.2e-16
  - Contingency table:
    - Married with Bachelor's or Higher: 1631
    - Married with Less than Bachelor's: 2503
    - Not Married with Bachelor's or Higher: 998
    - Not Married with Less than Bachelor's: 2648
- Interpretation of Results and Conclusion: Married individuals are more likely to have a bachelor's degree or higher compared to those who are not married. There is a highly significant association between marital status and education level.

### Question 2: Is there a difference in the mean sedentary behavior time between those who are married and those who are not married?
- Method of analysis: t-test 
- Method Justification: We're comparing the mean of a continuous variable (sedentary minutes) between two groups (married vs not married).
- IV = Martial status (categorical, 2 groups)
- DV = Sedentary behavior time (continuous)
- Results:
  - Mean sedentary time (Married) = 353.21 minutes (about 5.9 hours)
  - Mean sedentary time (Not Married) = 371.93 minutes (about 6.2 hours)
  - Difference = 18.72 minutes more for not married individuals
  - t = -3.8609
  - Df = 7385.2
  - P-value = 0.0001139
- Interpretation of Results and Conclusion: Non-married individuals spend more time in sedentary behavior (approximately 19 minutes more per day on average) compared to married individuals. There is a statistically significant difference in sedentary behavior between married and not married individuals.


### Question 3: How do age and marital status affect systolic blood pressure?
- Method of analysis: Multiple Linear Regression
- Method Justification: MLR is best becaise we have one continuous (age) and one categorical (marital status) predictor affecting a continuous outcome
- IV = Age (continuous) and Marital status (categorical)
- DV = Systolic blood pressure (continuous)
- Results: Age
  - Coefficient = 0.39524
  - Standard error = 0.01314
  - P-value < 2e-16 
  - Interpretation: Systolic BP increases with age. Age is a highly significant factor (p < 0.001).
- Results: Marital Status (Not Married vs Married):
  - Coefficient = 1.34909
  - Standard error = 0.45110
  - P-value = 0.0028
  - Interpretation: Systolic BP is higher in non-married individuals than married individuals. Marital status is significant (p = 0.003).
  - Residual standard error: 17.1 on 5832 degrees of freedom
  - R-squared results: 0.1344 (13.44%) variance in systolic blood pressure
  - Overall model F-statistic: 452.9 on 2 and 5832 DF
  - Overall model p-value: < 2.2e-16
- Interpretation of Results and Conclusion: Both age and marital status are significant predictors of systolic blood pressure with age being the dominant predictor. Increased age is associated with higher BP and so is non-married status.


### Question 4: Is there a correlation between self-reported weight and minutes of sedentary behavior?
- Method of analysis: Simple Linear Regression
- Method Justification: We're examining if one continuous variable (weight) predicts another continuous variable (sedentary time)
- IV = Self-reported weight (continuous)
- DV = Sedentary behavior time (continuous)
- Results:
  - Intercept: 239.32 minutes
  - Weight coefficient: 0.68 minutes per pound
  - Interpretation: Sedentary time increases with weight
  - P-value: < 2.2e-16 
  - R-squared: 0.0243 (2.43%)
- Interpretation: Weight explains only 2.43% of the variance in sedentary behavior
- F-statistic: 198.3 on 1 and 7952 DF,  p-value: < 2.2e-16
- Interpretation of Results and Conclusion: Weight is a statistically significant predictor of sedentary behavior. As weight increases, sedentary behavior time also increases.


### Question 5: Does mean sedentary behavior time differ across education levels?
- Variables: DMDEDUC2 and PAD680
- Method of analysis: One-way ANOVA
- Method Justification: We're comparing the means of a continuous variable (sedentary minutes) across more than two groups (5 education levels)
- IV = Education level (categorical)
- DV = Sedentary time (continous)
- Results:
  - F-statistic: 64.16
  - Degrees of freedom: 4 and 7703
  - P-value: < 2e-16 
  - Mean sedentary time by education level:
    - Less than 9th grade (1): 264.98 minutes (about 4.4 hours)
    - 9th-11th grade (2): 322.38 minutes (about 5.4 hours)
    - High School/GED (3): 329.72 minutes (about 5.5 hours)
    - Some College (4): 363.30 minutes (about 6.1 hours)
    - College graduate or higher (5): 405.36 minutes (about 6.8 hours)
- Interpretation of Results and Conclusion: There is a highly statistically significant difference in mean sedentary behavior time across education levels. Sedentary behavior time increases with higher education levels. This might be because college graduates are more likely to work desk jobs which come with a sedentary work environment. 

