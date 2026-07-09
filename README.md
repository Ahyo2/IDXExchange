# IDX-Exchange
IDX Exchange Data Science Internship 2026
California Property Close Price Prediction Model

## Project Overview

This repository contains work completed during the internship involving analysis of CRMLS data. The objective is to explore the dataset and prepare it for machine learning models that predict residential property sale prices. The target variable is `ClosePrice`.

## Repository Structure

```
.
├── notebooks/
|   └── 01_exploration.ipynb
├── .gitignore
├── requirements.txt
└── README.md
```

## Dataset

The analysis was performed using 30 months of available CRMLS sold property data from June 2025 to May 2026.

## Week 1

- Created github
- Downloaded project data
- Reviewed the CRMLS metadata documentation
- Documented the purpose of key dataset columns

## Week 2

- Loaded twelve months of CRMLS data into pandas
- Filtered records to:
  - PropertyType = Residential
  - PropertySubType = SingleFamilyResidence
- Performed exploratory data analysis (EDA) on:
  - ClosePrice
  - LivingArea
  - BedroomsTotal
  - BathroomsTotalInteger
  - LotSizeArea

## Week 3

- Remove all columns with > 40% null values
- Changed categorical features with two options to boolean
- 

## Software

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikitlearn
- Jupyter Lab/Jupyter Notebook

## Running the Project

1. Download the required CRMLS dataset (not included in this repository)
2. Update the file path in `notebooks/01_exploration.ipynb` if necessary
3. Run the notebook to reproduce the exploratory data analysis