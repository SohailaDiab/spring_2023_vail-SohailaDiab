# Regression Loss Functions

## Topics covered in today's module
* Mean Squared Error
* Mean Absolute Error
* Mean Squared Logarithm Error

## Main takeaways from doing today's assignment
- Loss functions are a measure of how well the model is performing on a specific dataset
- The loss functions that are used for regression include:
  - Mean Square Error - MSE (Quadratic loss/L2 Loss)
  - Mean Absolute Error - MAE (L1 Loss)
  - Mean Squared Logarithmic Error - MSLE 
  - Log cosh Loss
  - Quantile Loss
  - Huber Loss (Smooth MAE)

### Mean Square Error (MSE / L2)
$$MSE = \frac{\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}{n}$$

- MSE is measured as the average of squared difference between predictions and actual observations
- It's only concerned with the average magnitude of error irrespective of their direction
- It heavily penalizes larger errors, therefore it is not suitable for data with outliers
- The range is 0 to ∞

### Mean Absolute Error (MAE / L1)
$$MAE = \frac{\sum_{i=1}^{n}|y_i - \hat{y}_i|}{n}$$
- MAE is measured as the average of sum of absolute differences between predictions and actual observations
- Like MSE, this as well measures the magnitude of error without considering their direction
- Unlie MSE, MAE is more robust to outliers and doesn't heavily penalize larger errors since it takes the absolute and not the square
- The range is 0 to ∞
- *(If we consider directions also, that would be called Mean Bias Error (MBE), which is a sum of residuals/errors)*

### Mean Squared Logarithmic Error (MSLE)
$$MSLE = \frac{\sum_{i=1}^{n}(\log(y_i+1) - \log(\hat{y}_i+1))^2}{n}$$
- MSLE  takes the average $log$ of the actual and estimated outputs
- MSLE only cares about the relative difference between the true and the predicted value, or in other words, it only cares about the percentual difference between them
- This means that MSLE will treat small differences between small true and predicted values approximately the same as big differences between large true and predicted values
- MSLE can be used when we don't want large errors to be significantly more penalized than small ones, in those cases where the range of the target value is large

## Challenging, interesting, or exciting aspects of today's assignment
- It is interesting to see the vast amount of loss functions that can be used, each used depending on how our data looks like

## Additional resources used 
- [5 Regression Loss Functions All Machine Learners Should Know](https://heartbeat.comet.ml/5-regression-loss-functions-all-machine-learners-should-know-4fb140e9d4b0)
- [MAD vs RMSE vs MAE vs MSLE vs R²: When to use which?](https://datascience.stackexchange.com/questions/42760/mad-vs-rmse-vs-mae-vs-msle-vs-r%C2%B2-when-to-use-which)
- [What’s the Difference Between RMSE and RMSLE?](https://medium.com/analytics-vidhya/root-mean-square-log-error-rmse-vs-rmlse-935c6cc1802a)
