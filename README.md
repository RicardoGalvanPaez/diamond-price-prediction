# Diamond Price Prediction

Regression model to predict diamond prices based on physical and qualitative 
characteristics, using Linear Regression and polynomial feature engineering.

## Problem Statement

Diamond pricing is influenced by multiple interacting features — carat, cut, color, 
clarity, and dimensions. This project builds and compares regression pipelines to 
accurately predict market price from these characteristics.

## Dataset

- **Source:** ggplot2 R package / public data repositories
- **Features:**
  - `carat` — Diamond weight in carats
  - `cut` — Cut quality (Fair, Good, Very Good, Premium, Ideal)
  - `color` — Color grade from D (best) to J (worst)
  - `clarity` — Clarity grade (I1 to IF)
  - `depth`, `table`, `x`, `y`, `z` — Physical dimensions
- **Target:** `price` (USD)

## Tech Stack

- Python 3.9
- Pandas, NumPy
- Scikit-learn (LinearRegression, PolynomialFeatures, OrdinalEncoder, 
  OneHotEncoder, MinMaxScaler, RobustScaler, Pipeline)
- Matplotlib, Seaborn
- Google Colab

## Methodology

Four progressively improved pipelines were built and compared:

| Model | RMSE | R² |
|---|---|---|
| Baseline (carat only) | $1,532 | 0.846 |
| Ordinal Encoding + Robust Scaler | $1,217 | 0.903 |
| One-Hot Encoding + MinMax Scaler | $1,143 | 0.914 |
| **Polynomial Features (Degree 2)** | **$749** | **0.963** |

## Key Results

The best model achieved an **R² of 0.963** and an RMSE of **$749 USD**, meaning 
it explains 96.3% of the variance in diamond prices. Polynomial feature engineering 
provided the most significant performance gain — reducing error by 51% compared 
to the baseline.

## What I Learned

- Impact of encoding strategy (Ordinal vs One-Hot) on regression performance
- How polynomial features capture non-linear relationships between carat and price
- Importance of scaling strategy selection based on data distribution
- Building and comparing multiple ML pipelines systematically
