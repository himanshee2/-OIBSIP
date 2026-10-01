# Car Price Prediction with Machine Learning

Predicts the selling price of a used car based on brand, age, mileage, fuel type,
and transmission, using the CarDekho used-car dataset (301 listings, India).

## Tech Stack
Python, pandas, scikit-learn, matplotlib, seaborn, Jupyter Notebook

## Pipeline
1. Data cleaning — null checks, duplicate removal, standardized categorical values
2. Feature engineering — `Car_Age` from `Year`, `Brand` extracted from `Car_Name`
3. EDA — price distribution, price vs. fuel type, price vs. car age
4. One-hot encoding of categorical features
5. Correlation heatmap
6. Train/test split (80/20)
7. Trained 3 regression models: Linear Regression, Random Forest, Gradient Boosting
8. Evaluated with MAE, RMSE, R²
9. Feature importance chart for the best model

## Results

| Model              | MAE   | RMSE  | R²    |
|---------------------|-------|-------|-------|
| Linear Regression    | 1.329 | 2.458 | **0.766** |
| Gradient Boosting     | 1.262 | 3.236 | 0.594 |
| Random Forest          | 1.432 | 3.604 | 0.496 |

**Best model: Linear Regression** (R² = 0.766). `Present_Price` is the strongest
predictor of resale value, followed by `Car_Age` and `Kms_Driven`.

## How to Run

pip install pandas numpy matplotlib seaborn scikit-learn jupyter ipykernel
jupyter notebook car_price_prediction.ipynb

Then Run All cells.

## Author
Himanshee — B.Tech CSE, Amity University Noida
Oasis Infobyte AICTE Summer Internship Program