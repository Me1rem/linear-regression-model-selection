# Model Selection for Linear Regression: A Comparative Study

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-1.3+-150458.svg?logo=pandas)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/numpy-1.21+-013243.svg?logo=numpy)](https://numpy.org/)

## 📚 Project Overview

This project presents a comprehensive and systematic approach to model selection for multiple linear regression. The primary objective is to demonstrate and compare two fundamental feature selection techniques—**Backward Elimination using Akaike Information Criterion (AIC)** and **Forward Selection using Bayesian Information Criterion (BIC)** —to identify the optimal subset of predictors that best explains the target variable.

The project provides a clear, step-by-step implementation, from data exploration and model fitting to rigorous model diagnostics. It serves as a robust template for any predictive modeling task, emphasizing the importance of information criteria and parsimonious model building. The analysis concludes with a strong convergence of both selection methods, providing high confidence in the final model.

## 🎯 Project Objectives

- **Implement OLS Regression:** Build a linear regression model from scratch using the normal equations.
- **Perform Feature Selection:** Systematically apply and compare Backward (AIC) and Forward (BIC) selection algorithms.
- **Calculate Information Criteria:** Correctly compute log-likelihood, AIC, and BIC for model evaluation.
- **Validate the Model:** Diagnose the final model through residual analysis and statistical tests.
- **Visualize the Process:** Create clear visualizations of the selection paths and model diagnostics for interpretability.

##  Dataset and Files

### Dataset
The project uses a simulated dataset (`FE-GWP1_model_selection_1.csv`) containing 100 observations and 6 variables. This dataset is ideal for demonstrating feature selection as it includes one target variable and five potential predictors.

- **Target Variable:** `Y`
- **Predictors:** `X1`, `X2`, `X3`, `X4`, `X5`

### Project Files
- `CORRECTED_FE.ipynb`: The main Jupyter Notebook/Google Colab file containing all the Python code, analyses, visualizations, and explanations.
- `FE-GWP1_model_selection_1.csv`: The dataset used for the analysis. (Note: The path in the notebook may need to be updated.)

##  Technologies and Libraries

This project is built using Python and leverages the following key libraries:

- **`pandas`**: For data manipulation and analysis.
- **`numpy`**: For numerical operations and matrix calculations.
- **`matplotlib`**: For creating static, interactive, and publication-quality visualizations.
- **`scipy`**: For statistical tests (e.g., Shapiro-Wilk, Durbin-Watson) and probability plots.
- **`itertools`**: For iterating over combinations of predictors.
- **`warnings`**: To suppress unnecessary warnings for a cleaner output.

##  Methodology and Workflow

The analysis follows a structured workflow to ensure a robust and reproducible model selection process.

### 1. Data Exploration
- **Initial Analysis**: Display dataset dimensions, summary statistics (mean, standard deviation, quartiles), and a correlation matrix to understand the relationships between variables.
- **Variance Inflation Factor (VIF)**: Calculated to check for multicollinearity among predictors. VIF values close to 1.0 indicate very low multicollinearity, confirming the predictors are relatively independent.

### 2. Model Fitting and Information Criteria
A custom `fit_model()` function is implemented to:
- Fit an Ordinary Least Squares (OLS) model using the normal equations.
- Calculate essential statistics: **R²**, **Adjusted R²**, **Residual Sum of Squares (RSS)**, and **Root Mean Square Error (RMSE)** .
- **Compute AIC and BIC** from the log-likelihood of the model.

### 3. Backward Selection using AIC
The algorithm starts with the full model (all 5 predictors).
1.  It fits a model with all predictors.
2.  At each step, it iteratively removes one predictor and records the new AIC.
3.  If removing a predictor results in a lower AIC, it is permanently removed from the model.
4.  The process stops when no further removal improves AIC.

### 4. Forward Selection using BIC
The algorithm starts with a null model (intercept only).
1.  It fits a model with only the intercept.
2.  At each step, it iteratively adds one predictor and records the new BIC.
3.  If adding a predictor results in a lower BIC, it is permanently added to the model.
4.  The process stops when no further addition improves BIC.

### 5. Model Diagnostics
The final recommended model is rigorously evaluated using:
- **Residuals vs. Fitted Plot**: To check for homoscedasticity and linearity.
- **Q-Q Plot**: To assess the normality of residuals.
- **Scale-Location Plot**: To check for homoscedasticity.
- **Histogram of Residuals**: To visually inspect the distribution.
- **Shapiro-Wilk Test**: A formal statistical test for normality.
- **Durbin-Watson Statistic**: To test for autocorrelation in the residuals.

##  How to Run the Project

To reproduce this analysis, follow these steps:

### Prerequisites
- Python 3.8 or higher
- A Jupyter Notebook environment (e.g., Google Colab, Jupyter Lab, or VS Code)

### Installation

1.  **Clone the Repository (or download the files):**
    ```bash
    git clone <your-repository-url>
    cd <your-project-directory>
