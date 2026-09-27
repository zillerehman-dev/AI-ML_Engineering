# Linear Regression — Complete Machine Learning Project

Predicting flight arrival delay from operational and passenger data.

This notebook is part of an AI/ML Engineering learning series. It is built to teach Linear
Regression properly: the mathematics behind it, the assumptions it relies on, and the complete
professional workflow used to take a raw dataset to a validated, saved, production-aware model.
The goal is not a single high R² score. The goal is to practice the reasoning an ML engineer
applies at every step, so the same workflow can be reproduced on a different regression dataset
independently.

## What this notebook covers

- Choosing a target variable deliberately, including why the dataset's most obvious column is
  *not* used
- A full data quality audit: missing values, duplicates, data types, outliers, and what to do
  (and not do) about each
- Exploratory data analysis built around specific questions, not decorative charts
- Linear Regression theory from first principles: simple and multiple regression, residuals,
  the cost function, Ordinary Least Squares, gradient descent (and why scikit-learn does not use
  it), and how to read coefficients and the intercept correctly
- The six classical assumptions of Linear Regression, each explained, checked against the data,
  and tied to whether it affects prediction, inference, or both
- A leak-proof preprocessing pipeline built with `ColumnTransformer` and `Pipeline`
- A baseline model, used as the yardstick for every model that follows
- Full evaluation: MAE, MSE, RMSE, R², and Adjusted R², each explained and interpreted, not just
  computed
- Residual analysis, heteroscedasticity testing (Breusch-Pagan), and residual normality testing
  (Shapiro-Wilk)
- Multicollinearity analysis with the Variance Inflation Factor (VIF)
- Influential observation analysis with Cook's Distance
- A feature scaling experiment showing scaling has no effect on plain OLS predictions, and why
  that changes for regularized models
- Ridge, Lasso, and Elastic Net regression: theory, cross-validated hyperparameter tuning with
  `GridSearchCV`, and a fair comparison against plain Linear Regression
- Error analysis on individual predictions, and a learning curve to check for high bias or high
  variance
- Coefficient interpretation, including one-hot encoded categorical coefficients and the
  distinction between a coefficient and a causal effect
- Final model selection based on stated criteria, followed by a single, honest evaluation on the
  untouched test set
- Saving and reloading the full preprocessing-plus-model pipeline with `joblib`, and using it to
  make a new prediction
- Production considerations: input validation, versioning, monitoring, data and concept drift,
  and retraining
- Linear Regression's limitations, its relationship to other regression algorithms, common
  beginner mistakes, and a concise mathematical reference
- A self-assessment section of interview-style questions, left unanswered on purpose
- Ten independent practical challenges, left unsolved on purpose

## Dataset

The notebook uses an airline passenger satisfaction survey (`data.csv`, roughly 130,000 rows).
The dataset's most prominent column, `satisfaction`, is a binary label and is not suitable for
Linear Regression, so it is set aside and the reasoning for that decision is explained in detail
in the notebook. The target used instead is `Arrival Delay in Minutes`, a continuous measurement
with a genuine, real-world regression problem behind it: estimating how late a flight will land
using information available at or shortly after departure.

`data.csv` should sit in the same folder as the notebook. The notebook loads it with a relative
path and does not require any other setup.

## Requirements

- Python 3.10+
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- statsmodels
- scikit-learn
- joblib

Install everything with:

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn joblib
```

## Running the notebook

1. Place `data.csv` in the same directory as the notebook file.
2. Open `Linear_Regression_Complete_ML_Project.ipynb` in Jupyter Notebook, JupyterLab, or VS
   Code.
3. Run all cells from top to bottom. Every random process in the notebook is seeded
   (`random_state = 42`), so re-running it reproduces the same splits, tuning results, and
   metrics shown in the notebook.
4. Running the notebook end to end also saves a trained model file,
   `linear_regression_arrival_delay_model.joblib`, to the working directory.

## Repository structure

```text
.
├── Linear_Regression_Complete_ML_Project.ipynb   # The main notebook
├── data.csv                                       # Dataset used by the notebook
└── README.md
```

## Notes on the results

All numbers in the notebook come from actually running the workflow on this dataset, not from
invented figures. The final Linear Regression model reaches an R² of roughly 0.94 on the held-out
test set, driven almost entirely by departure delay as a predictor. The notebook is explicit about
where the model's assumptions are violated (residual heteroscedasticity and non-normality are
both present and confirmed with formal tests) and what that does and does not mean for the
model's usefulness, rather than treating a high R² as proof that everything is fine.

## License

Add a license of your choice here before publishing (for example, MIT), and update this section
accordingly.
