# Vaginal-candidiasis-analysis
Prevalence &amp; risk factor analysis of vaginal candidiasis- Makerere University Hospital
# Prevalence and Risk Factors Associated With Vaginal Candidiasis Among Female Students at Makerere University Hospital

This repository contains the data analysis workflow (SPSS + Python) for the study:

**“Prevalence and Risk Factors Associated With Vaginal Candidiasis Among Female Students Attending Makerere University Hospital.”**

The project integrates:
- Statistical analysis done in **SPSS**
- Reproducible data visualizations created in **Python**
- Clean documentation so others can follow the workflow

---

##  Project Overview

Vaginal candidiasis is a common fungal infection among reproductive-age women.  
This study assessed:

- **Prevalence of vaginal candidiasis**
- **Sociodemographic and behavioral risk factors**
- **Microbiological findings (Wet Prep vs Gram Stain)**
- **Predictors of infection using logistic regression**

---

##  Tools Used
### **Software**
- **SPSS    26** — Primary statistical analysis
- **Python 3.10** — Visualization and analytical replication

### **Python Libraries**
- pandas  
- numpy  
- matplotlib  
- seaborn  

---

##  Key Analyses & Visualizations

---

### 1️ Heatmap of Chi-Square Values
Shows risk factors significantly associated with vaginal candidiasis.

Python script: `scripts/chi_square_heatmap.py`

```python
import pandas as pd
import matplotlib.pyplot as plt

# Data preparation
data = {
    'Risk Factor': [
        'Antibiotic use',
        'Sexual activity',
        'Number of sexual partners',
        'Intercourse (last 3 mo.)',
        'Frequency of sexual intercourse',
        'Contraceptive use',
        'Underwear change frequency'
    ],
    'Chi-square': [5.758, 7.364, 27.626, 5.415, 18.732, 15.676, 6.066],
    'p-value': [0.016, 0.007, 0.000, 0.020, 0.000, 0.000, 0.014]
}

df = pd.DataFrame(data).set_index('Risk Factor')

def significance_stars(p):
    if p < 0.001:
        return '***'
    elif p < 0.01:
        return '**'
    elif p < 0.05:
        return '*'
    else:
        return ''

df['Significance'] = df['p-value'].apply(significance_stars)

plt.figure(figsize=(8, 4))
plt.imshow(df[['Chi-square']], aspect='auto')
plt.colorbar(label='Chi-square value')
plt.xticks([0], ['Chi-square'])
plt.yticks(range(len(df.index)), df.index)

for i, (chi2, stars) in enumerate(zip(df['Chi-square'], df['Significance'])):
    plt.text(0, i, f'{chi2:.2f}{stars}', ha='center', va='center')

plt.title('Heatmap of Chi-square Values with Significance Levels')
plt.tight_layout()
plt.show()
```

---

### 2️ Prevalence Pie Chart
Displays proportion of positive vs negative cases among 217 participants.

Python script: `scripts/prevalence_piechart.py`

```python
import matplotlib.pyplot as plt

labels = ['Negative (66.4%)', 'Positive (33.6%)']
sizes = [144, 73]

plt.figure(figsize=(6, 6))
plt.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=90)
plt.title('Prevalence of Vaginal Candidiasis among Participants (N = 217)')
plt.axis('equal')  # Ensures the pie is circular
plt.show()
```

---

### 3️ Adjusted Odds Ratio Heatmap
Visualizes multivariate logistic regression results with significance stars.

Python script: `scripts/adjusted_or_heatmap.py`

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Example logistic regression results (replace with actual output)
data = {
    'Predictor': ['Antibiotic use', 'Sexual activity', 'Contraceptive use'],
    'AOR': [2.5, 1.8, 0.7],
    'p-value': [0.004, 0.012, 0.08]
}

df = pd.DataFrame(data).set_index('Predictor')

def sig_stars(p):
    if p < 0.001: return '***'
    if p < 0.01: return '**'
    if p < 0.05: return '*'
    return ''

df['Significance'] = df['p-value'].apply(sig_stars)

plt.figure(figsize=(6, 4))
sns.heatmap(df[['AOR']], annot=df[['AOR']].round(2), cmap='coolwarm', center=1.0, fmt='.2f')
plt.title('Adjusted Odds Ratios (Logistic Regression)')
plt.ylabel('Predictors (stars indicate significance)')
plt.tight_layout()
plt.show()
```

---

### 4️ Bar Graph: Wet Prep vs Gram Stain Findings
Compares detection rates of microorganisms using Wet Prep vs Gram Stain.

Python script: `scripts/microbiology_bargraph.py`

```python
import pandas as pd
import matplotlib.pyplot as plt

 microbiology findings 
data = {
    'Organism': ['Candida', 'Trichomonas', 'Clue cells'],
    'Wet Prep': [40, 10, 25],
    'Gram Stain': [55, 0, 30]
}

df = pd.DataFrame(data).set_index('Organism')

df.plot(kind='bar', figsize=(8, 5))
plt.title('Microbiology Findings: Wet Prep vs Gram Stain')
plt.ylabel('Count Detected')
plt.xlabel('Organism / Finding')
plt.legend(title='Method')
plt.tight_layout()
plt.show()
```
---

##  SPSS Output

The complete SPSS `.spv` output file is stored in:

```
analysis/SPSS/spss_output.spv
```

It contains:

- Descriptive statistics  
- Chi-square tests  
- Logistic regression (adjusted and crude ORs)  
- Cross-tabulations  
- Frequency tables  

---

##  Reproducibility

To run the Python scripts, first install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

Then execute each script:

```bash
python scripts/chi_square_heatmap.py
python scripts/prevalence_piechart.py
python scripts/adjusted_or_heatmap.py
python scripts/microbiology_bargraph.py
```

---

##  Notes

- Raw participant data is not included for confidentiality.  
- SPSS output is preserved exactly as analyzed.  
- Python files reproduce all visuals used in the final report.  

---

##  Author

**Echou Joel**  
Biomedical Laboratory Scientist • Researcher • Data Analyst  
ECHEPO Research & Analytics  
Email: echoujoel562@gmail.com  

---

##  Citation (If Used in Academic Work)

Echou Joel (2025). *Prevalence and Risk Factors Associated With Vaginal Candidiasis Among Female Students Attending Makerere University Hospital.*  
GitHub Repository: [https://github.com/echoujoel/vaginal-candidiasis-analysis](https://github.com/echoujoel/vaginal-candidiasis-analysis)





         
