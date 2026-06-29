# IDX-Exchange
IDX Exchange Data Science Internship 2026
California Property Close Price Prediction Model

## Project Overview

This repository contains work completed during the internship involving analysis of CRMLS data. The objective is to explore the dataset and prepare it for machine learning models that predict residential property sale prices.

## Repository Structure

```
.
├── notebooks/
|   └── 01_exploration.ipynb
├── .gitignore
└── README.md
```


## Dataset

The analysis was performed using 12 months of CRMLS sold property data from June 2025 to May 2026. The notebook assumes the dataset has already been downloaded and is available locally.

## Week 1

- Established access to the project dataset
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

## Software

- Python
- pandas
- matplotlib
- Jupyter Lab/Jupyter Notebook

## Running the Project

1. Download the required CRMLS dataset (not included in this repository)
2. Update the file path in `notebooks/01_exploration.ipynb` if necessary
3. Run the notebook to reproduce the exploratory data analysis
