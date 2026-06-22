# AAI-510 Student Academic Risk Prediction

## Final Project – Machine Learning: Fundamentals and Applications (AAI-510)

### Team 3
- Ashley Figueroa
- Jackson Kenyon
- Saman Tavasoli

---

## Project Overview

Educational institutions often struggle to identify students who are academically at risk until their performance has already declined. This limits opportunities for early intervention and can negatively impact student success.

The goal of this project is to develop a machine learning solution capable of predicting whether a student is academically at risk based on academic, behavioral, demographic, and support-related factors. By identifying at-risk students earlier, schools can provide targeted support and allocate resources more effectively.

This project was completed as the final team project for AAI-510: Machine Learning Fundamentals and Applications at the University of San Diego.

---

## Business Problem

Schools collect large amounts of student information, including attendance, study habits, tutoring participation, extracurricular involvement, and parental support. However, identifying students who may need intervention remains challenging.

The objective of this project was to build a predictive model that can:

- Identify academically at-risk students early
- Support proactive intervention strategies
- Improve allocation of educational resources
- Support data-driven decision making

---

## Dataset

### Student Performance Dataset

The dataset contains **2,392 student records** and includes:

- Academic information
- Behavioral indicators
- Demographic characteristics
- Support-related factors

Examples of features include:

- Absences
- StudyTimeWeekly
- Tutoring
- ParentalSupport
- Extracurricular
- Sports
- Music
- Age
- ParentalEducation

### Target Variable

For this project, academic performance was converted into a binary classification problem:

- **At Risk** = Students receiving grades D or F
- **Not At Risk** = Students receiving grades A, B, or C

---

## Data Preparation

The dataset required minimal cleaning and contained:

- No significant missing values
- No duplicate records
- Clean overall structure

### Preventing Data Leakage

The following variables were removed before modeling:

- StudentID
- GPA
- GradeClass
- GradeClassLabel

These variables either contained no predictive value or directly revealed the final academic outcome.

---

## Exploratory Data Analysis

Several important relationships were identified during exploratory analysis.

Students classified as at risk generally:

- Had higher absence rates
- Studied fewer hours per week
- Reported lower parental support
- Participated less frequently in tutoring and extracurricular activities

Attendance and study behavior showed the strongest relationships with academic performance.

---

## Machine Learning Models Evaluated

Three supervised machine learning models were evaluated:

### Decision Tree
- Baseline model
- Highly interpretable

### Random Forest
- Ensemble learning model
- Improved stability and accuracy

### XGBoost
- Gradient boosting model
- Advanced ensemble approach
- Strong predictive performance

---

## Model Evaluation Strategy

To ensure reliable results, we used:

- 80/20 Train-Test Split
- 5-Fold Stratified Cross-Validation

Performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

---

## Results

All models performed well, but ensemble methods consistently outperformed the Decision Tree.

### Best Model: XGBoost

Final optimized XGBoost performance:

| Metric | Score |
|----------|----------|
| Accuracy | 0.889 |
| Precision | 0.893 |
| Recall | 0.951 |
| F1-Score | 0.921 |
| ROC-AUC | 0.931 |

The high recall score was especially important because it allowed the model to identify the majority of students who were actually at risk.

---

## Feature Importance

The most influential features identified by XGBoost were:

1. Absences
2. Tutoring Participation
3. Extracurricular Activities
4. Parental Support
5. Weekly Study Time

These findings suggest that attendance, engagement, and support systems play a major role in student success.

---

## Deployment Recommendation

We recommend deploying the optimized XGBoost model as a weekly batch prediction system.

### Proposed Workflow

Student Data  
→ XGBoost Model  
→ Risk Dashboard  
→ Counselor Review and Intervention

The model should be used as a decision-support tool rather than a replacement for educator judgment.

---

## Ethical Considerations

Potential risks include:

- Prediction bias
- Data privacy concerns
- Overreliance on automated decisions

Recommended mitigations:

- Human review of predictions
- Regular model monitoring
- Strong student data protection policies

---

## Project Structure

```
AAI-510-At-Risk-Student-Prediction/
│
├── data/
│   
│
├── notebooks/
│   
│
├── images/
│
├── slides/
│
└── README.md
```

---

## Conclusion

This project demonstrates that machine learning can be used effectively to identify students who may be academically at risk before poor outcomes occur.

Among the models evaluated, XGBoost provided the strongest performance and achieved over 95% recall. The model successfully identified key factors associated with academic risk and offers a practical foundation for early intervention strategies in educational settings.

The greatest value of this project is not simply predicting which students may struggle, but helping educators identify opportunities for support before students fall behind.

