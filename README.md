# 🎓 Student Performance Prediction

> An end-to-end Machine Learning project to predict student pass/fail outcomes using Python, built as part of an AI Internship.

---

## 📌 Project Overview

This project builds a complete machine learning pipeline on a dataset of **40,000 student records** to predict whether a student will **Pass or Fail** based on academic and behavioral features.

The project follows a structured data science workflow:
- Data Loading & Inspection
- Data Cleaning (missing values + invalid values)
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Model Building & Evaluation
- Conclusion & Insights

---

## 📂 Dataset

| Feature | Description |
|---|---|
| Student ID | Unique identifier for each student |
| Study Hours per Week | Number of hours studied per week |
| Attendance Rate | Percentage of classes attended (0–100%) |
| Previous Grades | Previous academic grades (0–100) |
| Participation in Extracurricular Activities | Yes / No |
| Parent Education Level | Associate / Bachelor / Master / Doctorate / High School |
| Passed | Target variable — Yes / No |

- **Total Records**: 40,000
- **Missing Values**: ~2,000 per column
- **Invalid Values**: Negative study hours, attendance rates above 100%, grades above 100

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualizations |
| Scikit-learn | Machine learning models |
| Jupyter Notebook | Development environment |
| Anaconda | Python distribution |

---

## 📊 Project Workflow

### Phase 1 — Setup & First Look
- Loaded dataset using Pandas
- Inspected shape, data types, summary statistics
- Checked unique values for categorical columns

### Phase 2 — Data Cleaning
- Detected and fixed **invalid values**:
  - Negative study hours → clipped to 0
  - Attendance rate > 100% → clipped to 100
  - Previous grades > 100 → clipped to 100
- Visualized missing data using a **heatmap** to confirm random distribution
- Filled missing numeric values with **median**
- Filled missing categorical values with **mode**
- Dropped 2,000 rows with missing target variable (`Passed`)
- Final clean dataset: **38,000 records**

### Phase 3 — Exploratory Data Analysis (EDA)
- Distribution plots (histograms) for numeric features
- Boxplots to check spread and outliers
- Countplot of Pass vs Fail (confirmed balanced dataset ~50/50)
- Group comparison: average study hours, attendance, grades for Passed vs Failed students
- Pass rate analysis by Parent Education Level and Extracurricular Activities
- **Correlation heatmap** — revealed near-zero correlation (-0.01 to 0.01) between all features and the target variable

### Phase 4 — Feature Engineering
- Encoded `Passed` (Yes/No → 1/0)
- Encoded `Participation in Extracurricular Activities` (Yes/No → 1/0)
- Applied **One-Hot Encoding** to `Parent Education Level` (5 categories)
- Dropped `Student ID` (irrelevant identifier)
- Final feature set: **8 columns**

### Phase 5 — Model Building
Split data: **80% Training / 20% Testing**

Built and trained 3 classification models:
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

### Phase 6 — Model Evaluation

| Model | Accuracy |
|---|---|
| Logistic Regression | 50.03% |
| Decision Tree | 49.87% |
| Random Forest | 50.25% |

Evaluated best model (Random Forest) using:
- Confusion Matrix
- Precision, Recall, F1-Score
- Classification Report

---

## 🔍 Key Finding

> Through EDA, it was discovered that **no feature showed a meaningful correlation** with the Pass/Fail outcome. This was confirmed by all three models achieving ~50% accuracy (equivalent to random guessing on a balanced binary target).

This highlights the most important lesson of the project:
**Thorough EDA before modeling reveals whether a dataset has predictive signal — saving time and setting realistic expectations.**

---

## 📈 Results Summary

- Dataset was balanced (~50% Pass, ~50% Fail)
- All numeric features (Study Hours, Attendance, Previous Grades) showed near-zero correlation with Pass/Fail
- Pass rates were identical (~50%) across all Parent Education Level and Extracurricular Activity categories
- All three ML models confirmed the EDA findings with ~50% accuracy

---

## 🚀 How to Run

1. Clone this repository:
```bash
git clone https://github.com/vani-dot/Student_Performance_Prediction.git
```

2. Open **Anaconda Navigator** and launch **Jupyter Notebook**

3. Navigate to the cloned folder and open:
```
Student_Performance_Prediction_Project.ipynb
```

4. Run all cells: **Run → Run All Cells**

---

## 📁 Repository Structure

```
Student_Performance_Prediction/
│
├── Student_Performance_Prediction_Project.ipynb   # Main notebook
├── student_performance_prediction.csv             # Dataset
└── README.md                                      # Project documentation
```

---

## 👩‍💻 Author

**Vanitha**
AI Internship Project | 2026

---

## 📝 License

This project is open source and available for educational purposes.
