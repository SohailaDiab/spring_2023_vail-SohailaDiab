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

### Mean Square Error
$$MSE = \frac{\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}{n}$$

- MSE is measured as the average of squared difference between predictions and actual observations
- It's only concerned with the average magnitude of error irrespective of their direction
- It heavily penalizes larger errors, therefore it is not suitable for data with outliers

### Mean Absolute Error

### Mean Squared Logarithmic Error

## Challenging, interesting, or exciting aspects of today's assignment
<To be filled>

## Additional resources used 
- [5 Regression Loss Functions All Machine Learners Should Know](https://heartbeat.comet.ml/5-regression-loss-functions-all-machine-learners-should-know-4fb140e9d4b0)
