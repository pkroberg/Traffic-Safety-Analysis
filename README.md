# U.S. Traffic Safety Analysis

**GitHub Repository:** https://github.com/pkroberg/Traffic-Safety-Analysis

---

## Overview

This notebook looks at traffic accident patterns across the United States using two datasets. The goal is to understand how factors like time of day, weather conditions, road features, and vehicle type relate to accident frequency and severity with a particular focus on motorcycle risk.

## Datasets I Used

### 1. US Accidents (Kaggle) — Primary Dataset
- **Source:** https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents
- **Coverage:** ~7.7 million accidents across the contiguous US, 2016–2023
- **Contents:** Accident severity, location, time, weather conditions, and road features
- **Note:** This file (~3GB) is too large to include in the repository. Download it from Kaggle and place `US_Accidents_March23.csv` in the same directory as this notebook.

### 2. FARS — Fatality Analysis Reporting System (NHTSA) — Motorcycle Risk Dataset
- **Source:** https://www.nhtsa.gov/file-downloads?p=nhtsa/downloads/FARS/
- **Coverage:** All fatal crashes in the US, 2016–2023
- **Contents:** Crash details including vehicle type, enabling motorcycle-specific fatality analysis
- **Files used:** `FARS{year}NationalCSV.zip` for years 2016–2023. 
- **Note:** This file is also too large to include in the repository. Download and unzip years 2016-2023 from the link above and place them in the same directory as this notebook.

## Why the need to merge these datasets?

The Kaggle dataset covers all accident severities but does not include vehicle type. It can't distinguish between car and motorcycle accidents. FARS covers only fatal crashes, but does record vehicle type. Since these datasets measure different things, they cannot be joined row-to-row. Instead, we use FARS to compute motorcycle fatality risk ratios by state and hour of day, then attach those ratios to the Kaggle data. This gives the primary dataset motorcycle-specific risk context without discarding non-fatal accidents.