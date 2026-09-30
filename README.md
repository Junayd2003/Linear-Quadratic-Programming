## Overview
This project compares linear and quadratic programming methods for portfolio optimisation. It was carried out as a funded summer research placement at the University of Sussex (June to August 2024). The repository contains the internal report (`JRA Dissertation.pdf`), the notebook (`Optimisation Code.ipynb`) and the cleaned data (`sp500_cleaned.xlsx`).

## Data
Daily returns for 352 S&P 500 stocks over 3,772 trading days (2000 to 2015). Stocks with mostly zero values were removed during cleaning.

## Models
Both models choose long-only weights that sum to 1 and minimise `α · risk − (1 − α) · expected return`, with `α = 0.5` unless stated.

- Linear programme: risk is the weighted sum of each stock's own mean absolute deviation from its mean return.
- Quadratic programme: risk is the portfolio variance `wᵀΣw`, using the sample covariance matrix.

Both are solved with CVXPY.

## Key Findings

1. Linear programme concentrates in one stock

   The linear model puts the whole portfolio into a single stock (`ED` on the full sample). Its objective is linear in the weights, so the optimum sits at a vertex of the feasible set, which here is one stock. The risk term also ignores how stocks move together, so it cannot reward diversification.

2. Quadratic programme diversifies

   The quadratic model uses the covariance matrix and spreads the portfolio across 9 stocks on the full sample.

3. Full-sample results (`α = 0.5`)

   | | Linear | Quadratic |
   |---|---|---|
   | Holdings | 1 stock | 9 stocks |
   | Mean daily return | 0.000451 | 0.001637 |
   | Variance of daily returns | 0.000137 | 0.000344 |

   The quadratic portfolio earned about 3.6 times the mean daily return of the linear portfolio, but with higher variance. The linear portfolio's variance was about 60% lower, because its objective favours a single low-volatility stock.

4. First trading year only (252 days, `α = 0.5`)

   | | Linear | Quadratic |
   |---|---|---|
   | Holdings | 1 stock | 6 stocks |
   | Mean daily return | 0.006261 | 0.006553 |
   | Variance of daily returns | 0.001344 | 0.000791 |

   Here the quadratic portfolio had both the higher mean return and about 41% lower variance.

5. Return only (`α = 0`)

   Both models pick the same single stock, the one with the highest mean return.

6. Computation time

   The linear model solves faster. The report gives averages of about 0.13 seconds for the linear model and 0.4 seconds for the quadratic model.

## Limitations
- Weights are fitted and evaluated on the same data, so all results are in-sample.
- The linear risk measure is a sum of individual stock deviations, not the deviation of the portfolio as a whole, so the two models are not compared on equal terms.
- The stock universe was cleaned by hand and contains only stocks with data across the period.

## Language & Packages

Python:
- numpy
- pandas
- matplotlib
- scipy
- cvxpy
- pulp
- gekko
- yfinance
