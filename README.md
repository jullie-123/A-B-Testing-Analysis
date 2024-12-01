# A-B-Testing-Analysis

## Overview
A large company with a substantial user base plans to increase sales through advertisements on its website. However, they are uncertain whether these ads are effective in boosting sales. To address this, an A/B testing experiment was conducted over 31 days, involving 20,000 customers.

The goal of this project is to analyze the A/B test results and determine if the advertisements lead to a statistically significant increase in sales.
## Data cleaning and preprocessing
In the initial data preprosseing we perform the following tasks:

- Data loading and inspection.
- Handling missing values.
- Data cleaning and formatting
- Ensure data types and values are appropriate for analysis.

## Exploratory Data Analysis
EDA involves Understanding the distribution of ad views and purchases.

Compare behaviors between control and test groups.

A/B Testing:

Define null and alternative hypotheses:

- Null Hypothesis: Ads have no effect on purchases.

- Alternative Hypothesis: Ads increase the likelihood of purchases.

Perform statistical tests (e.g., t-tests or chi-square tests) to evaluate the results.


```python
## Analyze completion rates - Categorical in nature - Chi-square test
## Generate a contingency table
contingency_table = pd.crosstab(data['test group'], data['made_purchase'])

print(contingency_table)

## Perform the chi-square test
chi2, p_value, _, _ = stats.chi2_contingency(contingency_table)

print(f"Chi-square:{chi2}, P-value:{p_value}")
```

```python
## Conclusions based on P values
alpha = 0.05

## Completion status
if p_value < 0.05:
   print("Reject the Null hypothesis for Ads have no effect on purchase")
else:
   print("Fail to reject the Null hypothesis Ads have no effect on purchase")
```


## Technologies used

- Python: For data manipulation and analysis.
- Pandas:For handling and cleaning data.
- Matplotlib and Seaborn: For data visualization.
- Scipy and statsmodels: Statistical Analysis

## Features
Bar chart to compare conversion rates between Ads and PSA

## Visualization
chart to compare conversion rates between Ads and PSA

![Bar chart online](https://github.com/user-attachments/assets/570fea24-e00a-454f-85b4-151f0e5bfd04)


## Findings
Ads increases purchases

## Recommendations
Given the effectiveness of ads in increasing purchases, the company should consider scaling the campaign to a broader audience or extending its duration.


