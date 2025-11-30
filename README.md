# Vaginal-candidiasis-analysis
Prevalence &amp; risk factor analysis of vaginal candidiasis- Makerere University Hospital
# 🧫 Prevalence and Risk Factors Associated With Vaginal Candidiasis Among Female Students at Makerere University Hospital

This repository contains the data analysis workflow (SPSS + Python) for the study:

**“Prevalence and Risk Factors Associated With Vaginal Candidiasis Among Female Students Attending Makerere University Hospital.”**

The project integrates:
- Statistical analysis done in **SPSS**
- Reproducible data visualizations created in **Python**
- Clean documentation so others can follow the workflow

---

## 📌 Project Overview

Vaginal candidiasis is a common fungal infection among reproductive-age women.  
This study assessed:

- **Prevalence of vaginal candidiasis**
- **Sociodemographic and behavioral risk factors**
- **Microbiological findings (Wet Prep vs Gram Stain)**
- **Predictors of infection using logistic regression**

---

## 📊 Tools Used
### **Software**
- **SPSS 25–29** — Primary statistical analysis
- **Python 3.10+** — Visualization and analytical replication

### **Python Libraries**
- pandas  
- numpy  
- matplotlib  
- seaborn  

---

## 📁 Repository Structure

vaginal-candidiasis-analysis/
│
├── README.md
│
├── data/
│   ├── raw/
│   │   └── dataset_description.txt   (no raw data for confidentiality)
│   └── processed/
│       └── cleaned_dataset.csv       
│
├── analysis/
│   ├── SPSS/
│   │   └── spss_output.spv           
│   ├── Python/
│   │   ├── chi_square_heatmap.ipynb
│   │   ├── prevalence_piechart.ipynb
│   │   ├── adjusted_or_heatmap.ipynb
│   │   └── microbiology_bargraph.ipynb
│
├── scripts/
│   ├── chi_square_heatmap.py
│   ├── prevalence_piechart.py
│   ├── adjusted_or_heatmap.py
│   └── microbiology_bargraph.py
│
├── visuals/
│   ├── chi_square_heatmap.png
│   ├── prevalence_pie_chart.png
│   ├── adjusted_or_heatmap.png
│   └── microbiology_bargraph.png
│
└── docs/
    └── detailed_report.pdf          
