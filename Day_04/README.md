# Convolution Neural Network

## Topics covered in today's module
* Convolution neural network components
* Visualizing kernels
* Visualizing feature maps
* Pooling
* Dropout
* Batch norm

## Main takeaways from doing today's assignment

### Convolutional Neural Networks
- An artificial neural network that is popularly used for analyzing images. They can be used for other data analysis or classification problems too.
- It is an ANN that is able to detect patterns and make sense of them. This pattern detection makes CNN useful for image analysis.
- It consists of:
  1. A convolutional (CONV) layer
  2. An activation layer (usually ReLU)
  2. A pooling layer
  3. A fully connected layer

### What differentiates CNN from a standard Multilayer Perception (MLP)?
- CNN has hidden layers called **Convolutional Layers**. They can and usually do have other non-convolutional layers as well, but the basis of the CNNs is the convolutional layers.

### Convolutional layers
![image](https://user-images.githubusercontent.com/70928356/218688932-3f579082-612b-4873-9ef9-4c1992951be4.png)
- These are the layers that are able to detect patterns.
- With each conv layer, we need to specify the number of filters it should have. Filters are what help to detect the patterns.
- Patterns can be something like edges in the pattern, so the filter could be an "edge detector". Other patterns can be corners, circles, squares, etc.<br>
These simple and somewhat geometric filters are what we'd see at the start of our network.<br>
The deeper the network, the more sophisticated the filters become. So in later layers, rather than edges and simple shapes, the filters may detect things like, eyes, hands, leaves, etc. In even deeper layers, filters may detect things like a person, cats, dogs, trees, etc.

<br>

- This layer performs a dot product between 2 matrices, where one matric is the set of learnable parameters known as a `kernel`, and the other matrix is the restricted portion of the receptive field.
- Kernel is usually smaller than the input data and is square-shaped (eg. 3x3, 5x5, 7x7, 9x9).
- The kernel slides across the input data (image) from left to right, and top to bottom. It calculates the dot product, and sums resulting in a single value. These single values produce two-dimensional representation of the image known as an `activation map`.
- How much the kernel slides (steps it takes left to right and top to bottom) is called a `stride`.

<br>

- Calculating the size of the output (activation map size):

![image](https://user-images.githubusercontent.com/70928356/218697572-fe3d9faf-9cef-41a8-9d8c-ae7f94c86dfd.png)

    - W: input volume size, 
    - F: the receptive field size of the Conv Layer neurons, 
    - S: the stride with which they are applied, 
    - P: the amount of zero padding used on the border, 
    - K: the depth of conv layer (multiply it by the whole formula to get the volume).
    
#### Properties of conv layer:
- Sparse interaction 
- Parameter sharing
- Equivariant representation

(more info in 1st link of additional resources)

### Activation Layer
*Note: Activation layer and activation function are the same thing and used interchangeably.*

- Once the feature maps are extracted, we then pass them through an activation function.
- The activation function is usually a Rectified Linear Unit (ReLU) layer.
  - ReLU is a non-linear function
  - No parameters or weights are given to learn from images
  - It sets all the negative pixel value to 0 and introduces non-linearity to the network
  - The resulted output is now a `rectified feature map`
  - Activation functions are used in NNs to learn more complex features
  
![image](https://user-images.githubusercontent.com/70928356/218702968-a2010572-8dcc-4899-92fb-38c23cf139fc.png)

### Pooling Layer
- The resulting feature map from the output layer then goes through the pooling layer.
- This is used to shrink the image (down-sampling operation) and reduces the dimensionality of the feature map.
- This is useful because it decreases the required amount of computational complexity and weights.
- It also helps to identify information from the image like edges, corners, and curves.
![image](https://user-images.githubusercontent.com/70928356/218714942-49572214-04ff-4c00-83f1-ae4662ce7796.png)

### Fully-Connected Layer
![image](https://user-images.githubusercontent.com/70928356/218715590-b1c12222-6095-4358-bc12-bdab8023c142.png)

- We then flatten the feature map matrix and input them to a fully-connected layer.
- This is the usual fully-connected feed forward neural network.
- The fully-connected layer then sums the features from all the combination of the features of the previous layer and gets it ready for classification.
- This helps to map the representation between the input and the output.

![image](https://user-images.githubusercontent.com/70928356/218718763-c6e736b9-9384-4421-8fb6-1fa984737ce4.png)

### Overfitting
- Happens when the model memorizes the data instead of learning it
- This could be due to the number of training samples not being sufficient enough for the model to learn properly
- We detect overfitting by seeing if the training error is much lower than the testing error

**Techniques for mitigating overfitting:**
#### 1. Pooling layer with padding
- Pooling layer reduces the spatial dimensions of the input. This can help migitate overfitting since it reduces the number of features, and overfitting occurs when the dataset size is not enough to learn the features
- Padding might be required to process inputs with a shape that does not perfectly fit kernel size and stride of the pooling layer. Also padding might be used for inputs which fit kernels to ensure the kernels equally cover the edge features of the input as well.

#### 2. Dropout
- Dropout is a regularization method that approximates training a large number of neural networks with different architectures in parallel.
- Dropout momentarily (in a batch of input data) switches off some neurons in a layer so that they do not contribute any information or learn any information during those updates, and the onus falls on other active neurons to learn harder and reduce the error.
- This has the effect of making the training process noisy, forcing nodes within a layer to probabilistically take on more or less responsibility for the inputs.

![download](https://user-images.githubusercontent.com/70928356/219655592-f06b5976-625a-424c-a2e5-f6bc21286bf3.gif)

#### 3. Batch Normalization
- We normalize the outputs of the activation function of a certain layer to avoid having its weights much larger than the other layers and to avoid exploding gradients

## Challenging, interesting, or exciting aspects of today's assignment
- How the CNNs are able to detect patterns by applying filters to an image.
- I took a Signal Processing course, where I studied convolution and understood that it finds the overlap of 2 signals. I did not understand why we needed it or where it is applied. It was very interesting to see how it actually works and that is it very important.

## Additional resources used 
- [Convolutional Neural Networks, Explained](https://towardsdatascience.com/convolutional-neural-networks-explained-9cc5188c4939)
- [CS231 Convolutional Neural Networks for Visual Recognition](https://cs231n.github.io/convolutional-networks/#conv)
- [Dropout for regularizing deep neural networks](https://machinelearningmastery.com/dropout-for-regularizing-deep-neural-networks/)
- [Batch normalization for training of deep neural networks](https://machinelearningmastery.com/batch-normalization-for-training-of-deep-neural-networks/)
- [Batch Normalization (“batch norm”) explained | DeepLizard YouTube video](https://www.youtube.com/watch?v=dXB-KQYkzNU)
