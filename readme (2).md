# 🏥 BRFSS 2024 — Behavioral Health Data Analysis

> **AI-Assisted Data Analysis using Claude (Anthropic)**  
> Source: [CDC Behavioral Risk Factor Surveillance System — data.gov](https://data.cdc.gov/api/views/hn4x-zwk7/rows.csv?accessType=DOWNLOAD)

---

## 📋 Project Overview

This project demonstrates AI-assisted exploratory data analysis on a real government public health dataset from the CDC's Behavioral Risk Factor Surveillance System (BRFSS), 2024. The analysis covers **obesity/overweight classification** and **physical inactivity rates** across U.S. states, segmented by the "Other" race/ethnicity subgroup.

---

## 💬 Prompts Used

### Initial Data Request
> *"Perform a deep analysis, identify hidden trends, and generate technical diagrams or multi-tab report structures."*

### Follow-up Analysis
> *"So what states most active and what states least active?"*

---

## 🤖 What Claude Did

Given raw tab-separated BRFSS data pasted directly into the chat, Claude:

- **Parsed and cleaned** the raw government dataset (handling missing values, footnotes, and type conversions)
- **Identified hidden trends** including regional clustering, data availability gaps, and statistical precision issues
- **Generated a multi-panel visual dashboard** (8 charts in a single figure) using matplotlib
- **Built a 5-tab Excel report** with conditional formatting, color scales, KPI cards, and data quality auditing
- **Flagged statistical warnings** — e.g. Texas's overweight figure (47.3%) carries a ±19pp confidence interval on n=82

---

## 📊 Key Findings

### Most Active States *(lowest physical inactivity %)*
| Rank | State | Inactivity Rate |
|------|-------|----------------|
| 1 | 🟢 New Hampshire | 11.6% |
| 2 | 🟢 Maine | 13.5% |
| 3 | 🟢 Georgia | 14.2% |
| 4 | 🟢 Colorado | 15.6% |
| 5 | 🟢 Oregon | 17.2% |

### Least Active States *(highest physical inactivity %)*
| Rank | State | Inactivity Rate |
|------|-------|----------------|
| 1 | 🔴 Illinois | 33.1% |
| 2 | 🔴 Missouri | 30.7% |
| 3 | 🔴 Ohio | 28.8% |
| 4 | 🔴 Michigan | 28.4% |
| 5 | 🔴 New Jersey | 27.4% |

> **National Average: 22.8%**

### Hidden Trends Uncovered
- **Data availability gap:** Only 30% of states had reportable overweight data for the "Other" subgroup vs. 55% for physical inactivity — Southern states are nearly a complete blind spot
- **Midwest sedentary cluster:** IL, MO, OH, MI form a statistically consistent high-inactivity band
- **New England active pattern:** NH and ME show roughly half the national inactivity rate
- **Precision trap:** Texas's 47.3% overweight figure is statistically unreliable (CI width: 38.2pp, n=82)
- **Most reliable estimate:** New York (n=536) had the largest sample size in the dataset

---

## 📁 Files in This Repository

| File | Description |
|------|-------------|
| `BRFSS_Analysis_Dashboard.png` | 8-panel visual analysis dashboard |
| `BRFSS_2024_Analysis.xlsx` | 5-tab Excel report with full data, stats, and quality audit |

### Excel Report Tabs
1. **📋 Executive Summary** — KPI cards + 5 annotated key findings
2. **🏃 Physical Inactivity** — All 22 states with CI width flags, regional tags, deviation from national average
3. **⚖️ Overweight Status** — 3 reportable states with precision warnings + full missing-data inventory
4. **📊 Statistical Analysis** — Descriptive stats + regional breakdown
5. **🔍 Data Quality Audit** — Completeness rates and full record inventory with ✅/❌ status

---

## 🛠 Tools & Methods

- **AI Assistant:** Claude Sonnet (Anthropic) via claude.ai
- **Data Source:** CDC BRFSS 2024, `Race/Ethnicity: Other` subgroup — [data.gov](https://data.gov)
- **Libraries used by Claude:** `pandas`, `numpy`, `matplotlib`, `openpyxl`
- **Output formats:** `.xlsx` (multi-tab), `.png` (dashboard)

---

## ⚠️ Data Limitations

- Results represent only the **"Other" race/ethnicity subgroup** — not the full adult population
- Many states have **insufficient sample sizes** for this subgroup, leading to wide confidence intervals
- This is a **snapshot analysis** of a data excerpt, not the full BRFSS dataset
- Small n values (< 70) should be interpreted with caution

---

## 🔗 Data Source

- **Dataset:** Nutrition, Physical Activity, and Obesity — Behavioral Risk Factor Surveillance System
- **Publisher:** Centers for Disease Control and Prevention (CDC)
- **Portal:** [data.gov](https://catalog.data.gov/dataset/nutrition-physical-activity-and-obesity-behavioral-risk-factor-surveillance-system)
- **Direct download:** https://data.cdc.gov/api/views/hn4x-zwk7/rows.csv?accessType=DOWNLOAD

---

---

## 🧠 Skills Demonstrated

- **Prompt Engineering** — Directing an AI assistant to perform multi-layered data analysis from a single natural language prompt
- **Public Data Sourcing** — Locating and working with real government datasets from data.gov and CDC open data portals
- **Exploratory Data Analysis (EDA)** — Identifying distributions, outliers, missing data patterns, and regional trends
- **Data Cleaning** — Handling missing values, footnote symbols, mixed types, and suppressed data in raw government CSVs
- **Statistical Reasoning** — Interpreting confidence intervals, sample sizes, and precision limitations in survey data
- **Data Visualization** — Multi-panel dashboard design with matplotlib including bar charts, scatter plots, box plots, histograms, and deviation charts
- **Excel Report Building** — Multi-tab workbook creation with conditional formatting, color scales, KPI cards, and data quality audits using openpyxl
- **Critical Thinking** — Flagging unreliable estimates (e.g. wide CIs on small n) and communicating data limitations clearly
- **Technical Communication** — Translating raw health data into actionable findings for a non-technical audience
- **Python (pandas, matplotlib, numpy, openpyxl)** — End-to-end data pipeline from raw input to polished outputs
- **GitHub Portfolio Documentation** — Structuring project work into professional README format for public showcase

---

*Analysis generated with Claude AI — March 2026*
