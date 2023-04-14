# Regularization

## Topics covered in today's module
* L1/L2 Regularization
* Dropout
* Overfitting
* Underfitting

## Main takeaways from doing today's assignment
### Regularization
- A technique used to **prevent overfitting**, which is when a model learns to fit the training data too well and fails to generalize to new, unseen data.
- Regularization forces weights to only take small values, which makes the distribution of weight values more "regular". 
- This is called "weight regularization", and it is done by adding to the loss function of the network a cost associated with having large weights.

#### L1 Regularization
$$\mathcal{L}_{\text{L1}}(\theta) = \lambda \sum_{i=1}^{m}|\theta_i|$$

$$J(\theta) = \frac{1}{2m}\sum_{i=1}^{m}(h_\theta(x^{(i)}) - y^{(i)})^2 + \frac{\lambda}{m}\sum_{i=1}^{m}|\theta_i|$$

$$cost = (\mathbf{y} - \mathbf{x}W)^2 + λ||W||$$

- Called Lasso Regression in regression problems.
- The cost added is proportional to the absolute value of the weights coefficients (i.e. to what is called the "L1 norm" of the weights).
- Encourages a sparse model (fewer and more sparse features) by pushing weights towards exactly zero.
- The penalty term in L1 regularization is the absolute sum of the weights, multiplied by a regularization hyperparameter $\lambda$.
- L1 regularization can be computationally expensive, especially when applied to large deep learning models with many parameters, but there are efficient algorithms such as coordinate descent and proximal gradient descent that can speed up the optimization process.
> Note: A sparse model has many parameters zeroed out by regularization


#### L2 Regularization
$$\mathcal{L}_{\text{L2}}(\theta) = \frac{\lambda}{2}\sum_{i=1}^{m}\theta_i^2$$

$$J(\theta) = \frac{1}{2m}\sum_{i=1}^{m}(h_\theta(x^{(i)}) - y^{(i)})^2 + \frac{\lambda}{2m}\sum_{i=1}^{m}\theta_i^2$$

$$cost = (\mathbf{y} - \mathbf{x}W)^2 + λ||W||_2^2$$

- Called Ridge Regression in regression problems.
- Called **weight decay** in the context of neural networks
- The cost added is proportional to the square of the value of the weights coefficients (i.e. to what is called the squared "L2 norm" of the weights)
- Penalizes the weights parameters without making them sparse since the penalty goes to zero for small weights.
- More common than L1.
- Has a nice Bayesian interpretation, where it corresponds to a Gaussian prior on the weights, assuming that the weights are normally distributed with mean zero and variance $\frac{1}{\lambda}$.
- Can also be used for weight initialization, where the model is initialized with small random weights and then regularized during training to prevent the weights from becoming too large.
- L2 regularization can be computationally efficient, as it adds a simple penalty term to the cost function that can be easily optimized using gradient descent or other optimization algorithms.


<h4> The choice of the regularization hyperparameter $\lambda$ is crucial in L1 and L2 regularization, as it determines the strength of the penalty term and the trade-off between model complexity and performance. A common practice is to use cross-validation to find the optimal value of $\lambda$ for a given dataset and model architecture. </h4>

### To Summarize L1 and L2:

|      | L1 Regularization | L2 Regularization |
| ---- | ---------------- | ---------------- |
| Effect on weights | Sparse weights with many zeros | Small but non-zero weights |
| Penalty term | Absolute sum of weights | Sum of squared weights |
| Feature selection | Yes | No |
| Computation efficiency | Less efficient for large models | More efficient for large models |
| Effective for | Noisy datasets with many irrelevant features | Small datasets or models with many parameters |
| Trade-off | Bias-variance trade-off | Bias-variance trade-off |
| Used for | Feature selection, reducing model complexity | Reducing model complexity, weight initialization |


## Challenging, interesting, or exciting aspects of today's assignment
<To be filled>

## Additional resources used 
- [L1 and L2 Regularization Methods | Towards Data Science](https://towardsdatascience.com/l1-and-l2-regularization-methods-ce25e7fc831c)
- [Regularization — Understanding L1 and L2 regularization for Deep Learning | Analytics Vidhya](https://medium.com/analytics-vidhya/regularization-understanding-l1-and-l2-regularization-for-deep-learning-a7b9e4a409bf)
