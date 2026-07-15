# House Price Predictor

## Project Overview

This project explores the Ames Housing dataset and develops a machine learning model for predicting house sale prices.

The project follows a complete machine learning workflow:

- Data loading and inspection
- Missing-value analysis
- Data cleaning
- Exploratory Data Analysis
- Feature Engineering
- One-Hot Encoding
- Train/Test Split
- Linear Regression
- Model Evaluation

## Dataset

The dataset contains 1,460 houses and 81 columns describing features such as:

- Living area
- Overall construction quality
- Garage capacity
- Basement size
- Neighborhood
- Year built
- Sale price

The target variable is `SalePrice`.

## Project Structure

House-price-predictor/
│
├── Data/
│ ├── raw/
│ └── processed/
├── images/
├── House_Price_EDA.ipynb
├── README.md
├── requirements.txt
└── .gitignore

## Data Cleaning

Missing values were handled according to their meaning rather than applying one method to every column.

Examples:

- Categorical values representing the absence of a feature were filled with `"None"`.
- `GarageYrBlt`was filled with 0 for houses without a garage, allowing the model to distinguish between houses with and without garage structures.
- `MasVnrArea` was filled with 0 for houses without masonry veneer, since a missing value represented the absence of the feature rather than missing information.
- `LotFrontage` was imputed using the median LotFrontage value within each neighborhood.This approach preserves neighborhood-specific characteristics and reduces the influence of extreme values compared to using the overall mean.
- The single missing `Electrical` value was filled using the mode.

## Exploratory Data Analysis

### Sale Price Distribution

`SalePrice` is positively skewed. Most houses are concentrated in the lower and middle price ranges, while a smaller number of expensive houses create a long right tail.

![Sale price distribution](images/saleprice_distribution.png)

### GrLivArea and SalePrice

There is a clear positive relationship between above-ground living area and sale price. Larger houses generally sell for more, although a few outliers are present.

![GrLivArea versus SalePrice](images/grlivarea_vs_saleprice.png)

### Overall Quality and SalePrice

`OverallQual` has the strongest positive correlation with `SalePrice`. Houses with higher overall quality ratings generally sell for higher prices.

![Overall quality versus SalePrice](images/overallqual_vs_saleprice.png)

### Sale Price Outliers

The box plot shows several high-priced outliers. These observations were not removed automatically because they may represent genuine luxury properties.

![SalePrice boxplot](images/saleprice_boxplot.png)

### Neighborhood Differences

Average sale prices vary considerably across neighborhoods. `NoRidge` has the highest average sale price, while `MeadowV` has the lowest.

![Average sale price by neighborhood](images/neighborhood_prices.png)

## Key Findings

- `OverallQual` has the strongest positive correlation with `SalePrice`.
- Larger above-ground living areas are generally associated with higher prices.
- Garage capacity, basement size, and first-floor area are also important numerical features.
- Newer and recently remodeled houses tend to sell for more.
- Neighborhood appears to be an important categorical predictor.
- `SalePrice` contains several valid high-value outliers.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Progress

- [x] Data loading
- [x] Data cleaning
- [x] Exploratory Data Analysis
- [x] Feature engineering
- [x] Linear Regression model
- [x] Model evaluation
- [ ] Model comparison
- [ ] Model optimization

## Linear Regression Results

The first machine learning model trained was a Linear Regression model.

Performance on the test dataset:

| Metric   | Value   |
| -------- | ------- |
| MAE      | $20,303 |
| RMSE     | $33,259 |
| R² Score | 0.856   |

The model explains approximately **85.6%** of the variation in house sale prices and serves as a strong baseline for future models.

## Next Steps

The next stage is to prepare the dataset for machine learning by:

- Train a Decision Tree Regressor.
- Train a Random Forest Regressor.
- Compare multiple regression models.
- Tune model hyperparameters.
- Select the best-performing model.
