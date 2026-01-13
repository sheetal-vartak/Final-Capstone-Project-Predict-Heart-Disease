# Cardiovascular Disease Prediction Project

**Author : Sheetal Vartak**

**Jupyter Notebook : [here](https://github.com/sheetal-vartak/Final-Capstone-Project-Predict-Heart-Disease/blob/2bbcded9b5ae0500670696fe263dc6aa2e30ea16/cardiovascular_disease_prediction_capstone_final.ipynb)**

## Executive Summary

This project develops a machine learning model to predict cardiovascular (heart) disease using patient health data. The goal is to enable early detection of heart disease risk, empowering healthcare providers to intervene proactively and improve patient outcomes. This project evaluates various modeling algorithms to determine the best way to predict heart didease.

---

## 1. Business Understanding

### The Problem

Heart disease is the leading cause of death worldwide, accounting for approximately 17.9 million deaths annually. Early identification of at-risk individuals can significantly reduce mortality through timely interventions, lifestyle changes, and preventive treatments.

### The Opportunity

Healthcare providers need tools that can:
- **Identify high-risk patients** before symptoms become severe
- **Prioritize preventive care resources** for those who need them most
- **Support clinical decision-making** with data-driven insights
- **Reduce healthcare costs** by preventing expensive emergency treatments

### Project Goal

Build a reliable predictive model that can screen patients for heart disease risk using readily available clinical measurements, achieving high accuracy while minimizing missed diagnoses (false negatives).

---

## 2. Data Overview & Statistical Analysis

### Dataset Summary

Data Source - https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction/data

| Metric | Value |
|--------|-------|
| Total Patients | 918 |
| Patients with Heart Disease | 508 (55.3%) |
| Patients without Heart Disease | 410 (44.7%) |
| Features Analyzed | 11 clinical measurements |

### Key Patient Characteristics

| Feature | Average | Range | Interpretation |
|---------|---------|-------|----------------|
| **Age** | 53.5 years | 28-77 years | Middle-aged to older adults |
| **Resting Blood Pressure** | 132 mmHg | 0-200 mmHg | Slightly elevated on average |
| **Cholesterol** | 199 mg/dL | 0-603 mg/dL | Borderline high average |
| **Maximum Heart Rate** | 137 bpm | 60-202 bpm | Normal range |
| **ST Depression (Oldpeak)** | 0.89 | -2.6 to 6.2 | Exercise-induced ECG changes |

### Data Quality Notes

- **172 patients** (18.7%) had missing cholesterol values recorded as zeros
- **1 patient** had a missing blood pressure reading
- Missing values were replaced with median values to maintain data integrity

### Statistical Relationships with Heart Disease

Strong correlations were identified between heart disease and:

| Factor | Correlation Direction | Statistical Significance |
|--------|----------------------|-------------------------|
| **ST Slope (ECG pattern)** | Strong | Highest predictor |
| **Chest Pain Type** | Strong | Asymptomatic chest pain highly associated |
| **Exercise-Induced Angina** | Strong | Presence significantly increases risk |
| **Maximum Heart Rate** | Moderate-Strong | Lower rates associated with disease |
| **Age** | Moderate | Older patients at higher risk |
| **Fasting Blood Sugar** | Moderate | Elevated levels increase risk |
| **Oldpeak (ST Depression)** | Moderate | Higher values indicate risk |

---

## 3. Key Findings

### Finding 1: Gender Differences in Heart Disease

Men in this study showed higher rates of heart disease compared to women.

---

### Finding 2: Silent Heart Disease is Common
 
Patients with "asymptomatic" chest pain (no obvious symptoms) had the **highest rates of heart disease**. This is concerning because these patients may not realize they are at risk.

---

### Finding 3: Exercise Response Reveals Risk

Two exercise-related factors were among the strongest predictors:
- **Exercise-induced angina** (chest discomfort during physical activity)
- **ST Slope changes** (abnormal heart electrical patterns during exercise)

Patients who experienced chest discomfort during exercise were significantly more likely to have heart disease.

---

### Finding 4: Lower Maximum Heart Rate Signals Risk
 
Patients with heart disease achieved **lower maximum heart rates** during exercise testing compared to healthy individuals.

---

### Finding 5: Fasting Blood Sugar Matters

Patients with elevated fasting blood sugar (>120 mg/dL, indicating diabetes or pre-diabetes) showed higher rates of heart disease.

---

## 4. Model Performance

### Prediction Accuracy

We tested multiple machine learning approaches to find the most accurate predictor:

| Model | Accuracy | Ability to Detect Disease (Recall) | Overall Score (ROC-AUC) |
|-------|----------|-----------------------------------|------------------------|
| **Random Forest** ⭐ | **87.5%** | 89.2% | **92.3%** |
| Support Vector Machine | 85.9% | 91.2% | 92.0% |
| Neural Network | 84.2% | 88.2% | 91.2% |
| Logistic Regression | 84.8% | 88.2% | 89.9% |

### What These Numbers Mean

- **87.5% Accuracy:** Out of 100 patients, the model correctly identifies 87-88 as having or not having heart disease
- **89.2% Recall:** Of patients who actually have heart disease, the model correctly identifies 89 out of 100
- **92.3% ROC-AUC:** The model has excellent ability to distinguish between healthy patients and those with heart disease

### Model Validation

The model was validated using:
- **80/20 train-test split** to ensure performance on unseen data
- **5-fold cross-validation** confirming consistent results across different data subsets
- Cross-validation accuracy: **84.5%** (stable and reliable)

### Model Comparison

<img width="980" height="721" alt="image" src="https://github.com/user-attachments/assets/93523e21-dd87-41c0-b510-6b3e946c86ef" />

---

## 5. Recommendations

### For Healthcare Providers

1. **Implement Screening Protocols**
   - Use this model as a first-line screening tool for patients over 45
   - Prioritize patients flagged as high-risk for follow-up diagnostic testing

2. **Focus on Key Risk Factors**
   - Pay special attention to patients with:
     - Asymptomatic presentation (silent disease)
     - Exercise-induced symptoms
     - Abnormal ECG patterns 
     - Elevated fasting blood sugar

3. **Integrate Exercise Testing**
   - The strongest predictors are exercise-related
   - Consider stress tests for at-risk patients to reveal hidden disease

### For Patients

1. **Know Your Numbers**
   - Blood pressure, cholesterol, blood sugar, and resting heart rate
   - Track changes over time

2. **Don't Ignore Subtle Signs**
   - Fatigue during exercise
   - Reduced exercise capacity
   - Any chest discomfort, even mild


---

## 6. Next Steps

### Immediate Actions

1. Gather feedback from healthcare providers
2. Validate predictions against actual patient outcomes
3. Include lifestyle factors (smoking, diet, physical activity)

### Future Enhancements

1. **Model Improvements**
   - Explore ensemble methods combining multiple models
   - Investigate deep learning for pattern recognition

2. **Technology Integration**
   - Develop a user-friendly web application for clinical use
   - Enable integration with health records

3. **Continuous Improvement**
   - Monitor model performance over time
   - Retrain with new data periodically

---

### Model Details
- Best performing model: **Random Forest Classifier**
- Features used: 11 clinical measurements
- Training data: 734 patients (80%)
- Test data: 184 patients (20%)

---

## Limitations

1. **Dataset Size:** 918 patients is a moderate sample; larger datasets could improve model reliability
2. **Population Representation:** Results may not generalize to all demographic groups
3. **Missing Lifestyle Data:** Smoking, diet, and exercise habits were not included
4. **Cholesterol Anomaly:** Some cholesterol values behaved unexpectedly in the model, suggesting data quality issues

---

## Conclusion

This cardiovascular disease prediction model demonstrates **strong performance (92.3% ROC-AUC)** in identifying patients at risk for heart disease. The analysis reveals that **exercise-related symptoms and ECG patterns** are the most powerful predictors, followed by age, blood sugar, and gender.

With this analysis, healthcare providers can:
- **Detect heart disease earlier** in at-risk patients
- **Allocate resources more effectively** to those who need them most
- **Save lives** through timely intervention and preventive care

---



