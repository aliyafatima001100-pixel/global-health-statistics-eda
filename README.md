# Global Health Statistics: Data Cleaning & Exploratory Data Analysis

A data cleaning and exploratory data analysis (EDA) project on a global health dataset, built in Python with pandas, NumPy, SciPy, Matplotlib and Seaborn.

**Course:** ICA (group project), Institute of Business Administration (IBA), Karachi

**Team:** Lamiah Sahar, Aliya Fatima, Amna Iqbal, Faryal Zia

## Overview

The dataset has **80,277 records and 22 attributes** covering disease prevalence, incidence and mortality, healthcare access, demographics, treatment types and socioeconomic indicators for **20 countries and 20 diseases** across **2023 and 2024**.

The notebook cleans the data and explores it to see how healthcare resources and socioeconomic factors relate to mortality and recovery.

## What the notebook does

1. **Data cleaning**
   - Checked data types and converted five whole-number columns (Year, Population Affected, Average Treatment Cost, DALYs, Per Capita Income) from float to integer
   - Filled 696 missing cells (under 0.04% of the data): mean for rates, median for counts/costs/income, mode for categories and Year. These missing values were introduced deliberately for the course exercise (see "A note on the data")
   - Verified 0 missing values and 0 duplicate rows remain
2. **Univariate analysis:** summary statistics, boxplots, histograms, skewness and normality tests (`scipy.stats.normaltest`), bar and pie charts for categorical variables
3. **Trend analysis:** 2023 vs 2024 comparison of key indicators
4. **Bivariate analysis:** pivot tables, correlation matrix and heatmap, scatter plots with regression lines, outcomes by vaccine/treatment availability

## Key findings

- The data is almost perfectly balanced: records per disease range from 3,893 (Tuberculosis) to 4,116 (Cholera), and disease-category shares from 8.91% to 9.30%.
- Average mortality changed from 5.044% (2023) to 5.050% (2024), a 0.13% change. This is too small to call a trend, and there are only two years.
- Every numeric variable is symmetric and roughly uniform across its range, so none is normally distributed.
- The strongest correlation between any two numeric variables is |r| = 0.009. Healthcare access, doctors, hospital beds, income and education show no measurable relationship with mortality or recovery.
- Mean mortality and recovery are nearly identical whether vaccines/treatment are available or not (mortality 5.044% vs 5.049%).

### A note on the data

The flat distributions, near-equal category counts and absence of correlations strongly suggest the dataset is **synthetic (randomly generated)**. In real health data, income, healthcare access and mortality would be clearly related. This project should therefore be read as a demonstration of data-cleaning and EDA method, not as a set of findings about real global health.

The missing values are also artificial: as part of the assignment, our instructor had us create null values in the table so that we could practise cleaning and imputation. The original public dataset does not contain these gaps, so the cleaning results in this notebook apply to the modified file, not to the original.

## Other limitations

- Only two years of data, so long-term trends can't be assessed.
- Mean/median/mode imputation slightly reduces variance (the amount missing is very small).
- Correlation does not imply causation.

## Repository contents

| File | Description |
|---|---|
| `ica_final_project_corrected.ipynb` | Full analysis notebook, with outputs |
| `Global_Health_Statistics_Report_Corrected.docx` | Written report |
| `README.md` | This file |

## Dataset

The dataset is **not included** in this repository. It comes from Kaggle: [Global Health Statistics](https://www.kaggle.com/datasets/malaiarasugraj/global-health-statistics) by malaiarasugraj.

**Note:** the original Kaggle file has no missing values. For our course assignment, null values were deliberately created in the table so that we could practise data cleaning and imputation. If you download the original file, the cleaning section will report 0 missing values, and the rest of the notebook runs the same.

To get the file with missing data: https://drive.google.com/file/d/1rZlLmHThffowHx1VsjrUgjkwOZLIhTu7/view?usp=sharing

**Important:** save the CSV as `Global Health Statistics.csv` and keep it in the **same folder as the notebook**, because the notebook loads it by that exact name.

## How to run

```bash
pip install pandas numpy scipy matplotlib seaborn jupyter
jupyter notebook ica_final_project_corrected.ipynb
```

1. Download the dataset from the Kaggle link above.
2. Save it as `Global Health Statistics.csv` in the **same folder** as the notebook.
3. Open the notebook and run all cells.

## Skills demonstrated

Python, pandas, NumPy, SciPy, Matplotlib, Seaborn, Jupyter, data cleaning, missing-value imputation, exploratory data analysis, statistical testing, data visualisation.
