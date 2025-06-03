# Iris Dataset - Exploratory Data Analysis (EDA)

## Overview

This notebook provides an exploratory data analysis (EDA) of the Iris dataset, a classic dataset in machine learning and statistics. The analysis covers data loading, initial inspection, statistical summaries, and visualizations to understand the dataset's structure and characteristics.

---

## Dataset Description

The Iris dataset contains measurements for 150 iris flowers from three species:

- **Setosa**  
- **Versicolor**  
- **Virginica**

Each sample includes four features:

- `sepal.length` (length of the sepal)  
- `sepal.width` (width of the sepal)  
- `petal.length` (length of the petal)  
- `petal.width` (width of the petal)  

An additional column, `variety`, indicates the species of each sample.

---

## Key Steps in the Analysis

1. **Importing Libraries and Loading Data**  
   Dataset loaded using `pandas` from `iris.csv`.  
   Libraries used: `pandas`, `seaborn`, and `matplotlib`.

2. **Initial Data Inspection**  
   Displayed first few rows to verify structure.  
   Checked dataset dimensions (150 rows, 5 columns) and data types (4 numeric, 1 categorical).

3. **Checking for Missing Values**  
   Confirmed no missing values—data is complete.

4. **Descriptive Statistics**  
   Generated summary statistics (mean, std, min, max, etc.) for numeric features.  
   Observations:  
   - `petal.length` and `petal.width` show highest variability.  
   - No constant columns found.

5. **Class Distribution**  
   Dataset is perfectly balanced with 50 samples per species.

6. **Visualizations**  
   - Histogram of Petal Length: Clear separation between species, especially Setosa.  
   - Boxplot of Sepal Width: Mild outliers but no major issues.

---

## Conclusions

- The Iris dataset is clean, with no missing values and balanced classes.  
- Petal measurements (`petal.length` and `petal.width`) show significant variability and are strong predictors for species classification.  
- Visualizations highlight distinct patterns, especially in petal dimensions, useful for modeling.

---

## Future Work

- Perform feature engineering to improve model performance.  
- Build and evaluate classification models (e.g., logistic regression, decision trees) to predict species.  
- Explore clustering techniques to group samples without species labels.

---

## Technologies Used

- Python
- Pandas
- Seaborn & Matplotlib
- Jupyter Notebook

---

##  Files

- `iris_data.csv` — raw dataset.
- `iris EDA.ipynb` — EDA notebook (with visualizations & conclusions). 
- `README.md` — this file


