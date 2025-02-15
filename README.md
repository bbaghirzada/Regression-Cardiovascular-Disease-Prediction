# CHD Cardiovascular Disease Regression Analysis

## Project Overview
This project aims to analyze cardiovascular disease risk factors using a regression model. The dataset contains various health-related features and demographic attributes, enabling a predictive analysis of coronary heart disease (CHD) over a ten-year period. The analysis includes **data cleaning, exploratory data analysis (EDA), and regression modeling** to identify key risk factors.

## Dataset
- **Source:** Kaggle
- **Observations:** 3,390 entries
- **Features:** 16 columns, including demographic attributes, health indicators, and CHD risk outcomes.

## Features & Data Types
| Feature Name          | Data Type | Description |
|----------------------|------------|-------------|
| `age`               | Integer | Age of the individual |
| `education`         | Float | Education level |
| `sex`               | Object | Gender of the individual (Male/Female) |
| `is_smoking`        | Object | Smoking status (Yes/No) |
| `cigsPerDay`        | Float | Number of cigarettes smoked per day |
| `BPMeds`            | Float | Blood pressure medication usage |
| `prevalentStroke`   | Integer | History of stroke (1 = Yes, 0 = No) |
| `prevalentHyp`      | Integer | Hypertension status (1 = Yes, 0 = No) |
| `diabetes`          | Integer | Diabetes status (1 = Yes, 0 = No) |
| `totChol`           | Float | Total cholesterol level |
| `sysBP`             | Float | Systolic blood pressure |
| `diaBP`             | Float | Diastolic blood pressure |
| `BMI`               | Float | Body Mass Index |
| `heartRate`         | Float | Heart rate per minute |
| `glucose`           | Float | Blood glucose level |
| `TenYearCHD`        | Integer | CHD occurrence within ten years (1 = Yes, 0 = No) |

## Data Cleaning Steps
- **Checked for missing values** in features like `education`, `cigsPerDay`, `BPMeds`, `totChol`, `BMI`, `glucose`, and imputed missing values appropriately.
- **Handled categorical variables**, converting `sex` and `is_smoking` into numerical representations.
- **Removed outliers** in `sysBP`, `BMI`, and `glucose` using statistical techniques.

## Exploratory Data Analysis (EDA)
- **Demographic Distribution:** Age and gender analysis to understand population representation.
- **Risk Factor Analysis:** Comparison of CHD occurrence by smoking status, diabetes, hypertension, and cholesterol levels.
- **Correlation Analysis:** Identification of key factors contributing to CHD using correlation heatmaps.

## Regression Modeling
- **Objective:** Predict `TenYearCHD` occurrence based on health indicators.
- **Model Used:** Logistic Regression to classify individuals at risk.
- **Performance Metrics:** Evaluated using accuracy, precision, recall, and AUC-ROC.

# Process Flow
## 1. Data Preprocessing

# Missing Values Handling:
        Used the median for numerical variables (e.g., glucose, systolic_bp) to handle missing values due to robustness against outliers.
        Used the mode for categorical variables (e.g., sex, is_smoking) for consistency.

# Feature Encoding:
        Mapped categorical variables to numeric values:
            sex: Female → 0, Male → 1
            is_smoking: No → 0, Yes → 1

# Feature Engineering

    Logarithmic Transformations:
        Applied log1p to highly skewed variables (glucose, systolic_bp, bmi, cigs_per_day) to reduce skewness and stabilize variance.

    Square Root Transformations:
        Applied sqrt to moderately skewed variables (total_cholesterol, diastolic_bp) for better normalization.

# Data Imbalance Handling

    SMOTE (Synthetic Minority Oversampling Technique):
        Oversampled the minority class (ten_year_chd = 1) to balance the dataset and improve recall for "at-risk" predictions.

# Model Training

    Trained a Logistic Regression Model with the resampled data to classify individuals as "No Risk" or "At Risk."
    Used standardized predictors (StandardScaler) to ensure uniform scaling for all features.

## Key Findings
- **Blood Pressure & Cholesterol:** Strong correlation between high `sysBP`, `totChol`, and CHD risk.
- **Smoking & Diabetes:** Smokers and diabetics have a significantly higher probability of developing CHD.
- **BMI Impact:** Higher BMI values correlate with an increased likelihood of CHD occurrence.

## Tools & Technologies Used
- **Python:** Data analysis and regression modeling.
- **Pandas & NumPy:** Data wrangling and preprocessing.
- **Matplotlib & Seaborn:** Visualizing data trends.
- **Scikit-learn:** Implementing and evaluating logistic regression models.

## Conclusion
This study provided meaningful insights into cardiovascular risk factors, emphasizing the role of hypertension, cholesterol, smoking, and diabetes in predicting CHD. The logistic regression model demonstrated effectiveness in identifying high-risk individuals, which could aid healthcare professionals in early intervention strategies. Through this analysis, I have gained valuable insights into the key risk factors contributing to cardiovascular disease. I have learned the importance of data cleaning and preprocessing in ensuring reliable results, particularly in handling missing values and outliers. Exploratory data analysis has deepened my understanding of how different health indicators interact and influence disease prediction. Implementing regression modeling allowed me to see how predictive analytics can be applied in healthcare to identify at-risk individuals. This project has strengthened my analytical skills and reinforced the importance of data-driven decision-making in medical research and public health initiatives.

---


