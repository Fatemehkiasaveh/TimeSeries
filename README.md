
In this project we want to forcast population of different countries in 6 years in future. we have two approches to address this: 1.deploy machine learning model on all of our countries
2.deploy 159 model on each country then get a average of their lossess
 
# 1 Population Prediction for 159 Countries using Machine Learning

 We explore the performance of different regression models and hyperparameter tuning methods to achieve the best results. Below is a summary of our findings:

## Decision Tree Regressor

We initially deployed a DecisionTreeRegressor model with the following parameters:

- Minimum Samples Split: 5
- Minimum Samples Leaf: 1

### Results without Normalization
- Mean Squared Error (MSE): 9,656,226,571.49
- Mean Absolute Error (MAE): 43,237.67

### Results after Data Normalization
- MSE after Normalization: 9,480,184,645.97
- MAE after Normalization: 43,503.56

## XGBoost Regressor

Next, we explored the XGBoostRegressor model.
- n_estimators: 300
- max_depth: 7
- eta: 0.3
- subsample: 0.5
- colsample_bytree: 0.5

### Results 
- MSE after using XGBoost: [62202547285.09498]
- MAE after using XGBoost: [195396.7268907563]

### Results after Hyperparameter Tuning


## Random Forest Regressor

Lastly, we employed the RandomForestRegressor model and conducted hyperparameter tuning using GridSearchCV to fine-tune the model's parameters.

### Results after Hyperparameter Tuning
- MSE after using Gridsearch + Random Forest: [1886420108.0787127]
- MAE after using Gridsearch + Random Forest: [25008.86289499493]

Best Hyperparameter:  {'max_depth': 20, 'max_features': 'auto', 'min_samples_split': 2, 'n_estimators': 250}
Best 586978.664078 using {'max_depth': 20, 'max_features': 'auto', 'min_samples_split': 2, 'n_estimators': 250}
We hope that these results provide valuable insights into predicting population figures for countries and encourage further exploration and improvement of our models.

# 2 Population Prediction for 159 Countries using Machine Learning (each country one model)

  
