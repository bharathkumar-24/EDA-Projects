# 🍷 Wine Quality Prediction

A complete end-to-end machine learning project that predicts **red wine quality** (High / Low) using physicochemical features. The pipeline covers raw data cleaning, thorough exploratory data analysis, feature engineering, and a tuned KNN classifier.

---

## 📌 Problem Statement

Given a set of chemical properties of red wine (acidity, sulphates, alcohol content, etc.), classify each wine as **High Quality** (score > 5) or **Low Quality** (score ≤ 5).

---

## 📂 Dataset

| Property | Details |
|---|---|
| **Source** | [UCI Wine Quality Dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality) |
| **File** | `winequality-red.csv` |
| **Raw Rows** | 1,599 |
| **Rows after dedup** | 1,359 |
| **Features** | 11 physicochemical inputs |
| **Target** | `quality` → binarised to `high` / `low` |

### Feature Overview

| Feature | Description | Impact on Quality |
|---|---|---|
| fixed acidity | Tartaric acid (non-volatile) | Weak differentiator |
| volatile acidity | Acetic acid (vinegar taste) | 🔻 Lower = better |
| citric acid | Adds freshness & complexity | 🔺 Higher = better |
| residual sugar | Leftover sugar after fermentation | Weak differentiator |
| chlorides | Salt concentration | 🔻 Lower = better |
| free sulfur dioxide | SO₂ available to prevent spoilage | Mild increase in high quality |
| total sulfur dioxide | Total SO₂ (free + bound) | 🔻 Slightly lower in high quality |
| density | Related to sugar & alcohol | 🔻 Lower = often better |
| pH | Inverse of acidity | Weak indicator |
| sulphates | Preservative & bitterness | 🔺 Higher = better |
| **alcohol** | Ethanol % | 🔺 **Strongest predictor** |

---

## 🔬 Project Workflow

```
Raw CSV → Data Cleaning → EDA → Feature Engineering → Model Training → Evaluation
```

### 1. Data Cleaning
- Parsed semicolon-delimited raw format into a proper DataFrame
- Converted all columns from `object` to `float`
- Binarised the `quality` column: `≤ 5 → low`, `> 5 → high`
- Removed **240 duplicate rows** (1,599 → 1,359 rows)
- Verified: **no null values**

### 2. Exploratory Data Analysis (EDA)

**Univariate Analysis** — for every numeric feature:
- Histogram + KDE (Freedman–Diaconis optimal bin count)
- Boxplot (outlier visualisation)
- Q-Q Plot (normality check)
- Anderson-Darling test (statistical normality test)
- **Finding:** Almost all features are non-Gaussian and right-skewed

**Bivariate Analysis**
- Correlation heatmap
- Scatter plots & boxplots: Alcohol, Volatile Acidity, Sulphates, Citric Acid vs Quality

**Multivariate Analysis**
- Pair plots across key feature groups
- Cross-feature scatter plots coloured by quality class

### 3. Feature Engineering

| Step | Method | Detail |
|---|---|---|
| **Outlier Handling** | IQR Clipping | Applied to all numeric columns (non-Gaussian data) |
| **Feature Selection** | SelectKBest (ANOVA F-test) | Dropped `free sulfur dioxide`, `residual sugar`, `pH` |
| **Feature Transformation** | Skewness-based | `log1p` for skew > 1, `sqrt` for 0.5–1, reflected transforms for negative skew |
| **Feature Scaling** | MinMaxScaler | Normalisation (required for KNN distance calculations) |
| **Target Encoding** | LabelEncoder | `high → 1`, `low → 0` |

### 4. Model — K-Nearest Neighbours (KNN)

- **K Selection:** Cross-validated accuracy across k = 1 to 36 (6-fold CV)
- **Best K:** Automatically selected as the peak CV accuracy value
- **Final Model Config:** `KNeighborsClassifier(n_neighbors=best_k, algorithm='kd_tree', weights='distance')`
- **Train/Test Split:** 80 / 20

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading & manipulation |
| `numpy` | Numerical operations |
| `matplotlib` & `seaborn` | Visualisations |
| `scipy.stats` | Statistical tests (Anderson-Darling, Q-Q plots) |
| `sklearn.preprocessing` | LabelEncoder, MinMaxScaler |
| `sklearn.feature_selection` | SelectKBest, f_classif |
| `sklearn.neighbors` | KNeighborsClassifier |
| `sklearn.model_selection` | train_test_split, cross_val_score |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

### Run the Notebook

```bash
git clone https://github.com/bharathkumar-24/wine-quality-prediction.git
cd wine-quality-prediction
jupyter notebook Wine_Quality_Pridcition.ipynb
```

> Make sure `winequality-red.csv` is in the same directory as the notebook.

---

## 📁 Repository Structure

```
wine-quality-prediction/
│
├── Wine_Quality_Pridcition.ipynb   # Main notebook
├── winequality-red.csv             # Dataset
└── README.md                       # Project documentation
```

---

## 📊 Key Insights

- **Alcohol** is the single strongest predictor of wine quality — high-quality wines consistently show 10–14% alcohol content.
- **Volatile acidity** negatively impacts quality; wines rated high have significantly lower acetic acid levels.
- **Sulphates** and **citric acid** are positively correlated with quality.
- The dataset is fairly balanced: high quality ≈ 53.3%, low quality ≈ 46.7%.
- Most features are non-Gaussian and required skewness-based transformation before modelling.

---

## 👤 Author

**Bharath Kumar Nallabothula Boya**  
AI/ML Engineer | Technical Trainer  
📍 Hyderabad, India  
🔗 [GitHub: bharathkumar-24](https://github.com/bharathkumar-24)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).