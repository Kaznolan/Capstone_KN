# 🌍 Global Stroke Risk and Health Insights Dashboard

## 🧭 Project Overview
This project explores the relationship between **individual health factors**, **lifestyle variables**, and **global health indicators** to identify and visualize stroke risk patterns worldwide.  
By combining two public datasets — a *stroke prediction dataset* and a *global life expectancy dataset* — the Tableau dashboard offers insights into how medical, demographic, and socioeconomic factors influence stroke prevalence and life expectancy.

The analysis integrates **Python for data cleaning and analysis** and **Tableau for visualization and storytelling**, aligned with professional data analytics and ML-driven workflows.

---

## 🎯 Business Problem
Strokes are one of the leading causes of death and disability worldwide. Understanding how to predict a stroke can help public health policymakers, hospitals, and research institutions allocate resources effectively.

This project aims to answer:
- What demographic and lifestyle factors increase stroke risk?
- How do national health indicators (GDP, education, life expectancy) relate to stroke prevalence?
- Can ML be used to help identify individuals at risk?
- How can data storytelling make these insights understandable for non-technical audiences?
- The Business stakeholders have requested a

---

## 💡 Objectives
1. Identify key stroke risk factors from individual-level health data (Kaggle).  
2. Examine global patterns using life expectancy, education, and GDP indicators.  
3. Develop a Python-based predictive model for stroke likelihood.  
4. Build an interactive Tableau dashboard for decision-makers.  
5. Ensure data ethics, reproducibility, and transparency throughout.

---

## 🧪 Hypotheses
1. Higher glucose, BMI, and cardiovascular disease increase stroke risk.  
2. Age significantly affects stroke probability.  
3. Urban residents and private-sector workers show higher stroke rates.  
4. Countries with higher GDP and life expectancy have lower stroke rates.  
5. More years of schooling correlate with lower stroke risk.  
6. Hypertension is the strongest single modifiable risk factor for stroke (WHO).  
7. Psychosocial stress, depression, social isolation, or loneliness increase stroke risk (AHA).  
8. Physical inactivity / sedentary behaviour increases risk of stroke.

---

## 📊 Datasets Used

