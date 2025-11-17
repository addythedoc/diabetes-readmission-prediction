

# **Diabetes Readmission Prediction – Data Analytics & Modeling Project**

## 📌 **Overview**

This project demonstrates a complete end-to-end **data science workflow in R**, beginning with loading and cleaning the raw UCI hospital dataset, performing exploratory data analysis (EDA) on patient characteristics, building baseline predictive models (Logistic Regression & Random Forest), and interpreting key drivers of 30-day hospital readmission.

A concise project report and visual outputs summarize key findings.

This project demonstrates skills in **R programming, data cleaning, EDA, modeling, visualization, and healthcare analytics.**

---

## 📂 **Dataset**

**Name:** Diabetes 130-US Hospitals Readmission Dataset
**Source:** UCI Machine Learning Repository
**Rows:** ~100,000 hospital encounters
**Columns:** Demographics, diagnoses, treatments, lab procedures, medications
**Target Variable:**
`readmitted_30` → YES (readmitted within 30 days) or NO

This dataset is widely used for clinical readmission prediction research.

---

## 🛠 **Tools & Technologies**

* **R (tidyverse, janitor)** → Data cleaning & processing
* **ggplot2** → Exploratory data visualization
* **caret** → Train/test split, evaluation
* **pROC** → ROC curves & AUC
* **randomForest** → Non-linear predictive modeling
* **GitHub** → Version control & open-source sharing

---

## 📘 **Project Steps**

### **1. Data Loading & Cleaning (R)**

* Loaded raw CSV from UCI dataset
* Cleaned inconsistent column names
* Converted `"?"` entries to proper missing values
* Created binary outcome variable (`readmitted_30`)
* Converted key fields (age, race, gender, admissions) into categorical factors
* Exported cleaned dataset for further work

📄 *Script:* `R/01_load_clean.R`

---

### **2. Exploratory Data Analysis (EDA)**

EDA was conducted to understand patient demographics, clinical complexity, and readmission patterns.

Key analyses included:

* Time in hospital vs readmission
* Readmission proportion by age group
* Summary of lab procedures, diagnoses, and medications
* Distribution of demographic features

Visuals produced:

* **Boxplot:** Time in hospital by readmission status
* **Bar Chart:** Readmission rate across age groups

📄 *Script:* `R/02_eda.R`
📁 *Plots:* `outputs/plots/`

---

### **3. Predictive Modeling (R)**

Two baseline models were built:

#### **a. Logistic Regression**

* Trained on a 20,000-row sample for computational efficiency
* Interpretable coefficients
* Predictors included
  `age`, `number_diagnoses`, `num_lab_procedures`, `num_medications`, etc.
* **AUC: 0.5738**

#### **b. Random Forest**

* 200 trees, mtry = 4
* Captures nonlinear patterns
* **AUC: 0.5695**

📄 *Script:* `R/03_model.R`

---

### **4. Variable Importance Analysis**

Random Forest importance revealed:

* Number of lab procedures
* Number of medications
* Time in hospital
* Number of diagnoses
* Age
* Admission/Discharge type

These variables strongly influence readmission risk.

📊 *Plot:* `rf_variable_importance_top20.png`

---

## 📊 **Results & Insights (Summary)**

* Readmission risk **increases strongly with age**, especially 70+
* Clinical complexity (labs, meds, diagnoses) predicts readmission
* Length of stay is modestly higher in readmitted patients
* Administrative transitions (admission/discharge type) matter
* Models achieve **AUC ~0.57**, typical for administrative hospital data
* Suggests value of adding comorbidity scores, follow-up data, and richer clinical variables

---

# ▶ **How to Run This Project**

### **1. Clone the Repository**

```
git clone https://github.com/yourusername/diabetes-readmission-prediction.git
```

### **2. Install Required Libraries**

```r
install.packages(c("tidyverse", "janitor", "caret", "pROC", "randomForest"))
```

### **3. Run Data Cleaning**

```r
source("R/01_load_clean.R")
```

### **4. Run EDA**

```r
source("R/02_eda.R")
```

### **5. Run Modeling**

```r
source("R/03_model.R")
```

---

## 📧 **Contact**

**Aditya Kumar**
Public Health Data Analyst | Epidemiology | R | Python | SQL
📩 Email: **[neplusultraa@gmail.com]**

---



