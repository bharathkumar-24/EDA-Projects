# Sales Trend Analysis – Exploratory Data Analysis (EDA)

## Overview

This project provides a comprehensive exploratory data analysis (EDA) of a synthetic sales dataset. The goal is to understand overall sales behavior, revenue patterns, product performance, and temporal trends across a full year of data.

---

## Dataset Description

- **Total Records**: 100,000
- **Features**:
  - `Date`: Date of the sale (datetime)
  - `Product`: Product category (Laptop, Smartphone, etc.)
  - `Units_Sold`: Quantity sold in each transaction
  - `Revenue`: Revenue generated from the sale (USD)

- **Time Period**: Full year of 2022
- **Product Categories**: 5 types — Laptop, Smartphone, Tablet, Monitor, Printer

---

## Key Steps in the Analysis

### 1. **Data Loading & Initial Inspection**
- Loaded CSV file using pandas.
- Verified data types and structure.
- **Conclusion**: Data was clean, complete, and correctly formatted.

### 2. **Missing Value Check**
- Checked for null values.
- **Conclusion**: No missing values in any column.

### 3. **Descriptive Statistics**
- Generated summary stats for numerical columns.
- **Conclusion**:
  - `Units_Sold` ranged from 1–19, average ≈ 10.
  - `Revenue` ranged from \$100–\$2000, average ≈ \$1050.

### 4. **Date Range & Product Distribution**
- Spanned full year from Jan–Dec 2022.
- All 5 products were evenly represented.

### 5. **Visual Analysis**
- **Daily Revenue Trend**: Stable, without extreme seasonal fluctuations.
- **Product-wise Revenue**:
  - Barplot revealed top-performing products.
- **Histograms & Boxplots**:
  - Showed distribution and outliers in `Units_Sold` and `Revenue`.
- **Correlation Heatmap**:
  - Mild positive correlation between `Units_Sold` and `Revenue`.

---

## Insights

- **Laptops and Smartphones** were top revenue-generators.
- Most sales had 5–15 units per transaction.
- Revenue varied widely, possibly due to product pricing and quantity sold.
- No major issues in data quality or distribution.

---

## Future Work

- Add time-series forecasting (e.g., ARIMA, Prophet) for sales prediction.
- Analyze customer-level behavior if user info becomes available.
- Build classification or regression models to predict sales performance by product and date.

---

## Technologies Used

- Python
- Pandas
- Seaborn & Matplotlib
- Jupyter Notebook

---

## Folder Structure

