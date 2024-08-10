## Overview
This project explores portfolio optimisation using linear and quadratic programming methods in a comparative analysis that emphasises the limitations and benefits of both methods in their respective use cases. 

# Objectives
Linear Programming: Minimise the sum of absolute deviations from mean returns to reduce portfolio variance.
Quadratic Programming: Minimise portfolio variance using a covariance matrix to account for relationships between asset returns.

Key Findings
1. Linear Programming Bias:
• The linear programming model tends to concentrate investments in a single stock due
to the imbalanced scaling of variables within the objective function. This issue arises
because the linear model struggles to adequately balance mean absolute deviations
and mean returns.
2. Quadratic Programming Superiority:
• Quadratic programming effectively accounts for the complexities of stock
correlations through the covariance matrix, resulting in a well-diversified portfolio.
This model demonstrates a 192% lower variance compared to the linear model,
showcasing its ability to manage risk better.
3. Computational Efficiency:
2
• While the linear model is computationally more efficient, taking on average 0.13
seconds to solve, it fails to achieve the same level of accuracy and robustness as the
quadratic model, which takes about 0.4 seconds. The quadratic model's longer
computation time is justified by its significantly better performance and accurate
representation of portfolio risk.


# Repository Contents
Data: Monte Carlo Simulation, 500 Stocks. 
Code: Python scripts implementing linear and quadratic programming models using cvxpy.
Visualisations: Time series plots and other visual analyses comparing the performance of the two models.
Documentation: Detailed explanations of the methods, findings, and implications for portfolio optimisation.

# Language & Packages

Python:
- yfinance
- scipy
- numpy
- matplotlib
- time
- gekko
- matplotlib.pyplot
- pulp
- scipy.optimize
- pandas
- cvxpy
