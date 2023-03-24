# Overfitting and Underfitting

## Topics covered in today's module
* Overfitting
* Underfitting
* Data preparation
* Reducing network capacity

## Main takeaways from doing today's assignment
### Overfitting
#### What is overfitting?
- It happens when the model fits the training data very well, but fails to generalize and predict well on new, unseen data (test data).
- This is because the model memorized the parameters and patterns that are only relevant to the data it is training on
- High accuracy on train data, low accuracy on test data
#### How to reduce overfitting?
- Get more training data
- Reduce the network's capacity by removing layers or reducing the number of elements in the hidden layers
- Apply regularization, which comes down to adding a cost to the loss function for large weights
- Use Dropout layers, which will randomly remove certain features by setting them to zero

### Underfitting
#### What is underfitting?
- It happens when the model fails to capture the relationship between the input and output variables accurately
- Low accuracy on train data, low accuracy on test data

#### How to reduce underfitting?
- 



## Challenging, interesting, or exciting aspects of today's assignment
- Working with text data and learning how to preprocess it

## Additional resources used 
- [Underfitting and Overfitting in Deep Learning | Medium](https://medium.com/mlearning-ai/underfitting-and-overfitting-in-deep-learning-687b1b7eb738)
