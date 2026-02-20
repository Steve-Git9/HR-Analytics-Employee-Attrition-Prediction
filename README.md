# HR-Analytics-Employee-Attrition-Prediction
A comprehensive machine learning analysis aimed at identifying the key drivers of employee attrition and building predictive models to support proactive HR retention strategies.

---

## 📌 Overview

Using IBM's HR Attrition dataset (1,470 employees × 35 features), this project walks through the full data science lifecycle — from exploratory data analysis to model comparison — with the goal of helping organizations understand *why* employees leave and *who* is most at risk.

---

## 📂 Repository Structure

```
├── HR_AnalyticsChallenge.ipynb   # Main analysis notebook
├── IBH_HR_ATTRITION_DATASET.csv  # Source dataset
└── README.md
```

---

## 🔍 Analysis Highlights

### Exploratory Data Analysis
Key attrition drivers identified across five dimensions:

| Category | Key Findings |
|---|---|
| **Demographics** | Younger employees (18–34), single, male employees attrit more |
| **Organizational** | Sales Representatives have the highest attrition rate; lower job levels are at greater risk |
| **Compensation** | No stock options and lower income bands correlate with higher attrition |
| **Satisfaction** | Low job, environment, and work-life balance satisfaction (Level 1) are strong predictors |
| **Career & Workload** | Overtime is the #1 driver — employees working OT are ~3× more likely to leave |

### Machine Learning Models

Two classifiers were trained and compared on the full dataset:

| Model | Accuracy | Attrition Recall | ROC AUC |
|---|---|---|---|
| Random Forest | 87% | 0.10 ⚠️ | — |
| Logistic Regression *(balanced)* | 75% | **0.67 ✅** | **0.796** |

> **Verdict:** Despite lower overall accuracy, Logistic Regression with `class_weight='balanced'` is the preferred model because identifying true attrition cases (minority class) is the primary objective. High overall accuracy on an imbalanced dataset is misleading.

**Top predictive features (Logistic Regression):**
1. `OverTime_Yes` (+1.82)
2. `JobRole_Laboratory Technician` (+1.52)
3. `MaritalStatus_Single` (+1.50)
4. `BusinessTravel_Travel_Frequently` (+1.38)
5. `Department_Research & Development` (−1.10)

---

## 💡 Strategic Recommendations

1. **Targeted Onboarding** — Focus retention efforts on employees in their first year, especially those changing roles or managers.
2. **Overtime Policy** — The single most impactful lever; mandate caps or compensation for overtime hours.
3. **Role-Specific Interventions** — Sales Representatives require immediate attention: review comp, targets, and support structures.
4. **Flexible Work** — Remote/hybrid options reduce commute burden and improve work-life balance scores.
5. **Predictive HR Monitoring** — Deploy the Logistic Regression model to flag at-risk employees before they disengage.

---

## 🛠️ Tech Stack

- **Python 3** · `pandas` · `scikit-learn`
- **Visualization:** `matplotlib` · `seaborn`
- **Environment:** Google Colab

---

## 🚀 Getting Started

1. Clone the repo and place `IBH_HR_ATTRITION_DATASET.csv` in the same directory as the notebook.
2. If running locally, remove or comment out the Google Drive mount cell:
   ```python
   # from google.colab import drive
   # drive.mount('/gdrive')
   ```
3. Update the `pd.read_csv()` path to point to your local file:
   ```python
   df = pd.read_csv('IBH_HR_ATTRITION_DATASET.csv')
   ```
4. Run all cells sequentially.

---

## 📊 Dataset

IBM HR Analytics Employee Attrition & Performance dataset — 1,470 records, 35 features including demographics, job details, satisfaction scores, and compensation data.

---

## 📄 License

This project is for educational and portfolio purposes.
