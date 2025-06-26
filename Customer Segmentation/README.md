# Customer Segmentation – Exploratory Data Analysis (EDA)

## Overview

This project presents an in-depth Exploratory Data Analysis (EDA) of a customer dataset aimed at uncovering patterns in purchasing behavior. The ultimate objective is to prepare the dataset for customer segmentation—grouping similar customers together based on spending habits and income.

---

## Dataset Description

The dataset contains anonymized information about customers. The key features in the dataset include:

- `CustomerID`: Unique identifier for each customer.
- `Age`: Customer's age in years.
- `Annual_Income`: Annual income of the customer in thousands of dollars.
- `Spending_Score`: Score assigned by the shopping center based on customer behavior and spending.

---

## Key Steps in the Analysis

### 1. Data Loading and Structure Check
- Loaded the dataset using pandas.
- Verified column names, data types, and dataset shape.
- **Conclusion**: The data is structured and loaded without issues.

### 2. Missing Value Check
- Checked for missing/null values in the dataset.
- **Conclusion**: No missing values found.

### 3. Descriptive Statistics
- Generated summary statistics for numerical features.
- **Conclusion**:
  - Age ranges were between young adults and seniors.
  - Spending Scores were well-distributed between 1–100.
  - Income had a wide but reasonable distribution.

### 4. Univariate Analysis
- Plotted distributions for `Age`, `Annual Income`, and `Spending Score`.
- **Conclusion**:
  - Most customers were aged between 20 and 40.
  - Spending scores varied significantly across customers.
  - Income distribution showed diverse economic classes.

### 5. Bivariate Analysis
- Scatter plots and box plots were used to explore relationships.
- **Conclusion**:
  - High-income customers don’t always have high spending scores.
  - Certain clusters are visually detectable—ideal for future segmentation.

### 6. Pairplot and Correlation
- Analyzed the relationships between all numerical features.
- **Conclusion**:
  - Mild correlation between income and spending behavior.
  - Potential clusters hint at the effectiveness of clustering models like KMeans.

---

## Insights

- Customers show varied income and spending behaviors, indicating the need for personalized marketing.
- Some high spenders have moderate income, suggesting customer loyalty or needs-based purchases.
- Clustering this dataset can lead to clear customer segmentation strategies.

---

## Future Work

- Apply unsupervised learning algorithms (e.g., KMeans, DBSCAN) to cluster customers.
- Identify customer personas to enhance targeted marketing campaigns.
- Include more demographic or behavioral features if available (e.g., gender, region, frequency of visits).

---

## Technologies Used

- Python
- Pandas
- Seaborn & Matplotlib
- Jupyter Notebook.

---
## Files

- `customers_data.csv` — raw dataset.
- `Customer Segmentation.ipynb` — EDA notebook (with visualizations & conclusions).
- `README.md` — this file.





