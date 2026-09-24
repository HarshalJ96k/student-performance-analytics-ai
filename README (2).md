# Student Performance Analytics & Prediction using AI

**AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026**

**Author:** Harshal Jadhav

---

## 1. Project Overview

This project analyzes student academic performance using data analytics and machine learning.

The project uses the **Student Performance Factors** dataset to study relationships between academic, lifestyle, family, school, social and student-related factors and the final examination score.

The workflow combines:

- Data cleaning and quality analysis
- Exploratory Data Analysis (EDA)
- Executive KPIs
- Driver and correlation analysis
- Student risk screening
- Machine learning prediction
- Feature importance analysis
- Actionable, BI-style insights

The main target variable is:

`Exam_Score`

---

## 2. Problem Statement

Educational institutions have access to several student-related variables such as attendance, study hours, previous scores, tutoring, motivation and access to resources.

The objective of this project is to analyze these factors, identify measurable patterns associated with examination performance, identify potential student-risk groups using transparent rules, and build a machine-learning model to predict `Exam_Score`.

---

## 3. Objectives

1. Load and validate the Student Performance Factors dataset.
2. Analyze missing values, duplicates and data types.
3. Calculate important student-performance KPIs.
4. Explore relationships between student factors and exam scores.
5. Analyze important numerical and categorical drivers.
6. Create a simple student-risk screening framework.
7. Build a Random Forest regression model.
8. Evaluate the model using MAE, MSE and R².
9. Identify important features using permutation importance.
10. Convert analytical results into practical academic-support insights.

---

## 4. Dataset

### Dataset Name

**Student Performance Factors**

### Source

Kaggle — Lai Nguyen

### Dataset Link

https://www.kaggle.com/datasets/lainguyn123/student-performance-factors

### Dataset File

`StudentPerformanceFactors.csv`

### Dataset Size

- **6,607 records**
- **20 variables**

### Target Variable

`Exam_Score`

### Main Variables

| Category | Variables |
|---|---|
| Academic | `Hours_Studied`, `Attendance`, `Previous_Scores`, `Tutoring_Sessions`, `Exam_Score` |
| Lifestyle | `Sleep_Hours`, `Physical_Activity` |
| Motivation / Support | `Motivation_Level`, `Parental_Involvement`, `Access_to_Resources` |
| Family | `Family_Income`, `Parental_Education_Level` |
| School | `Teacher_Quality`, `School_Type`, `Distance_from_Home` |
| Social / Technology | `Peer_Influence`, `Internet_Access`, `Extracurricular_Activities` |
| Student Characteristics | `Learning_Disabilities`, `Gender` |

---

## 5. Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Scikit-learn**
- **Jupyter Notebook**

---

## 6. Project Workflow

```text
Dataset
   ↓
Data Loading
   ↓
Data Quality Check
   ↓
Data Cleaning & Preprocessing
   ↓
KPI Analysis
   ↓
Exploratory Data Analysis
   ↓
Driver / Correlation Analysis
   ↓
Student Risk Analysis
   ↓
Machine Learning
   ↓
Model Evaluation
   ↓
Feature Importance
   ↓
Actionable Insights
```

The analytical approach follows:

```text
KPI → Pattern → Driver → Risk / Opportunity → Action
```

---

## 7. Data Preparation

The project checks:

- Dataset shape
- Data types
- Missing values
- Duplicate records
- Unique values
- Descriptive statistics

For machine learning:

- Numerical missing values are handled using **median imputation**.
- Categorical missing values are handled using **most-frequent imputation**.
- Categorical variables are converted using **One-Hot Encoding**.
- Preprocessing is implemented inside a Scikit-learn pipeline.

The executed dataset contains missing values in:

- `Parental_Education_Level`
- `Teacher_Quality`
- `Distance_from_Home`

---

## 8. Executive KPIs

The executed analysis produced the following results:

| KPI | Result |
|---|---:|
| Total Students | 6,607 |
| Average Exam Score | 67.24 |
| Pass Rate (Score ≥ 50) | 100.00% |
| Average Attendance | 79.98% |
| Average Study Hours | 19.98 |

---

## 9. Key Analytical Findings

### Numerical Relationships

The strongest positive numerical correlations with `Exam_Score` in the executed analysis were:

| Variable | Correlation |
|---|---:|
| Attendance | 0.581072 |
| Hours_Studied | 0.445455 |
| Previous_Scores | 0.175079 |
| Tutoring_Sessions | 0.156525 |

These values describe associations in the dataset and should not be interpreted as proof of causation.

### Motivation-Level Analysis

Observed average exam scores:

| Motivation Level | Average Exam Score |
|---|---:|
| High | 67.70 |
| Medium | 67.33 |
| Low | 66.75 |

