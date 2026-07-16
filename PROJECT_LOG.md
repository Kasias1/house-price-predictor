# House Price Predictor - Project Log

## Objective

Build an end-to-end machine learning pipeline capable of predicting house sale prices using the Ames Housing dataset.

---

## Dataset

- Dataset: Ames Housing
- Observations: 1,460
- Features: 81

---

## Data Cleaning

Completed:

- Handled missing values
- Filled categorical missing values representing the absence of a feature with "None"
- Filled GarageYrBlt with 0 for houses without garages
- Filled MasVnrArea with 0 where no masonry veneer existed
- Filled LotFrontage using neighborhood median
- Filled Electrical using mode

---

## Exploratory Data Analysis

Completed:

- SalePrice distribution
- Correlation analysis
- Scatter plots
- Box plots
- Neighborhood price analysis

Key Findings:

- SalePrice is positively skewed.
- OverallQual is the strongest predictor.
- Larger houses generally sell for higher prices.
- Neighborhood has a significant influence on price.

---

## Feature Engineering

Completed:

- Separated features and target
- One-hot encoded categorical variables
- Splitted data into training and testing sets (80/20)

---

## Models

### Linear Regression

MAE: 20,303

RMSE: 33,259

R²: 0.856

---

### Decision Tree

MAE: 26,825

RMSE: 42,276

R²: 0.767

---

### Random Forest

MAE: 17,779

RMSE: 29,210

R²: 0.889

Best Model: Random Forest

---

## Lessons Learned

- Importance of handling missing values correctly.
- How to perform exploratory data analysis.
- Why one-hot encoding is necessary.
- Why train/test splits prevent overfitting.
- How different machine learning algorithms perform on the same dataset.
- Why model evaluation should be based on objective metrics rather than assumptions.

---

## Future Improvements

- Hyperparameter tuning
- Cross-validation
- XGBoost
- Feature selection
