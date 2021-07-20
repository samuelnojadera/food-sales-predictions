# food-sales-predictions

A project created for a Data Science bootcamp at Coding Dojo. The task is to predict sales using regression models.

## Data
Source:https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

Data Dictionary:
{IMAGE PLACEHOLDER} Data Dictionary

Before anything, the data was first cleaned in 'data_cleaning.ipynb'. Null and irregular values, as well as outliers were handled in this notebook.

'data_visualizations.ipynb' contains visualizations to get a grasp on the data and what sort of information it holds. 'data_analysis.ipynb' is a more indepth analysis focusing on correlations and relevant statistics.

## Preprocessing and Modelling

'proprocessing_and_models.ipynb' is where the machine learning happens. As the task is to predict sales, 3 different models were tested: Linear Regression, KNN Regression, and Random Forest Regression.

KNN Regression and Random Forest Regression involved some minor hyperparameter tuning, namely, 'n_neigbors' and 'n_estimators' respectively. Linear Regression used default values for the most part.

{IMAGE PLACEHOLDER} KNN Metrics, Random Forest Metrics, Linear Regression Metrics

## Findings
### Model Performance Comparison

The optimal 'N' parameters were first determined for KNN Regression and Random Forest Regression.
    1. n_neighbors: 30
    2. n_estimators: 40
    *These were determined in the 'preprocessing_and_models' notebook.
    
The RMSE for the optimal models:
    1. KNN Regression = 830.23
    2. Random Forest Regression = 844.27
    3. Linear Regression = 900.51
    
{IMAGE PLACEHOLDER} Optimal Models in Comparison
    
KNN Regression was the best performing model followed closely by Random Forest Regression. Normal Linear Regression performed poorly in comparison to the two.

### Model Prediction Comparison

{IMAGE PLACEHOLDER} Optimal Models Prediction Comparison

While the KNN Model RMSE score is better than that of the Random Forest Model, the Random Forest Model is better fits the best fit line (red) above. It performs better with larger values than both the Linear Regression and KNN Model.

### Feature Importance

Feature Importance was derived from:
    1. KNN Regression: sklearn's permutation_importance() function.
    2. Random Forest Regression: sklearn's built feature_importances_ attribute.
    3. Linear Regression: Acquired from absolute value of coefficients.
    *Source of these techinques is stated in the notebook.
    
{IMAGE PLACEHOLDER} Feature Importances

Common amongst the three models is Item_MRP as the standout feature. Other than that, Outlet_Type is significant for both Random Forest and Linear Regression models. Outlet_Location_Type, Outlet_Size, and Item_Type_Breakfast is also signficant to the Linear Regression Model. Item_Visibility and Item_Weight stand out for the Random Forest Model.




















