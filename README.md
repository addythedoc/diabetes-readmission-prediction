
**Diabetes Readmission Prediction – Data Analytics & Modeling in R**

Part of my Public Health & Healthcare Analytics Portfolio
Portfolio: https://github.com/addythedoc/public-health-data-analytics-portfolio

**Overview**

This project demonstrates a complete end-to-end data science workflow in R using the UCI Diabetes 130-US Hospitals dataset. The analysis includes loading and cleaning raw hospital encounter data, performing exploratory data analysis (EDA), building baseline predictive models, and interpreting key drivers of 30-day hospital readmission.

The project highlights applied skills in R programming, data cleaning, exploratory analysis, statistical modeling, machine learning, visualization, and healthcare analytics.

**Dataset**

Name: Diabetes 130-US Hospitals Readmission Dataset

Source: UCI Machine Learning Repository

Size: ~100,000 inpatient encounters (1999–2008)

Features: Demographics, diagnoses, treatments, lab procedures, medications

Outcome variable:
readmitted_30 → YES (readmitted within 30 days) or NO

Raw and processed data files are not included in this repository due to file size limitations and best practices. Instructions to recreate them are provided in the data/README.md file.

**Tools & Technologies**

R: tidyverse, janitor

Visualization: ggplot2

Modeling & evaluation: caret, pROC, randomForest

Version control: Git & GitHub

**Project Workflow**

**Data Loading & Cleaning**

Key steps included:

Loading the raw UCI diabetes dataset

Standardizing column names

Replacing "?" placeholders with missing values

Creating the binary outcome variable (readmitted_30)

Converting key variables (age, race, gender, admission characteristics) into categorical factors

Exporting a cleaned, analysis-ready dataset

Script: scripts/01_load_clean.R

**Exploratory Data Analysis (EDA)**

EDA focused on understanding patient demographics, clinical complexity, and hospitalization patterns.

Analyses included:

Time in hospital by readmission status

Readmission proportion by age group

Distribution of diagnoses, laboratory procedures, and medications

Descriptive summaries of demographic variables

Key visualizations:

Boxplot of time in hospital by readmission status

Bar chart of readmission proportions across age groups

Script: scripts/02_eda.R
Figures saved in: outputs/figures/

**Predictive Modeling**

Two baseline classification models were built.

**Logistic Regression**

Trained on a 20,000-row sample for computational efficiency

Predictors included age, time in hospital, number of diagnoses, laboratory procedures, medications, admission and discharge characteristics, race, and gender

Performance assessed using confusion matrix and ROC–AUC

Observed AUC: approximately 0.55–0.57

**Random Forest**

200-tree random forest with tuned parameters

Captured nonlinear relationships and interactions

Evaluated using confusion matrix and ROC–AUC

Observed AUC: approximately 0.57–0.58

Script: scripts/03_model.R

**Variable Importance**

Random forest variable importance analysis identified the strongest predictors of readmission risk:

Number of laboratory procedures

Number of medications

Time in hospital

Number of diagnoses

Age

Admission and discharge type

A ranked importance plot is included in the outputs folder.

**Results & Key Insights**

Readmission risk increases with age, especially in older populations

Clinical complexity (labs, medications, diagnoses) strongly predicts readmission

Readmitted patients tend to have slightly longer hospital stays

Administrative transitions during admission and discharge play an important role

Predictive performance (AUC ≈ 0.57) is typical for models using administrative hospital data alone

These findings suggest that enhanced clinical, outpatient follow-up, and social determinants data are likely required for substantial improvement in readmission prediction.

**How to Run the Project**

Clone the repository to your local machine

Download the raw dataset from the UCI Machine Learning Repository

Place the raw CSV file in the data/raw/ directory

Run the scripts in the following order:

scripts/01_load_clean.R

scripts/02_eda.R

scripts/03_model.R

**Repository Structure**

data/ — Processed data descriptions (data file excluded)

scripts/ — R scripts for cleaning, EDA, and modeling

outputs/figures/ — Key visualizations

outputs/models/ — Model summaries and importance tables

**Contact**

Aditya Kumar
Public Health Data Analyst | Epidemiology | R | Python | SQL
Email: neplusultraa@gmail.com
