# Deep Learning and TensorFlow

## Topics covered in today's module
* Linear models in machine learning
* Introduction to TensorFlow
* Dataloaders
* Building a simple Neural Network

## Main takeaways from doing today's assignment
### - Sigmoid is sufficient if we have 2 classes (binary). We would need only 1 output neuron.

### - We need to scale pixel values from [0, 255] to be normalized to [0, 1].
- This is to speed up the learning process. It helps to avoid the possibility of exploding gradients because of the high range of the pixels [0, 255] and improve the convergence speed.
- When using the image as it is, without scaling, and passing through a Deep Neural Network, the computation of high numeric values may become more complex.

### - If we just directly fed the non-scaled pixel values [0, 255] to the neural networks, the learning process would be very long.
- These will produce huge activation values ( if you're using ReLU ). After the forward pass, you'll end up with a huge loss value and gradients.

### - **Sigmoid function:**
- It is used for logistic regression and basic neural network implementation
- It is used for **BINARY classification** problems
- Returns values between **0 and 1** or **1 and -1**
- Basically, in binary classification there is a threshold. For example if the probability is 0.6 and above, it will be class A, otherwise, it will be class B. We only need one neuron for this.
- If there are more layers in our Neural Network, the more data is compressed and lost per layer, and this amplifies and causes significant data loss overall.
- Equation:

$$ f(x) = sigmoid(x) =  \dfrac{1}{1+e^{-x}} $$

<p align="center">
<img src="https://user-images.githubusercontent.com/70928356/218247145-e7d2119e-086d-4738-8c87-aa14ec2c0692.png">
</p>

### - **SoftMax function:**
- It is used for logistic regression and basic neural network implementation
- Used for **MULTI-CLASS classification** problems and CNNs
- Takes vectors of real numbers as inputs, and normalizes them into a probability distribution
- Input can be any real number, positive or negative
- After Softmax Activation, each element will be in the range of **0 to 1**, and the **elements will add up to 1**

## Some jargon:
### Logits
Output values of a neuron getting fired up, and all those neurons map a certain input to a certain class. <br>
It's basically the output of the output layer / input of the last activation function.

Logits on their own are not bounded (as in don't have a range) and are less interpreteable (as to what the output value indicates).

So, we use Softmax function to normalize the logits to be bounded by [0, 1]

###  Probabilities
Output of the last activation function

### Ground truth
Target values

### Probabilities and ground truth
Inputs to the loss function (if the loss function is separate than the activation function)

### Logits and ground truth
Inputs to the loss function (if the loss function is combined with the activation function)

## Challenging, interesting, or exciting aspects of today's assignment
- The differences between Softmax and Sigmoid functions was confusing at first, but as I got to read more, it became clearer
- [The Pastry A.I. That Learned to Fight Cancer](https://www.newyorker.com/tech/annals-of-technology/the-pastry-ai-that-learned-to-fight-cancer) was a very interesting read

## Additional resources used 
- [Sigmoid vs Softmax activation function](https://medium.com/arteos-ai/the-differences-between-sigmoid-and-softmax-activation-function-12adee8cf322)
- [Why should we Normalize image pixel values or divide by 255? | Medium](https://medium.com/analytics-vidhya/a-tip-a-day-python-tip-8-why-should-we-normalize-image-pixel-values-or-divide-by-255-4608ac5cd26a#:~:text=The%20pixel%20values%20can%20range,range%20from%200%20to%201.)
- [How to Manually Scale Image Pixel Data for Deep Learning | ML Mastery](https://machinelearningmastery.com/how-to-manually-scale-image-pixel-data-for-deep-learning/#:~:text=Normalize%20Pixel%20Values,-For%20most%20image&text=Neural%20networks%20process%20inputs%20using,value%20between%200%20and%201.)
- [What is the significance of normalization of data before feeding it to a ML/DL model? | Stack Overflow](https://stackoverflow.com/questions/62111708/what-is-the-significance-of-normalization-of-data-before-feeding-it-to-a-ml-dl-m)
- [cmap=plt.cm.gray, cmap=mpl.cm.binary and cmap=plt.get_cmap("gray")](https://github.com/ageron/handson-ml/issues/575)
