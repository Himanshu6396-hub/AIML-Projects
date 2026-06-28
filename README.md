# 🎓 Student Performance Prediction using Linear Regression

> **Minor Project 1 — Supervised Machine Learning**

---

## 📌 Problem Statement

Academic performance is influenced by a variety of demographic and socio-economic factors. Early identification of at-risk students can help educators intervene in time. This project aims to **predict a student's math score** based on features such as gender, parental education level, lunch type, race/ethnicity, and test preparation course completion using a **Linear Regression** model.

---

## 📂 Repository Structure

```
├── data/
│   └── StudentsPerformance.csv        # Dataset
├── model/
│   └── linear_regression_model.pkl    # Trained model (saved with joblib)
├── notebook/
│   └── students_performance_analysis.ipynb  # Jupyter Notebook (full workflow)
├── results/
│   ├── eda_math_score_distribution.png
│   ├── eda_math_score_by_gender.png
│   ├── eda_math_score_by_test_prep.png
│   ├── eda_math_score_by_parental_edu.png
│   ├── eda_correlation_heatmap.png
│   ├── evaluation_actual_vs_predicted.png
│   ├── evaluation_residuals.png
│   └── evaluation_metrics.csv
└── README.md
```

---

## 📊 Dataset

- **Source:** [Kaggle — Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Rows:** 1000 | **Columns:** 8
- **Target Variable:** `math score`

| Feature | Type | Description |
|---|---|---|
| gender | Categorical | Male / Female |
| race/ethnicity | Categorical | Group A–E |
| parental level of education | Categorical | Education level of parent |
| lunch | Categorical | Standard / Free-reduced |
| test preparation course | Categorical | Completed / None |
| math score | Numerical | **Target** |
| reading score | Numerical | Reading exam score |
| writing score | Numerical | Writing exam score |

---

## 🔧 Methodology

### 1. Data Preprocessing
- Checked for and confirmed **no missing values**
- Checked for and removed **duplicate rows**
- Applied **Label Encoding** to all categorical columns

### 2. Exploratory Data Analysis (EDA)
- Distribution plot of math scores → approximately normal distribution
- Boxplot by gender → males score slightly higher in math
- Boxplot by test preparation course → completed students score notably higher
- Boxplot by parental education → higher education correlates with better scores
- Correlation heatmap → reading/writing scores are most strongly correlated with math score

### 3. Model Development
- **Algorithm:** Linear Regression (sklearn)
- **Train/Test Split:** 80% / 20% (`random_state=42`)
- **Features (X):** All columns except `math score`
- **Target (y):** `math score`

### 4. Model Evaluation

| Metric | Value |
|---|---|
| MAE | 4.1301 |
| MSE | 28.2753 |
| RMSE | 5.3175 |
| **R² Score** | **0.8838** |

---

## 📈 Results

The Linear Regression model achieved an **R² Score of 0.8838**, explaining approximately **88.4% of the variance** in math scores.

Key findings from the model coefficients:
- **Reading score** and **writing score** are the strongest predictors of math performance
- Students who **completed test preparation** scored significantly higher
- **Parental education level** has a moderate positive influence
- **Lunch type** (standard vs. free/reduced) reflects socio-economic background and impacts scores

The **Actual vs. Predicted** scatter plot shows predictions closely follow the perfect-fit diagonal, and the **Residuals plot** shows errors are randomly distributed with no strong pattern, indicating the model is well-fitted.

---

## 🧪 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/student-performance-prediction.git
cd student-performance-prediction

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter

# 3. Launch Jupyter Notebook
jupyter notebook notebook/students_performance_analysis.ipynb
```

---

## 📦 Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
joblib
jupyter
```

---

## 🔗 References

- Dataset: https://www.kaggle.com/datasets/spscientist/students-performance-in-exams
- Scikit-learn Documentation: https://scikit-learn.org/stable/modules/linear_model.html
- Seaborn Documentation: https://seaborn.pydata.org/

---

## 👤 Author

**Minor Project 1 | Supervised Machine Learning**
