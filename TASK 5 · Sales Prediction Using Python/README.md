# Task 5 · Sales Prediction Using Python

A regression project that predicts product sales from advertising spend across
three media channels — **TV, Radio, and Newspaper**.

## Objective

Build and compare regression models to answer two questions:
1. How accurately can advertising spend predict sales?
2. Which advertising channel has the biggest impact on sales?

## Dataset

**`Advertising.csv`** — 200 markets, 4 columns:

| Column | Description |
|---|---|
| `tv` | TV advertising spend ($'000) |
| `radio` | Radio advertising spend ($'000) |
| `newspaper` | Newspaper advertising spend ($'000) |
| `sales` | Product sales ('000 units) — target variable |

This is the classic advertising dataset from *An Introduction to Statistical
Learning* (ISLR), widely mirrored on Kaggle. No missing values, no duplicates.

## Tech Stack

- Python 3
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- Jupyter Notebook

## Project Structure

```
Task5_Sales_Prediction/
├── Sales_Prediction.ipynb   # Main notebook (all analysis + models)
├── Advertising.csv          # Dataset
└── README.md                # This file
```

## How to Run

1. Clone or download this folder.
2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate        # venv\Scripts\activate on Windows
   pip install pandas numpy scikit-learn matplotlib seaborn ipykernel
   ```
3. Open `Sales_Prediction.ipynb` in Jupyter or VS Code and run all cells.

## Workflow

1. **Data loading & EDA** — null check, descriptive statistics, pairplot
2. **Visualization** — scatter plots of Sales vs. each channel, correlation heatmap
3. **Train/test split** — 80/20
4. **Baseline model** — Linear Regression
5. **Additional model** — Random Forest Regressor
6. **Evaluation** — MAE, RMSE, R² for both models
7. **Residual analysis** — residual plot for the best-performing model
8. **Interpretation** — standardized coefficients + feature importances to
   fairly compare channel impact (raw coefficients are not comparable across
   features on different scales)

## Results

| Model | MAE | RMSE | R² |
|---|---|---|---|
| Linear Regression | 1.46 | 1.78 | 0.899 |
| Random Forest | 0.61 | 0.74 | 0.983 |

**Random Forest outperforms Linear Regression** on all three metrics, suggesting
a mild non-linear/interaction effect between channels that the linear model
can't capture.

### Which channel matters most?

- **TV** has the strongest effect on sales — confirmed by both the standardized
  linear regression coefficient and the Random Forest feature importance.
- **Radio** has a clear secondary positive effect.
- **Newspaper** has almost no effect on sales once TV and Radio are accounted for.

> **Note:** raw (unstandardized) coefficients are misleading here because TV
> spend ranges up to ~$300k while Radio only ranges up to ~$50k. Standardizing
> the features before comparing coefficients is what reveals TV as the true
> top driver.

## Key Takeaway

If a marketing budget had to be reallocated, shifting spend away from
Newspaper and toward TV (and secondarily Radio) would be expected to have the
largest impact on sales, based on this dataset.

## Author
Himanshee — B.Tech CS, Amity University Noida
Oasis Infobyte AICTE Summer Internship Program