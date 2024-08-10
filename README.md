## Overview
This project explores portfolio optimisation using linear and quadratic programming methods in a comparative analysis that emphasises the limitations and benefits of both methods in their respective use cases. 

# Objectives
Linear Programming: Minimise the sum of absolute deviations from mean returns to reduce portfolio variance.
Quadratic Programming: Minimise portfolio variance using a covariance matrix to account for relationships between asset returns.
# Key Findings
Performance: The linear programming portfolio generally achieved higher returns but with greater variance compared to the quadratic portfolio.
Risk Management: The quadratic model demonstrated better risk control and stability due to its inherent consideration of asset correlations.
Constraints: Implementing diversification constraints was crucial for the linear model to prevent concentrated risk and improve comparability with the quadratic model.
Practical Implications
This study provides insights into the strengths and limitations of different optimisation techniques, highlighting the importance of choosing the appropriate model based on specific investment goals and risk tolerance. It also underscores the value of mathematical optimisation in real-world financial decision-making.

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
