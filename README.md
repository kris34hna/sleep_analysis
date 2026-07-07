# Sleep Health & Lifestyle — EDA & Classification

Analyzing sleep health and lifestyle data to uncover the key factors driving sleep disorders — and building machine learning models to classify Sleep Apnea, Insomnia, and No Disorder.

---

## Brief Summary

An end-to-end data analysis and machine learning project on 374 individuals — involving data cleaning, feature engineering, univariate, bivariate & multivariate EDA, and 4 classification models (KNN, SVM, Decision Tree, Random Forest) — to answer: "Which lifestyle and health factors most strongly predict sleep disorders, and which model classifies them best?"

---

## Overview

This project explores a sleep health dataset to understand how age, occupation, BMI, stress level, blood pressure, heart rate, and physical activity relate to sleep quality and sleep disorders. The analysis moves from EDA to machine learning — training and comparing 4 classification models to predict whether a person has Sleep Apnea, Insomnia, or No Disorder.

---

## Problem Statement

Sleep disorders affect millions of people globally, yet the underlying risk factors are often unclear without medical testing. This project aims to answer:


"Which lifestyle and health characteristics — BMI, blood pressure, stress, age, heart rate — are most strongly associated with sleep disorders, and can we build a reliable model to classify them?"

#### Research Questions:

Question:-
1. What health and lifestyle factors are associated with Sleep Apnea and Insomnia?
2. How do stress level, sleep duration, and quality of sleep relate to each other?
3. Which machine learning model best classifies sleep disorder type?

---

## Dataset

| Column | Description |
|--------|-------------|
| Person | IDUnique identifier for each individual |
| Gender | Gender of the individual |
| Age |Age of the individual |
| Occupation | Profession of the individual |
| Sleep Duration | Average number of hours the person sleeps per day |
| Quality of Sleep | Self-rated quality of sleep (scale 1–10) |
| Physical Activity | LevelMinutes spent on physical activity per day |
| Stress Level | Self-rated stress level (scale 1–10) |
| BMI Category | Body Mass Index category (Normal, Overweight, Obese) |
| Blood Pressure | Blood pressure reading (Systolic/Diastolic) |
| Heart Rate | Resting heart rate in bpm |
| Daily Steps | Average daily step count |
| Sleep Disorder | Target — Sleep Apnea / Insomnia / None |

#### Feature Engineering:

| New Column | Source | Description |
|------------|--------|-------------|
| systolic_bp | Blood Pressure | Extracted systolic value (before /) |
| diastolic_bp | Blood Pressure | Extracted diastolic value (after /) |

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Python (Jupyter Notebook) | Data cleaning, EDA & model building |
| Pandas / NumPy | Data manipulation & feature engineering |
| Matplotlib / Seaborn | Visualizations (KDE plots, pie charts, heatmaps, countplots) |
| Scikit-learn  |ML models, train-test split, label encoding, evaluation metrics |

---

## Methods

| Step | Description |
|------|-------------|
| Initial Inspection | Checked shape (374 × 13), data types, null values, and duplicates |
| Data Cleaning | Standardized column names to lowercase with underscores, filled sleep_disorder nulls with "None" (single-type sleepers) |
| Feature Engineering | Split blood_pressure (Systolic/Diastolic) into two separate integer columns systolic_bp & diastolic_bp, dropped original blood_pressure column |
| Univariate Analysis | KDE + histogram for all numeric columns · Pie charts + countplots for all categorical columns (gender, occupation, BMI category, sleep disorder) |
| Bivariate Analysis | KDE plots of all numeric columns split by sleep_disorder · Cross-tabulation heatmaps of categorical columns vs sleep_disorder |
| Multivariate Analysis | Full correlation heatmap including one-hot encoded sleep_disorder columns |
| Label Encoding | Encoded gender, occupation, bmi_category using LabelEncoder for model input |
| Train-Test Split | 80/20 split with random_state=42 |
| Model Training | Trained 4 classifiers — KNN, SVM, Decision Tree, Random Forest |
| Model Evaluation | Accuracy, Error Rate, F1 Score, Confusion Matrix, Classification Report for each model |

---

## Key Insights

#### Univariate Insights:

1. Age (27–59): Evenly spread with no dominant group and no outliers.
2. Sleep Duration (5.8–8.5 hrs): Multimodal — likely driven by occupation differences.
3. Quality of Sleep (4–9): Skewed toward higher ratings; only a small poor sleep group (4–5).
4. Heart Rate: Only variable with visible outliers (75–86 bpm) — early signal of an at-risk subgroup.
5. Blood Pressure: Two visible clusters — normal range vs. elevated — matching sleep disorder groups.

#### Bivariate Insights:

1. Heart Rate is the clearest numeric separator — Sleep Apnea patients show higher heart rates (75–86 bpm) vs. normal (65–72 bpm).
2. Age: Sleep Apnea group is oldest on avg (49.7 yrs) vs. Insomnia (43.5 yrs) vs. None (39 yrs).
3. Sleep Duration: No disorder group sleeps most (7.36 hrs), Insomnia sleeps least (6.59 hrs) — expected.
4. Daily Steps: Sleep Apnea group has high steps (likely confounded by Nurses occupation).

#### Multivariate Insights:

1. Sleep Duration ↔ Quality of Sleep: +0.88 — strongest relationship; more sleep hours = better quality.
2. Stress Level ↔ Quality of Sleep: -0.90 — stress is the single biggest lifestyle factor degrading sleep.
3. Stress Level ↔ Sleep Duration: -0.81 — high stress = shorter sleep.
4. Systolic BP ↔ Diastolic BP: +0.97 — both measure the same underlying system.
5. Blood Pressure is strongest driver of Sleep Apnea — diastolic_bp (+0.67) & systolic_bp (+0.61) correlate more with Sleep Apnea than any other feature.
6. Age ↔ Sleep Apnea: +0.45 — age drives both BP and Sleep Apnea risk together.

---

## Dashboard / Output

This project's output is the Jupyter Notebook (Sleep_EDA.ipynb) containing:

1. KDE + Histogram for all numeric columns.
2. Pie charts + Countplots for all categorical columns.
3. KDE plots of all numeric columns split by Sleep Disorder.
4. Cross-tabulation heatmaps — Gender, Occupation, BMI vs Sleep Disorder.
5. Full correlation heatmap (including encoded sleep disorder).
6. Model Accuracy vs Error Rate — grouped bar chart.
7. Confusion Matrix heatmaps for all 4 models

---

## Results & Conclusion

The analysis confirms that BMI, blood pressure, age, and heart rate are the strongest predictors of sleep disorders — particularly Sleep Apnea. Stress level is the biggest lifestyle factor degrading sleep quality and duration. Occupation shows patterns (e.g., Nurses have high Sleep Apnea rates) but this is likely confounded by BMI and age rather than the job itself. Gender and daily steps show no clear reliable pattern. Among the 4 models, Random Forest is expected to perform best given the mixed data types and non-linear relationships in the dataset.

---


## Author & Contact

| Field | Info |
| Name | KRISHNA |
| LinkedIn | https://www.linkedin.com/in/krishna-krishna-26a106231/ | 
| GitHub | https://github.com/ |


⭐ If you found this project helpful, consider giving it a star!
