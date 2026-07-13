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
|   └── 02_preprocessing.ipynb
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

### Loading data
1. Loaded all CRMLS data using Pandas
2. Filtered records to:
  - PropertyType = Residential
  - PropertySubType = SingleFamilyResidence

### Exploratory Data Analysis (EDA)
1. Performed univariate EDA on:
    - `ClosePrice`
    - `LivingArea`
    - `BedroomsTotal`
    - `BathroomsTotalInteger`
    - `LotSizeArea`
    - `CountyOrParish`
2. Correlation Matrix of the following numerical features:
    - `ClosePrice`
    - `LivingArea`
    - `DaysOnMarket`
    - `YearBuilt`
    - `BuildingAreaTotal`
    - `LotSizeSquareFeet`
3. Stacked histogram of `ClosePrice` colored by `BathroomsTotalInteger`

### Deliverables
1. `01_exploration.ipynb`

## Week 3

### Preprocessing
1. Cleaned Dataset as follows:
    - Dropped duplicates
    - Removed impossible values and dropped nulls for `ClosePrice`
    - Converted impossible values to nan for the following columns
      - `Longitude`/`Latitude`, `LivingArea`, `ParkingTotal`, `LotSizeSquareFeet`, `YearBuilt`, `GarageSpaces`
    - Remove all columns with > 40% null values
    - Drop observations in states other than California
    - Drop columns with a single value
    - Changed Date columns to DateTime format
    - Dropped redundant, unhelpful, and leaky features
    - Converted columns with Y/N values to Boolean
    - Imputed missing values accordingly
      - `Flooring`, `MLSAreaMajor`, `BuyerOfficeAOR`, `City`, `Levels`, `HighSchoolDistrict`, `PostalCode`, `BuyerAgentAOR`, `ListAgentAOR` imputed with 'Unknown'
      - `AssociationFee`, `GarageSpaces`, `ParkingTotal` imputed with zero
      - `LivingArea`, `LotSizeSquareFeet`, `YearBuilt` imputed with median
      - `BedroomsTotal`, `BathroomsTotalInteger`, `Stories` imputed with mode
      - Dropped null values for `Latitude`/`Longitude`

2. Used `relativedelta` to split cleaned dataset into training and testing

### Deliverables:
1. `02_preprocessing.ipynb`
2. `df_cleaned.csv`

## Week 4

### General Preprocessing
1. Dropped more columns that are location based because `Latitude`/`Longitude` are the most specific
2. Split `Flooring` and `Levels` by comma to encode later

### After Training and Testing Split
3. Scale continuous and discrete columns using `StandardScaler`
   - fit_transform on training data and just transform testing
4. Encode `Flooring_list`, `Levels_list` and `HighSchoolDistrict`
   - `MultiLabelBinarizer` for `Flooring_list` and `Levels_list`
   - K-fold target encoding for `HighSchoolDistrict`

### Linear Regression
1. Used `sklearn.linear_model.LinearRegression()` to train two models
   - normal model on regular training dataset
   - log transformed `ClosePrice`
2. RMSE and R^2 metrics:
    - Regular RMSE: 586746.74, R^2: 0.6594
    - Log-transform RMSE: 739778.43, R^2: 0.4586
3. Residual plots for better visualization

### Deliverables
1. `O3_baseline_model.ipynb`

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