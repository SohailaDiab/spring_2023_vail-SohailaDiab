# Activation Functions

## Topics covered in today's module
* Introduction to Sigmoid, Tanh, ReLU
* Visualizing how ReLU affects the feature maps
* Vanishing and exploding gradients
* Dying ReLU problem
* Advanced activation functions: Swish, GeLU, SeLU

## Main takeaways from doing today's assignment
![download (2)](https://user-images.githubusercontent.com/70928356/221397657-5dbfa626-2043-4ff8-8a8e-ac0d4acb1269.gif)

- Linear functions assumes the change is constant across all variables, and cannot capture complex patterns
- Therefore, we use activation functions to give the model the ability to capture complex patterns

### Activation Function
- It is a non-linear function that is used to decide which neurons will be fired (activated) in the neural network
- It takes in the output signal from the previous cell and converts it into some form that can be taken as input to the next cell
- A neural network without an activation function is essentially just a linear regression model
- The choice of activation function in the **hidden layer** controls how well the network model learns the training dataset. All hidden layers typically use the same activation function
- The choice of activation function in the **output layer** defines the type of prediction the model can make

**Most commonly used for hidden layers:**
- Multilayer Perceptron 
  - `Rectified Linear Activation (ReLU)` 
- Convolutional Neural Network
  - `Rectified Linear Activation (ReLU)` 
- Recurrent Neural Network
  - `Hyperbolic Tangent (TanH)`
  - `Logistic (Sigmod)`

**Most commonly used for output layers:**
- Regression:
  - One node, `Linear activation`
- Classification:
  - Binary Classification
    - One node only, `Sigmoid activation`
  - MultiClass Classification
    - One node per class (n nodes), `Softmax activation`
  - MultiLabel Classification
    - One node per class (n nodes), `Sigmoid activation`    
    

## Challenging, interesting, or exciting aspects of today's assignment
<To be filled>

## Additional resources used 
- [Everything you need to know about “Activation Functions” in Deep learning models | Towards Data Science](https://towardsdatascience.com/everything-you-need-to-know-about-activation-functions-in-deep-learning-models-84ba9f82c253)
