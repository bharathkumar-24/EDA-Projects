# Titanic Survival Pridiction - Exploratory Data Analysis (EDA)

## Overview

This notebook performs an Exploratory Data Analysis (EDA) on the Titanic dataset to uncover patterns, relationships, and potential predictors of survival. The dataset includes details about passengers such as age, class, fare paid, family connections, and survival status.

---

## Dataset Description

The Titanic dataset contains 891 samples with the following key features:

- **PassengerId**: Unique ID for each passenger  
- **Survived**: Survival (0 = No, 1 = Yes)  
- **Pclass**: Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd)  
- **Name**: Name of the passenger  
- **Sex**: Gender  
- **Age**: Age in years  
- **SibSp**: # of siblings/spouses aboard  
- **Parch**: # of parents/children aboard  
- **Ticket**: Ticket number  
- **Fare**: Passenger fare  
- **Cabin**: Cabin number  
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)

---

## Key Steps in the Analysis

### 1. Dataset Inspection

- Shape: 891 rows × 12 columns  
- Used `.info()` to check column types and nulls.

> **Conclusion**: Dataset contains missing values in `Age`, `Cabin`, and `Embarked`.

---

### 2. Initial Glimpse

- Displayed first 5 rows with `.head()`

> **Conclusion**: Features like `Name`, `Sex`, `Pclass`, and `Fare` are useful for further analysis.

---

### 3. Missing Value Analysis

- Used `.isnull().sum()` to detect missing values.

> **Conclusion**:
> - `Cabin`: ~77% missing, can be dropped or used as "has_cabin"
> - `Age`: ~19% missing, can be imputed
> - `Embarked`: only 2 missing entries

---

### 4. Summary Statistics

- Used `.describe()` to view mean, std, and quartiles for numeric features.

> **Conclusion**:
> - `Fare` is skewed due to some very high values.
> - `Age` spans from 0.4 to 80, with a median ~28.
> - Most passengers had few or no family onboard.

---

### 5. Survival Count Plot

- Used `sns.countplot()` to show survival class distribution.

> **Conclusion**: Dataset is imbalanced (~38% survived, ~62% did not).

---

### 6. Gender vs Survival

- Used countplot with `Sex` and `Survived`.

> **Conclusion**: Women had a much higher survival rate than men.

---

### 7. Passenger Class vs Survival

- Used countplot with `Pclass` and `Survived`.

> **Conclusion**: 1st class passengers were most likely to survive; 3rd class had lowest survival rates.

---

### 8. Age Distribution

- Used `sns.histplot()` to visualize age distribution.

> **Conclusion**: Most passengers were between 20–35 years old.

---

### 9. Family Size Feature

- Engineered new feature: `FamilySize = SibSp + Parch + 1`
- Visualized with a histogram.

> **Conclusion**: Medium-sized families had better survival odds; very large families fared worse.

---

### Key Insights

- **Gender:**  
  Female passengers had a significantly higher survival rate than males. This reflects the "women and children first" evacuation protocol during the sinking.

- **Passenger Class (Pclass):**  
  Passengers in 1st class showed a much higher likelihood of survival compared to those in 2nd and 3rd class, indicating that socioeconomic status impacted access to lifeboats.

- **Age:**  
  passengers with age bwtween 20 and 35  had better survival chances .

- **Fare:**  
  Higher fare prices were associated with increased survival probability, likely due to the correlation between fare, passenger class, and better access to safety.

- **Family Relationships:**  
  Traveling with family (siblings/spouses or parents/children) influenced survival odds, highlighting the role of social connections during the evacuation.


---

## Future Work

- Impute missing `Age` and `Embarked` values.
- Drop or transform `Cabin` into categorical (e.g., CabinKnown).
- Train machine learning models using engineered features.
- Explore correlations and build predictive pipelines.

---

## Technologies Used

- Python
- Pandas
- Seaborn & Matplotlib
- Jupyter Notebook.

---

##  Files

- `titanic_data.csv` — raw dataset.  
- `Titanic Survival Pridiction.ipynb` — EDA notebook (with visualizations & conclusions).  
- `README.md` — this file.

