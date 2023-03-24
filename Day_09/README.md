# Overfitting and Underfitting

## Topics covered in today's module
* Overfitting
* Underfitting
* Data preparation
* Reducing network capacity

## Main takeaways from doing today's assignment
### 1.) Overfitting
#### What is overfitting?
- It happens when the model fits the training data very well, but fails to generalize and predict well on new, unseen data (test data).
- This is because the model memorized the parameters and patterns that are only relevant to the data it is training on
- High accuracy on train data, low accuracy on test data
- This could happen because the model is too complex
#### How to reduce overfitting?
- Get more training data
- Reduce the network's capacity by removing layers or reducing the number of elements in the hidden layers
- Apply regularization, which comes down to adding a cost to the loss function for large weights
- Use Dropout layers, which will randomly remove certain features by setting them to zero

### 2.) Underfitting
#### What is underfitting?
- It happens when the model fails to capture the relationship between the input and output variables accurately
- Low accuracy on train data, low accuracy on test data
- This could happen because the model is too simple
#### How to reduce underfitting?
- Increase number of features in the dataset
- Increase the complexity of the model by either increasing the number of parameters of the model or the order of the model
- Train the model for more epochs

### 3.) Bias and Variance
![image](https://user-images.githubusercontent.com/70928356/227613076-c50d0f14-ea01-409d-8ee0-c1953a55b286.png)
![image](https://user-images.githubusercontent.com/70928356/227613472-b9869832-b05e-4d11-9e79-72d59f276dcd.png)

#### Bias
- Bias is the difference between the average prediction of our model and the correct value which we are trying to predict. 
- Model with high bias pays very little attention to the training data and oversimplifies the model. It always leads to high error on training and test data.
- Consistent answers, but consistently wrong answers.
- High Bias -> Underfitting

#### Variance
- Variance is the variability of model prediction for a given data point or a value which tells us spread of our data. 
- Model with high variance pays a lot of attention to training data and does not generalize on the data which it hasn’t seen before. As a result, such models perform very well on training data but has high error rates on test data.
- Will not get consistent predictions of future results
- High Variance -> Overfitting




## Challenging, interesting, or exciting aspects of today's assignment
- Working with text data and learning how to preprocess it

## Additional resources used 
- [Underfitting and Overfitting in Deep Learning | Medium](https://medium.com/mlearning-ai/underfitting-and-overfitting-in-deep-learning-687b1b7eb738)
- [The Complete Guide on Overfitting and Underfitting in Machine Learning | simplilearn](https://www.simplilearn.com/tutorials/machine-learning-tutorial/overfitting-and-underfitting)
- [Techniques for handling underfitting and overfitting in Machine Learning | Medium](https://towardsdatascience.com/techniques-for-handling-underfitting-and-overfitting-in-machine-learning-348daa2380b9)
- [Gentle Introduction to the Bias-Variance Trade-Off in Machine Learning | Machine Learning Mastery](https://machinelearningmastery.com/gentle-introduction-to-the-bias-variance-trade-off-in-machine-learning/)
- [Understanding the Bias-Variance Tradeoff | Medium](https://towardsdatascience.com/understanding-the-bias-variance-tradeoff-165e6942b229)
