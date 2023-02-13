# Artificial Neural Networks

## Topics covered in today's module
* Introduction to Neural Networks
* Hyperparameters
* Forward Pass
* Backpropagation
* Computing accuracy

## Main takeaways from doing today's assignment
- Activation functions are a crucial part of a neural network that help model non-linearity of input data. These activation functions are represented by the neurons defined in each layer of the network.
- Properties of activation functions:
  - Non-linear
  - Injective: $f(x1) = f(x2)  ->  x1=x3$
  - Differentiable and continuous
    - Useful for updating the model weights after each training pass to make the model more accurate using an approach called "backpropogation based on gradient descent"
- $y=2x$ is NOT an activation function since it is linear
- $y=sin(x)$ is not a good activation function since 2 inputs can give the same output. They're also "spiky", so differentiating it in order to adjust the weights of the nodes is challenging. 
- It is preferable for activation functions to be smooth.

- We never use softmax and identity functions in the hidden layers. We use sigmoid, tanh, ReLU, variants of ReLU, swish and hard swish functions only in the hidden layers.
- Very deep neural networks using sigmoid activation functions could not easily be trained, due to a problem called the "vanishing gradient problem". The **Rectified Linear (RELU)** activation function overcomes this problem, allowing models to learn faster and perform better.

## Challenging, interesting, or exciting aspects of today's assignment
- Understanding the math behind backpropagation

## Additional resources used 
- [Weight Initialization for Deep Learning Neural Networks | ML Mastery](https://machinelearningmastery.com/weight-initialization-for-deep-learning-neural-networks/#:~:text=Weight%20initialization%20is%20used%20to,the%20models%20on%20a%20dataset.)
- [How to initialize deep neural networks? Xavier and Kaiming initialization](https://pouannes.github.io/blog/initialization/)
- [Interpreting logits: Sigmoid vs Softmax - Note: GREAT Explanation!!](https://web.stanford.edu/~nanbhas/blog/sigmoid-softmax/)
- [Why use softmax only in the output layer and not in hidden layers?](https://stackoverflow.com/questions/37588632/why-use-softmax-only-in-the-output-layer-and-not-in-hidden-layers)
- [Introduction to the Rectified Linear Unit (ReLU) and Limitations of Sigmoid and Tanh Activation Functions](https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/)
- [Step-by-step back propagation](https://hmkcode.com/ai/backpropagation-step-by-step/)
- [Back propagation visualization](http://experiments.mostafa.io/public/ffbpann/)
- (Difference Between Backpropagation and Stochastic Gradient Descent)[https://machinelearningmastery.com/difference-between-backpropagation-and-stochastic-gradient-descent/]