| Dataset | Description | Source |
|---|---|---|
| **Healthcare Stroke Data** | 5,110 individual records with health and demographic features used to predict stroke likelihood. | [Kaggle – Stroke Prediction Dataset](https://www.kaggle.com/fedesoriano/stroke-prediction-dataset) |
| **Life Expectancy Data** | WHO dataset containing country-level indicators (life expectancy, GDP, schooling, etc.). | [Kaggle – Life Expectancy (WHO)()]https://www.kaggle.com/datasets/adamsmith852/life-expectancy-data-gho) |

Both datasets are **publicly available and anonymized**.

---

## 🧹 Data Cleaning Summary

### 1) Stroke Dataset
- Column names standardized to `snake_case`.  
- Missing `bmi` imputed with median; missing `smoking_status` → `"Unknown"`.  
- Standardized categorical fields (e.g., `work_type`, `gender`).  
- Outliers capped for `bmi` and `avg_glucose_level` via IQR.  
- Engineered `age_band` and synthetic `country` for mapping.  
- Duplicates removed; ID uniqueness validated.

### 2) Life Expectancy Dataset
- Sorted by `country` and `year`.  
- Numeric columns forward-filled within country; categorical columns imputed by mode within country.  
- Duplicates removed; invalid entries filtered; latest year per country selected.  
- Kept `country`, `life_expectancy`, `gdp`, `schooling`.

### 3) Merge
- Merged on `country`.  
- Computed stroke rate per country for visualization and correlation analysis.  
- Exported final file: `merged_health_data.csv`.

---

## 🧮 Exploratory Data Analysis (EDA)
Python (Pandas, Matplotlib, Seaborn) produced:
- Stroke distribution by age and gender.  
- Correlation heatmap of numeric variables.  
- BMI and glucose distributions by stroke outcome.  
- Global scatter plots comparing GDP, life expectancy, and stroke prevalence.  

These insights informed the dashboard and hypotheses validation.

---

## 🤖 Predictive Modeling
**Model:** Logistic Regression (baseline)

| Step | Description |
|---|---|
| **Features** | Age, BMI, Glucose, Hypertension, Heart Disease |
| **Split** | 80% train / 20% test |
| **Scaling** | StandardScaler |
| **Metrics** | Accuracy, Precision, Recall, F1-Score, ROC-AUC |

> **Note:** Final metric values to be reported after training and evaluation are complete.

---

## 📈 Tableau Dashboard
**Title:** 🌍 *Global Stroke Risk and Health Insights*  
**Tool:** Tableau Public

### Key Visuals
1. 🌍 **World Map** — Stroke rate per country (choropleth).  
2. 👥 **Demographics** — Stroke rate by age band and gender.  
3. 🚬 **Lifestyle** — Smoking status, work type, residence type.  
4. 💰 **Economics** — GDP vs. stroke rate.  
5. 🎓 **Education & Health** — Schooling vs. life expectancy.  
6. 📊 **KPI Cards** — Total stroke cases, average age, GDP, life expectancy.  
7. ⚖️ **Ethics Panel** — Privacy and AI-ethics notice.

**Filters:** Country | Gender | Age Band | Year

---

## ⚖️ Ethical & Privacy Considerations
- All datasets are **publicly available and anonymized**.  
- No personally identifiable information (PII).  
- Predictive results are **for educational purposes** and not clinical decision-making.  
- Ethical AI use: applied for **automation, ideation, summarization**, and reproducible analysis.

---

## 🧠 AI Integration (LO4)
- **AI for Ideation:** Help with finding Hypotheses ( acting as Business), business requirements ( acting as business), dashboard wireframe suggestions (acting as business stakeholder).  
- **AI for Code:** Code review, refactoring suggestions.  
- **AI for Modeling:** Feature selection guidance and baseline model setup.  
- **AI for Storytelling:** README structure improvements, narrative clarity, and framing for non-technical audiences.

---

## 🧩 Learning Outcomes Mapping

| Learning Outcome | Demonstrated In |
|---|---|
| **LO1** | Statistical concepts (EDA, distributions, correlations) |
| **LO2** | Python data manipulation and visualization |
| **LO3** | Healthcare data analysis and interpretation |
| **LO4** | AI assistant integrated into workflow |
| **LO5** | Data cleaning, processing, storage, and export |
| **LO6** | Ethical reflection section |
| **LO8** | Dashboard and README storytelling |
| **LO10** | Maintenance and continuous learning plan |

---

## 🔄 Maintenance and Future Work

| Area | Improvement Plan |
|---|---|
| Data | Automate dataset refresh via WHO API / scheduled ETL |
| Model | Add Random Forest & Gradient Boosting; hyperparameter tuning |
| Dashboard | Integrate Tableau Prep; parameterized data extracts |
| Ethics | Add bias/fairness checks and model cards |

---

## 💾 File Structure
📁 **CAPSTONE_KN/**
- 🔁 **.venv/**
- 📂 **Assets/**
  - 🖼️ **Images/**
    - 📄 markdown-cheat-sheet.md
- 📊 **Dashboards/**
  - 📁 Tableau_data/
- 📦 **Data/**
  - 🧹 Cleaned/
  - 🧾 Raw/
- 📘 **jupyter_notebooks/**
  - 📓 1Data_Analysis.ipynb  
  - 📓 2DCL.ipynb  
  - 📓 3EDA.ipynb  
  - 📓 4ML.ipynb  
  - 📓 5Data_Visualisations.ipynb
- 🧾 **Readme_items/**
  - 📄 Conclusions.md

---

## 🎯 **Release Plan**

*(Times are Europe/London, 24-hour clock; dates dd/mm/yyyy.)*

| # | Milestone | Release | Date | Time |
|---|------------|----------|------|------|
| 1 | Environment setup & README draft | R1 | 08/10/2025 | 12:00 |
| 2 | Data analysis completion | R2 | 08/10/2025 | 17:00 |
| 3 | Requirements update | R3 | 09/10/2025 | 11:30 |
| 4 | Clean data finalized | R4 | 10/10/2025 | 16:30 |
| 5 | Exploratory analysis (EDA) | R5 | 12/10/2025 | 18:30 |
| 6 | ML baseline model | R6 | 12/10/2025 | 17:00 |
| 7 | General modifications (TBC) | R7 | 13/10/2025 | 19:00 |
| 8 | Data visualization | R8 | 13/10/2025 | 06:00 |
| 9 | Tableau dashboard | R9 | 13/10/2025 | 12:00 |
| 10 | Review & documentation update | R10 | 13/10/2025 | 16:00 |

---

## 📖 **Glossary**

**AI (Artificial Intelligence)** 
Computer systems that perform tasks requiring human-like intelligence, such as pattern recognition and prediction. 

**EDA (Exploratory Data Analysis)** 
The process of visually and statistically exploring datasets to summarize their main characteristics. 

**ETL (Extract, Transform, Load)** 
A data pipeline process that collects data from multiple sources, cleans/transforms it, and loads it into a final dataset or database. 

**GDP (Gross Domestic Product)**  
A measure of a country’s total economic output and indicator of economic health.

**Hypertension**  
High blood pressure — a major modifiable risk factor for stroke. 

**IQR (Interquartile Range)**  
A measure of statistical dispersion used to detect and handle outliers in numeric data. 

**KPI (Key Performance Indicator)**  
Quantitative metrics used to track progress toward a specific goal. 

**ML (Machine Learning)**  
A subset of AI that uses data and algorithms to imitate how humans learn, allowing systems to improve automatically. 

**PII (Personally Identifiable Information)**  
Any data that can identify an individual (e.g., name, ID, address). This project uses no PII.

**ROC-AUC (Receiver Operating Characteristic – Area Under Curve)** 
A metric that measures how well a classification model distinguishes between classes. 

**Snake Case**  
A naming convention where words are lowercase and separated by underscores (e.g., `avg_glucose_level`). 

**StandardScaler** 
A preprocessing tool in scikit-learn that normalizes numeric data by removing the mean and scaling to unit variance. 

**Tableau**  
A business intelligence and data visualization tool used to create dashboards and interactive data stories. 

**WHO (World Health Organization)**  
The United Nations agency responsible for international public health. 

---

## 📚 **References**

- World Health Organization (WHO) Global Health Data  
- Kaggle Datasets: Stroke Prediction & Life Expectancy  
- Scikit-learn, Pandas, Matplotlib Documentation  
- Tableau Public Resources  
- Centers for Disease Control and Prevention (CDC). (2024). Stroke Risk Factors.
  U.S. Department of Health and Human Services.
  Retrieved from https://www.cdc.gov/stroke/risk-factors/index.html

- Benjamin, E. J., Muntner, P., Alonso, A., et al. (2019). Heart Disease and Stroke    Statistics—2019 Update: A Report From the American Heart Association. Circulation Research, 124(3), e437–e448.
https://www.ahajournals.org/doi/10.1161/circresaha.116.308398

 - Rastogi, P., & Nayak, R. (2019). Aging and Ischemic Stroke. Aging and Disease, 10(6),  1435–1446.
https://pmc.ncbi.nlm.nih.gov/articles/PMC6535078/

World Health Organization (2023) Global Health Estimates 2023: Disease burden by cause, age, sex, by country and by region, 2000–2019. Geneva: WHO. Available at: https://www.who.int/data/gho
 (Accessed: 12 October 2025).

World Health Organization (2021) WHO Global Health Observatory (GHO) data: Cerebrovascular disease (stroke). Available at: https://www.who.int/data/gho/data/themes/topics/topic-details/GHO/cerebrovascular-diseases
 (Accessed: 12 October 2025).

GBD 2019 Stroke Collaborators (2021) ‘Global, regional, and national burden of stroke and its risk factors, 1990–2019: a systematic analysis for the Global Burden of Disease Study 2019’, The Lancet Neurology, 20(10), pp. 795–820. DOI: 10.1016/S1474-4422(21)00252-0
.

Feigin, V.L., Stark, B.A., Johnson, C.O. et al. (2022) ‘Global, regional, and national burden of stroke and its risk factors, 1990–2021’, The Lancet Neurology, 21(10), pp. 934–953.

World Stroke Organization (2023) Global Stroke Fact Sheet 2023. Available at: https://www.world-stroke.org/
 (Accessed: 12 October 2025).

Naghavi, M. et al. (2017) ‘Global, regional, and national age–sex specific mortality for 264 causes of death, 1980–2016: a systematic analysis for the Global Burden of Disease Study 2016’, The Lancet, 390(10100), pp. 1151–1210.

World Bank (2023) World Development Indicators: Health and risk factors. Available at: https://data.worldbank.org/indicator
 (Accessed: 12 October 2025).

Johnson, W., Onuma, O., Owolabi, M. and Sachdev, S. (2016) ‘Stroke: a global response is needed’, Bulletin of the World Health Organization, 94(9), pp. 634–634A. DOI: 10.2471/BLT.16.181636
.

---

## 👤 **Author**

**Name:** Karen Nolan  
**Cohort:** Data Analytics with Artificial Intelligence Bootcamp — June-2025-wmcaa  
**Date:** October 2025  
**Email:** [kaznolan@googlemail.com](mailto:kaznolan@googlemail.com)  
**LinkedIn:** (add link)

---

## 🧾 **License**

This project uses only publicly available datasets and is intended for academic and educational purposes.
