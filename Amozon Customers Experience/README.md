# Customer Retention Analysis

Understanding why customers stay or leave is crucial for any business. This project dives deep into customer behavior data to identify key factors influencing retention. Using exploratory data analysis (EDA), visualizations, and feature engineering, we uncover patterns and insights that businesses can act on.

---

## Problem Statement

Customer churn is a critical business issue. Losing a customer is far more costly than retaining one. The goal of this analysis is to:
- Understand patterns of customer engagement
- Identify attributes that separate retained customers from those who churned
- Suggest actionable insights for retention strategy

---

## Goals of This Project

- Perform comprehensive EDA on customer behavior data
- Compare behavioral and feedback metrics across retained vs churned groups
- Use multivariate visualizations to reveal interactions between variables
- Group continuous features (like time spent) into interpretable segments
- Highlight the most influential features affecting customer retention

---

## Dataset Overview

Each row in the dataset represents a unique customer with the following columns:

| Feature | Description |
|--------|-------------|
| `Age` | Age of the customer |
| `Gender` | Male / Female |
| `Location` | City or region |
| `Time_Spent_on_Site` | Total time user spent on site (in minutes) |
| `Products_Viewed` | Number of products viewed |
| `Products_Purchased` | Number of products purchased |
| `Feedback_Score` | Rating given by customer (1 to 10) |
| `Satisfaction_Score` | Internal satisfaction metric (1 to 10) |
| `Num_Interactions` | Total customer support interactions |
| `Retention_Status` | Target variable: 1 for retained, 0 for churned |

---

## Exploratory Data Analysis (EDA)

### Univariate Analysis:
- Distribution of age, satisfaction, feedback
- Countplots of categorical variables like gender and retention status

### Bivariate Analysis:
- Correlation heatmap between numerical features
- Boxplots comparing features with `Retention_Status`
- Retention rate by demographic or usage segments

### Multivariate Analysis:
- Grouped boxplots (e.g., `Products_Purchased` vs `Satisfaction_Score` by `Retention_Status`)
- Interactions between `Time_Spent`, `Feedback_Score`, `Num_Interactions`, etc.
- Bin-based insights (e.g., grouping `Time_Spent_on_Site` into Low, Medium, High, Very High)

---

## Key Visual Insights

Some sample conclusions from the analysis:

1. Customers with higher **Feedback Scores** and **Satisfaction Scores** are more likely to be retained.
2. **Product Purchases** and **Support Interactions** are strongly associated with retention — engaged customers stay.
3. **Time Spent** alone is not enough — customers who spend a lot of time but view few products are more likely to churn.
4. Retention varies by **location and age**, suggesting potential for targeted campaigns.

---

## Sample Visualizations

Visuals include:
- Heatmaps
- Pair plots
- Violin plots

---

## Feature Engineering

We created new features to enhance insight:

- **Time_Spent_Group**: Binned version of `Time_Spent_on_Site` into categories (Low, Medium, High, Very High)
- **Retention Rate Calculations**: Grouped aggregations to compute retention likelihood
- **Interaction Ratios**: Ratio of products purchased to products viewed

---

## Tools & Libraries

Built using Python and key data libraries:

- `pandas`, `numpy` – Data manipulation
- `matplotlib`, `seaborn` – Visualizations
- `scikit-learn` – For future machine learning modeling.


