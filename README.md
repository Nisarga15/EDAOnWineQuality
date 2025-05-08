# EDAOnWineQuality
# 🍷 Exploratory Data Analysis on Wine Quality

This project explores the quality of red wine based on its physicochemical properties using Exploratory Data Analysis (EDA) and Machine Learning techniques. Our goal is to uncover the chemical factors that most influence wine quality and build models to predict wine scores.

---

## 📁 Dataset Overview

We used the `Redwinequality.csv` dataset from the UCI Machine Learning Repository. It contains:

- 1,599 red wine samples
- 11 input features (physicochemical attributes)
- 1 target variable: `quality` (score from 0 to 10)

### Features:

| Feature               | Description |
|------------------------|-------------|
| `fixed acidity`        | Non-volatile acids that contribute to tartness |
| `volatile acidity`     | Vinegar-like aroma; high values reduce quality |
| `citric acid`          | Enhances flavor freshness |
| `residual sugar`       | Sugar after fermentation; affects mouthfeel |
| `chlorides`            | Salt content; high values may indicate contamination |
| `free sulfur dioxide`  | Prevents microbial growth |
| `total sulfur dioxide` | Sum of free and bound forms |
| `density`              | Mass/volume ratio; affected by sugar & alcohol |
| `pH`                   | Acidity strength; affects taste and stability |
| `sulphates`            | Preservative agent; improves shelf life |
| `alcohol`              | Positively correlated with richness and quality |

---

## 🔍 EDA Methodology

We followed a 3-step EDA approach:

### 1. Data Acquisition
- Loaded dataset using pandas
- Used `.info()` and `.describe()` for initial inspection

### 2. Preprocessing
- Checked for null values (none present)
- Detected outliers using boxplots (e.g., volatile acidity, residual sugar)
- Applied feature scaling (StandardScaler)

### 3. Exploratory Data Analysis
- Plotted histograms, boxplots, and scatter plots
- Generated a correlation heatmap
- Found strong positive correlation with:
  - Alcohol
  - Sulphates
  - Citric Acid  
- Found strong negative correlation with:
  - Volatile Acidity
  - Density

---

## 📈 Machine Learning Models

We applied regression and classification models to predict wine quality.

### Binary Classification (`high_quality` if `quality >= 7`)

| Model             | Accuracy | Precision | Recall | F1 Score |
|------------------|----------|-----------|--------|----------|
| Logistic Regression | 86%    | 55%       | 23%    | 33%      |
| Decision Tree       | 87%    | 57%       | 51%    | 54%      |
| Random Forest       | 90%    | 73%       | 51%    | 60%      |

### Regression (predict exact quality score)
- **Linear Regression**  
  - R² ≈ 0.40  
  - RMSE ≈ 0.62

### Top Features (by importance):
- Alcohol
- Sulphates
- Volatile Acidity
- Density

---

## 📊 Key Insights

- Higher **alcohol** and **sulphates** → higher quality
- Higher **volatile acidity** and **density** → lower quality
- Most wines are rated 5 or 6 → distribution skewed to the middle
- Feature interactions matter → Random Forest performs best

---

## 🛠️ Future Work

- Apply SMOTE or resampling to handle class imbalance
- Hyperparameter tuning (GridSearchCV)
- Analyze other features like grape variety or fermentation methods

---

## 🚀 How to Run

1. Clone the repository  
   ```bash
   git clone https://github.com/Nisarga15/EDAOnWineQuality.git
   cd EDAOnWineQuality
2. Install dependencies
3. Run the notebook and upload the .csv file when prompted
   Open wine_quality_analysis.ipynb in Jupyter Notebook or VS Code or google colab

**References**

Cortez, P., et al. (2009). Modeling wine preferences by data mining from physicochemical properties. Decision Support Systems, 47(4), 547–553.
Forina, M., et al. (1986). Multivariate data analysis as a discriminating method of the origin of wines. Vitis, 25(3), 189–201.
Dataset Source: UCI ML Repository

