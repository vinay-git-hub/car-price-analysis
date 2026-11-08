# Car Price Analysis and Prediction

A beginner-level end-to-end data analysis and regression project using the UCI Automobile dataset. I used this project to practise data cleaning, exploratory analysis, feature transformations, preprocessing, regression modelling and model evaluation.

## Project question

**Can vehicle specifications help explain and predict automobile prices?**

## Dataset

- **Source:** UCI Machine Learning Repository – Automobile (Imports-85)
- **Records in raw file:** 205
- **Attributes:** 26, including the target column `price`
- **Records used for analysis:** 201 after removing the four records where `price` was missing
- **Target:** `price`

The notebook downloads the dataset directly from the UCI source, so a separate CSV file is not required to run it. An internet connection is needed for the data-loading cell.

Dataset source: https://archive.ics.uci.edu/ml/machine-learning-databases/autos/imports-85.data

## What I worked on

1. **Data overview and cleaning** – inspected the data, replaced `?` with missing values, converted numeric columns, and removed records without a target price.
2. **Exploratory data analysis** – reviewed price distributions, numerical correlations, categorical group summaries and an ANOVA comparison for drive-wheel groups.
3. **Feature transformations** – explored unit conversion and horsepower grouping. These were exploratory demonstrations; the final model retains the selected original features.
4. **Encoding and preprocessing** – demonstrated category encoding and built preprocessing pipelines for numeric and categorical predictors.
5. **Model development** – trained simple linear, degree-2 polynomial and multiple linear regression models.
6. **Cross-validation and Ridge tuning** – used five-fold cross-validation and `GridSearchCV` to compare models and choose a Ridge `alpha` from the tested values.
7. **Model evaluation** – compared a median baseline and regression models using test-set R², MAE and RMSE, and plotted actual versus predicted prices for Ridge.

## Selected model results from the saved notebook run

- Best Ridge `alpha` from the tested grid: **1**
- Ridge mean cross-validation R²: **0.843**
- Ridge held-out test R²: **0.900**
- Ridge held-out test MAE: **2,242.28**
- Ridge held-out test RMSE: **3,500.97**

In the same saved run, Multiple Linear Regression achieved a slightly higher held-out test R² (**0.915**). Ridge had the higher mean cross-validation R² and lower variation across folds. I therefore discuss both results rather than claiming Ridge was the best on every measure.

These are the results saved in this notebook run. Small differences may occur with different library versions or changes to the data and split.

## How to run the notebook

1. Download or clone this repository.
2. Install the packages listed in `requirements.txt`.
3. Start Jupyter Notebook or JupyterLab.
4. Open `automobile_price_analysis.ipynb`.
5. Run the cells from top to bottom. The data-loading cell requires internet access to retrieve the UCI dataset.

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

## Tools and libraries

Python, Jupyter Notebook, pandas, NumPy, Matplotlib, Seaborn, SciPy and scikit-learn.

## Notes

This is a learning and portfolio project, not a production pricing tool. The dataset is small, so the model results should be treated as an initial evaluation rather than proof that the model will perform equally well on a larger or more recent set of vehicles.
