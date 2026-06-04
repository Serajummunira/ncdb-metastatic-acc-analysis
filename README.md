# ncdb-metastatic-acc-analysis
Data analysis for a medical research paper on                     treatment patterns and survival outcomes in de novo                     metastatic adenoid cystic carcinoma using NCDB (N=541)
# Treatment Patterns and Outcomes in De Novo Metastatic Adenoid Cystic Carcinoma
### National Cancer Database (NCDB) Analysis | 2004–2023
---

## 📌 Project Overview

This is a **real-world medical data analysis project** conducted as part of 
a peer-reviewed research paper on adenoid cystic carcinoma (ACC) — a rare 
salivary gland cancer. The study examines treatment patterns and survival 
outcomes in 541 patients with de novo metastatic ACC using data from the 
National Cancer Database (NCDB).

> ⚠️ **Note:** The raw NCDB data files (.dat) are not included in this 
> repository due to the NCDB Data Use Agreement which prohibits 
> redistribution. This repository contains the analysis code, figures, 
> and results only.

---

## 🎯 Research Aims

- **Aim 1:** Describe treatment patterns and trends in de novo metastatic ACC
- **Aim 2:** Evaluate the impact of surgical resection on overall survival 
  using multiple causal inference methods

---

## 📊 Dataset

| Feature | Details |
|---|---|
| **Data Source** | National Cancer Database (NCDB) PUF 2023 |
| **Diagnosis Years** | 2004 – 2023 |
| **Raw Records Searched** | 644,758 across 10 site-specific files |
| **Final Cohort** | **541 patients** with de novo metastatic ACC |
| **Raw Columns** | 154 per file |
| **Analysis Columns** | 55 (after cleaning) |
| **Cancer Type** | Adenoid Cystic Carcinoma (ICD-O-3 histology 8200) |
| **Stage** | M1 (distant metastasis at diagnosis) |

---

## 🔬 Key Findings

| Finding | Result |
|---|---|
| Median Overall Survival | **32.2 months** |
| 1-year OS | 73.0% |
| 3-year OS | 46.5% |
| 5-year OS | 30.2% |
| Surgery HR (multivariable Cox) | **0.67 (0.55–0.81), p<0.001** |
| Surgery benefit consistency | Significant in **14/15 subgroups** |
| R0 margin rate | 36.1% (reflects aggressive disease) |
| Best treatment modality | Surgery + Radiation therapy |

---

## 📁 Repository Structure

├── notebooks/         # Google Colab analysis notebook
├── figures/           # All 9 publication-quality figures (300 DPI)
├── tables/            # All 6 results tables (CSV format)
├── docs/              # Methods, Results, and Analysis report (Word)
└── requirements.txt   # Python dependencies

---

## 🛠️ Methods & Statistical Analysis

### Data Preprocessing
- Loaded 10 fixed-width NCDB .dat files using `pandas.read_fwf()`
- Applied sequential inclusion criteria to identify 541 eligible patients
- Reduced 154 columns to 55 analysis variables

### Statistical Methods
| Method | Purpose |
|---|---|
| Kaplan-Meier + Log-rank test | Survival curves (9 figures) |
| Multivariable Cox Regression | Primary survival analysis |
| Propensity Score Overlap Weighting | Causal inference (N=479) |
| Propensity Score Matching (1:1 NNM) | Causal inference (N=248, 124 pairs) |
| 6-Month Landmark Analysis | Eliminate immortal time bias (N=473) |
| Instrumental Variable (2SRI) | Unmeasured confounding (F-stat=11.59) |
| Subgroup Analysis | 15 prespecified subgroups |

### Libraries Used
```python
pandas          # Data manipulation
numpy           # Numerical operations  
lifelines       # Survival analysis (KM, Cox regression)
scikit-learn    # Propensity score estimation and matching
statsmodels     # IV first-stage regression (Wald F-test)
scipy.stats     # Chi-square and Mann-Whitney U tests
matplotlib      # All figures (300 DPI)
```

---

## 📈 Figures

| Figure | Description |
|---|---|
| Fig 1 | Overall survival — full cohort (N=541) |
| Fig 2 | KM: Surgery vs. No Surgery ⭐ Primary figure |
| Fig 3 | KM: By treatment modality (6 groups) |
| Fig 4 | KM: Academic vs. Non-academic facility |
| Fig 5 | Cox regression forest plot |
| Fig 6 | KM: After propensity score matching |
| Fig 7 | Subgroup forest plot (15 subgroups) |
| Fig 8 | Treatment utilization trends over time |
| Fig 9 | 6-month landmark analysis |

---

## 📋 Tables

| Table | Description |
|---|---|
| Table 1 | Baseline characteristics (Surgery vs No Surgery, N=541) |
| Table 2 | Multivariable Cox regression — primary analysis |
| Table 3 | Cox regression in PS matched cohort (N=248) |
| Table 4 | Subgroup analysis (15 subgroups) |
| Table 5 | Surgical extent and quality metrics (N=269) |
| Table 6 | Comprehensive sensitivity analysis (7 methods) |

---

## ⚙️ How to Run the Analysis

1. Open `notebooks/ACC_Analysis_Complete.ipynb` in Google Colab
2. Mount your Google Drive
3. Place the NCDB .dat files in `/content/drive/MyDrive/NCDB_ACC/`
4. Run all cells in order

```python
# Install required libraries
pip install lifelines scikit-learn statsmodels tabulate
```

---

## 📝 Notes

- This analysis was performed as part of a collaboration with a 
  supervising physician for a manuscript submission
- The Introduction and Discussion sections of the paper were written 
  by the physician co-author
- All analyses were performed in Python 3 using Google Colab
- All figures were saved at 300 DPI for publication quality

---

## 👤 Author

**Serajum Munira**  
Data Analyst  
inkedin.com/in/serajum-munira-290628243  
smunira@ualr.edu

---

## 📄 License

This project is licensed under the MIT License.  
The underlying NCDB data is subject to the NCDB Data Use Agreement 
and cannot be redistributed.
