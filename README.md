# Data Science Project: Regression Analysis for Pricing Prediction

**Author:** Fong Chin Wai (Vivi) — Student ID: mc653748
**Course:** CISC7204 Data Science Practice, University of Macau (Assignment 1, 2026)

This repository contains the complete regression analysis pipeline from Assignment 1
of CISC7204. It predicts the market price of three product categories — **used cars**,
**laptops**, and **houses** — from their features using supervised machine learning.

**Live website:** [https://fongchinwai-vivi.github.io/data-science-project/](https://fongchinwai-vivi.github.io/data-science-project/) — browse this project as a GitHub Pages site (figure gallery + notebook download links).

---

## 1. Research Question

How accurately can the market price of a product or property be predicted from its
features using linear regression models?

The project works through three concrete pricing problems:

1. **Automobile price prediction** — predict the price of a 1985-era automobile from
   attributes such as engine size, horsepower, and curb weight.
2. **Laptop price prediction** — predict laptop prices from technical specifications.
3. **House price prediction** — predict the sale price of houses in King County
   (Seattle area) from square footage, number of bedrooms, bathrooms, floors, and
   location-related features.

## 2. Dataset Source and Usage Permissions

All datasets are publicly available and used for educational purposes:

| File | Description | Source | Permission |
|---|---|---|---|
| `data/auto.csv`, `data/module_5_auto.csv` | 1985 automobile data (205 rows, 26 columns) | UCI Machine Learning Repository (`imports-85.data`) | Public domain / free for research and education |
| `data/laptops.csv` | Laptop specifications and prices | IBM Skills Network course dataset (DA0101EN) | Publicly distributed for learners |
| `data/usedcars.csv` | Used car listings | IBM Skills Network course dataset (DA0101EN) | Publicly distributed for learners |
| `data/clean_df.csv` | Cleaned automobile data (output of Module 2 wrangling) | Derived from `auto.csv` | Derived from public data |
| `data/housing.csv` | King County house sales, May 2014 – May 2015 (21,613 rows) | Kaggle — [House Sales in King County](https://www.kaggle.com/harlfoxem/housesalesprediction), slightly modified for the course | Publicly available (Kaggle) |

No passwords, API keys, personal data, or restricted datasets are included in this
repository.

## 3. Methods and Tools

**Tools:** Python, pandas, numpy, matplotlib, seaborn, scikit-learn, Jupyter Notebook.

**Methods:**
- Data acquisition and loading (`pd.read_csv`, header and data-type inspection)
- Data wrangling: missing-value detection, replacing `?` with `NaN`, mean imputation,
  one-hot encoding, feature binning
- Exploratory data analysis: distributions, histograms, scatter plots, correlation analysis
- Modeling: simple linear regression, multiple linear regression, polynomial features
- Model evaluation and refinement: train/test split, k-fold cross-validation,
  Ridge regression, `GridSearchCV` hyperparameter tuning
- Metrics: R² (coefficient of determination) and MSE (mean squared error)

The notebooks mirror the six course modules (Module 01 → Module 06) and can be run
in order.

## 4. Key Findings and Limitation

**Key findings**
- For automobiles, **engine size** and **horsepower** are the strongest predictors of
  price; a scatter plot shows a clear positive linear relationship between engine size
  and price (`figures/m03_scatter_engine_size_vs_price.png`).
- Missing values (`?`) must be handled before modeling; mean imputation preserves the
  overall distribution while allowing all rows to be used.
- A plain polynomial regression on horsepower overfits the training data; after
  cross-validation and **Ridge regression with grid-searched alpha**, the test-set
  R² improves substantially and the model generalizes better
  (`figures/m04_model_comparison_r2_mse.png`, `figures/m05_gridsearch_alpha_tuning.png`).
- For housing, **square footage / living area** correlates most strongly with sale
  price (`figures/m06_price_vs_sqft_correlations.png`), confirming that size dominates
  King County housing prices.

**Limitation**
- The automobile dataset dates from 1985, so the fitted price model may not generalize
  to the current used-car market; conclusions should be treated as a demonstration of
  the modeling workflow rather than a market-ready pricing tool.

## 5. Repository Structure

```
data-science-project/
├── README.md
├── requirements.txt
├── notebooks/            # Assignment 1 notebooks (Module 01–06, one per stage)
│   ├── A1_Module01_Lab01_DataAcquisition.ipynb
│   ├── A1_Module02_Lab01_Wrangling.ipynb
│   ├── A1_Module03_Lab01_EDA.ipynb
│   ├── A1_Module04_Lab01_LinearRegression.ipynb
│   ├── A1_Module05_Lab01_CrossValidation_Ridge.ipynb
│   └── A1_Module06_FinalProj_HousePrice.ipynb
├── data/                 # Datasets (see table above)
│   ├── auto.csv
│   ├── laptops.csv
│   ├── clean_df.csv
│   ├── usedcars.csv
│   ├── module_5_auto.csv
│   └── housing.csv
└── figures/              # Key visualizations
    ├── m02_horsepower_binning_histogram.png
    ├── m02_missing_values_filled_with_mean.png
    ├── m03_scatter_engine_size_vs_price.png
    ├── m04_model_comparison_r2_mse.png
    ├── m05_gridsearch_alpha_tuning.png
    └── m06_price_vs_sqft_correlations.png
```

## 6. How to Reproduce the Analysis

1. Clone or download this repository.
2. (Recommended) Create a virtual environment:
   ```bash
   python -m venv venv
   ```
   Activate it (`venv\Scripts\activate` on Windows).
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
5. Open the notebooks in `notebooks/` **in order** (Module 01 → Module 06) and run
   all cells. Each notebook reads its dataset from the `data/` folder, so no extra
   download is needed.

Expected runtime: a few minutes per notebook on a standard laptop.

---

*Course: CISC7204 Data Science Practice — Assignment 1. Built for Practice 9
(Build Your Data Science Portfolio).*

