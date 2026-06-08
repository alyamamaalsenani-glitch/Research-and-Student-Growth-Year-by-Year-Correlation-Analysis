# Research and Student Growth — Year-by-Year Correlation Analysis

This repository contains a comprehensive data analytics and statistical modeling project designed to evaluate and track the relationship between academic research outputs, allocated funding, and shifting student populations over an extended timeline. 

The primary objective is to engineer a central master time-series index table and quantify how institutional research intensity metrics interact with undergraduate and postgraduate dynamics.

---

## 📊 Project Overview & Objectives
Institutions often run multiple fragmented transactional databases for tracking student registrations, grant disbursements, and publication records. This project breaks down those silos by:
1. **Consolidating 4 Independent Datasets** (Grants, Publications, Undergraduates, Postgraduates) into a unified master timeline.
2. **Aligning Multi-Format Timestamps** by standardizing academic-year boundaries (`YYYY-YYYY`) to precise calendar ending periods.
3. **Exploratory Data Analysis (EDA)** via multi-axis trends and comparative visual distributions.
4. **Statistical Correlation & Regression Modeling** using Pearson coefficients ($r$), R-squared ($R^2$), $p$-values, and multi-year predictive lag models to discover if research activity acts as a leading indicator for postgraduate recruitment.

---

## 🗂️ Data Sources Architecture
The framework processes and shapes data from four foundational scopes:

1. **Research Projects (`Growth in the number of research projects...xlsx`):** Tracks counts and allocated funding amounts (in Omani Rials - OMR) across 5 competitive grant mechanisms: *External, Internal, Strategic, Joint,* and *National Research* grants.
2. **Research Papers (`Growth in number of research papers...xlsx`):** Tracks scholarly dissemination metrics broken down by *Journal Publications* vs. *Conference Presentations*.
3. **Undergraduate Students (`Growth of Undergraduate students.xlsx`):** Captures total *Admitted, Registered,* and *Graduated* volumes for Diploma and Bachelor tracks, including cross-tabulated gender distributions.
4. **Postgraduate Students (`Growth of postgraduate students.xlsx`):** Captures enrollment health across *Postgraduate Diploma, Masters,* and *Doctorate (Ph.D.)* programs.

---

## 🛠️ Tech Stack & Dependencies
The pipeline is written in **Python 3.x** and relies on standard modern scientific computing packages:
* **Pandas**: Matrix transformations, multi-index pivoting, missing-data reconciliation, and merge operations.
* **NumPy**: Vectorized data alignment and mathematical calculations.
* **Matplotlib**: Canvas configurations and multi-axis plot structures.
* **Seaborn**: Statistical visualizations, trend density plotting, and correlation heatmaps.
* **SciPy (stats)**: Statistical tests, Pearson correlation evaluations, and linear regression parameters ($p$-values, standard errors).

---

## ⚙️ Data Pipeline Pipeline Steps

### 1. Extraction & Feature Alignment
* Trims whitespace and extracts clean strings from dirty column names.
* Splits complex academic period markers (e.g., mapping split periods like `2025-2026` to chronological integer indices like `2026`) to preserve structural cohesion with raw calendar year data.

### 2. Multi-Dimensional Pivoting
Transforms raw records into distinct feature matrix entities using pivot techniques:
* Summarizes project counts and sum totals of multi-million OMR fund allocations by grant categories.
* Structures concurrent columns representing distinct registration segments and degree tiers simultaneously.

### 3. Synchronization & Master Generation
* Executes chronological outer joins to build a continuous unified database covering historical trajectories.
* Resolves structural zeros caused by lagging reporting cycles safely without introducing skew into long-term regression profiles.

---

## 📈 Analysis & Statistical Modeling Techniques

### Correlation & Regression Matrix
The system loops across every logical intersection pair between Research Indicators ($X$) and Student Demographics ($Y$). For every relationship, it calculates:
* **Pearson Correlation Coefficient ($r$):** Detects strength and direction.
* **Coefficient of Determination ($R^2$):** Measures the percentage of variance explained by the trend.
* **Statistical Significance ($p$-value):** Filters out noise and random variances ($p < 0.05$).

### Predictive Lag Modeling
Recognizing that research funding can take years to translate into student growth, the notebook evaluates time-shifted dynamics:
$$\text{Driver}(t) \longrightarrow \text{Outcome}(t + \text{Lag})$$
The system iteratively tests shift offsets (e.g., 1-year, 2-year, and 3-year lags) to detect if heightened institutional funding accurately predicts future surges in high-tier Doctorate registrations.

---

## 🚀 How To Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/research-student-growth-analysis.git](https://github.com/YOUR_USERNAME/research-student-growth-analysis.git)
   cd research-student-growth-analysis   