---

## 10. Student Risk Analysis

A project-defined screening framework was used:

| Risk Level | Rule |
|---|---|
| High Risk | `Exam_Score < 60` AND `Attendance < 70` |
| Medium Risk | `Exam_Score < 65` OR `Attendance < 75` |
| Low Risk | All remaining students |

### Executed Results

| Risk Level | Students | Percentage |
|---|---:|---:|
| Low | 3,896 | 58.97% |
| Medium | 2,648 | 40.08% |
| High | 63 | 0.95% |

These are project-defined analytical categories and are not official academic classifications.

---

## 11. Machine Learning

### Algorithm

**Random Forest Regressor**

### Configuration

| Parameter | Value |
|---|---|
| Number of Trees | 250 |
| Minimum Samples per Leaf | 2 |
| Random State | 42 |
| Train/Test Split | 80% / 20% |
| Target | `Exam_Score` |

### Model Evaluation

Results from the executed notebook:

| Metric | Result |
|---|---:|
| MAE | 1.0537 |
| MSE | 4.4819 |
| R² | 0.6829 |

The MAE of 1.0537 means that, on the held-out test set, the model's predictions differed from actual exam scores by approximately 1.05 score points on average.

---

## 12. Feature Importance

Permutation importance was used to identify the original variables that contributed most to predictive performance.

Top features from the executed analysis:

| Feature | Permutation Importance |
|---|---:|
| Attendance | 1.835600 |
| Hours_Studied | 1.219833 |
| Previous_Scores | 0.246796 |
| Access_to_Resources | 0.196845 |
| Parental_Involvement | 0.164495 |
| Tutoring_Sessions | 0.119547 |
| Parental_Education_Level | 0.043458 |
| Motivation_Level | 0.034886 |
| Family_Income | 0.030740 |
| Peer_Influence | 0.029132 |

Permutation importance is a model-based measure and should not be interpreted as a causal effect.

---

## 13. Actionable Insights

Based on the analysis, the project highlights the following areas for academic monitoring:

- Monitor attendance together with academic performance.
- Consider study-time patterns when planning academic support.
- Review previous performance when identifying students who may need additional support.
- Examine tutoring and resource-access patterns at group level.
- Use predictive results as decision-support information rather than automatic student classification.

---

## 14. Project Structure

```text
Student_Performance_Project/
│
├── Harshal_StudentPerformance_Analytics.ipynb
├── StudentPerformanceFactors.csv
├── requirements.txt
├── Harshal_StudentPerformance_Report.docx
└── README.md
```

---

## 15. Installation

Install the required Python libraries:

```bash
pip install -r requirements.txt
```

---

## 16. How to Run

### Step 1 — Download the Dataset

Download `StudentPerformanceFactors.csv` from:

https://www.kaggle.com/datasets/lainguyn123/student-performance-factors

### Step 2 — Place the Dataset

Keep the CSV in the same folder as the notebook:

```text
Student_Performance_Project/
├── Harshal_StudentPerformance_Analytics.ipynb
└── StudentPerformanceFactors.csv
```

### Step 3 — Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4 — Open the Notebook

Open:

```text
Harshal_StudentPerformance_Analytics.ipynb
```

using Jupyter Notebook, JupyterLab, VS Code or Google Colab.

### Step 5 — Run All Cells

Run the cells from top to bottom.

The notebook will generate:

- Data-quality results
- KPI tables
- EDA visualizations
- Correlation analysis
- Risk analysis
- Machine-learning results
- Actual vs predicted visualization
- Feature importance
- BI-style findings

---

## 17. Responsible Use and Limitations

- This is an educational/internship analytics project.
- The dataset is a public dataset and may not represent every student population.
- Correlation does not establish causation.
- Risk thresholds are defined specifically for this project.
- Machine-learning predictions should not be used as the sole basis for high-stakes decisions about individual students.
- Model results can change with different data, train/test splits, preprocessing methods or model configurations.

---

## 18. Future Scope

Possible extensions include:

- Interactive Streamlit dashboard
- Power BI dashboard
- Comparison of multiple ML algorithms
- Longitudinal student-performance analysis
- Explainable AI using SHAP
- Institution-specific model validation
- Automated academic-support recommendations

---

## 19. Project Deliverables

| File | Description |
|---|---|
| `Harshal_StudentPerformance_Analytics.ipynb` | Complete executed Python analytics and ML notebook |
| `requirements.txt` | Required Python dependencies |
| `Harshal_StudentPerformance_Report.docx` | Complete project report |
| `README.md` | Project overview, dataset, setup and usage instructions |

---

## 20. Author

**Harshal Jadhav**

Student Performance Analytics & Prediction using AI

**AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026**
