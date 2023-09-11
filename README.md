
In this project, we want to forecast the population of different countries in 6 years in the future. We have two approaches to address this: 1. deploy a machine learning model on all of our countries
2. Deploy 159 model in each country then get an average of their loss.
 
# 1 Population Prediction for 159 Countries Using Machine Learning

 We explore the performance of different regression models and hyperparameter tuning methods to achieve the best results. Below is a summary of our findings:
 ## Data Preprocessing for Time Series Prediction
This code snippet is part of a data preprocessing pipeline designed for time series prediction. It processes a DataFrame df containing population data, where 'M49' is a country or region code, and 'pop_value' is the population value. The goal is to create input-output pairs for training a time series prediction model.

Parameters

window_size = 6: This parameter determines the size of the input sequence. It specifies how many previous population values should be considered to predict the next value.

Train-Test Split

A cutoff index is calculated, representing 90% of the data length. This will be used to split the data into training and testing sets.
The data is split into training and testing sets using the calculated cutoff index:
x_train and y_train contain the training input sequences and output values.
x_test and y_test contain the testing input sequences and output values.

## Decision Tree Regressor

We initially deployed a DecisionTreeRegressor model with the following parameters:

- Minimum Samples Split: 5
- Minimum Samples Leaf: 1

### Results without Normalization
- Mean Squared Error (MSE): 9,656,226,571.49
- Mean Absolute Error (MAE): 43,237.67

### Results after Data Normalization
- MSE after Normalization: 26,682,340,733.149246, 
- MAE after Normalization: 65398.45185185187

## XGBoost Regressor

Next, we explored the XGBoostRegressor model.
- n_estimators: 300
- max_depth: 7
- eta: 0.3
- subsample: 0.5
- colsample_bytree: 0.5

### Results 
- MSE after using XGBoost: [204246947593.85364]
- MAE after using XGBoost: [260860.72135416666]

### Results after Hyperparameter Tuning
Best hyperparameter:  {'colsample_bytree': 0.3, 'eta': 0.3, 'max_depth': 9, 'n_estimators': 200, 'subsample': 0.3}

- MSE after using Gridseach + RF: [56347464168.372246]
- MAE after using Gridseach + RF: [185885.08788515406]


## Random Forest Regressor

Lastly, we employed the RandomForestRegressor model and conducted hyperparameter tuning using GridSearchCV to fine-tune the model's parameters.

### Results after Hyperparameter Tuning
- MSE after using Gridsearch + Random Forest: [1886420108.0787127]
- MAE after using Gridsearch + Random Forest: [25008.86289499493]

Best Hyperparameter:  {'max_depth': 20, 'max_features': 'auto', 'min_samples_split': 2, 'n_estimators': 250}
Best 586978.664078 using {'max_depth': 20, 'max_features': 'auto', 'min_samples_split': 2, 'n_estimators': 250}
We hope that these results provide valuable insights into predicting population figures for countries and encourage further exploration and improvement of our models.

# 2 Population Prediction for 159 Countries using Machine Learning (each country one model)

  
