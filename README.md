# Used Car Price Prediction

Predicting the listed price of a used car from its brand, model year, horsepower and fuel type, and comparing three regression models.

Team project for DTSC 2301 at UNC Charlotte, by Joshua Inacio and Ethan Eckenrode.

## Data
A web-scraped set of used-car listings (24,988 records, model years 2001-2026, 68 columns) collected by a classmate, Eric Toan. It is not included in this repository because it is not mine to republish. After cleaning (standardizing columns, fixing data types, dropping bad rows) 23,493 listings remained.

## Method
- Main features: brand, model year, horsepower, fuel type, with a preprocessing pipeline (imputation, one-hot encoding, scaling).
- Compared Linear Regression, Random Forest (300 trees) and Gradient Boosting (400 trees) on R², MAE and RMSE.
- Side questions on how price moves with horsepower, model year, brand and fuel type, plus feature importances.

## Results
| Model | R² | MAE | RMSE |
|---|---|---|---|
| **Random Forest** | **0.910** | **$2,682** | $5,471 |
| Gradient Boosting | 0.877 | $3,371 | $6,395 |
| Linear Regression | 0.689 | $6,077 | $10,176 |

The Random Forest predicts price within about $2,700 on average. In both tree models horsepower (about 0.42-0.46) and model year (about 0.29) are the strongest features.

## Limits
Listed prices are asking prices, not sale prices, and the data comes from one scrape.

## Run it
You need your own copy of the listings as `data/all_cars.csv`.
```bash
pip install -r requirements.txt
jupyter notebook used_car_price_prediction.ipynb
```
A short write-up is in [`docs/technical-report.pdf`](docs/technical-report.pdf).
