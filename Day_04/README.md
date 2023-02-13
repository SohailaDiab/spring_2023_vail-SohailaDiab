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

### What differentiates CNN from a standard Multilayer Perception (MLP)?
- CNN has hidden layers called **Convolutional Layers**. They can and usually do have other non-convolutional layers as well, but the basis of the CNNs is the convolutional layers.

### What do the convolutional layers do?
- These are the layers that are able to detect patterns.
- With each conv layer, we need to specify the number of filters it should have. Filters are what help to detect the patterns.
- Patterns can be something like edges in the pattern, so the filter could be an "edge detector". Other patterns can be corners, circles, squares, etc.<br>
These simple and somewhat geometric filters are what we'd see at the start of our network.<br>
The deeper the network, the more sophisticated the filters become. So in later layers, rather than edges and simple shapes, the filters may detect things like, eyes, hands, leaves, etc. In even deeper layers, filters may detect things like a person, cats, dogs, trees, etc.



## Challenging, interesting, or exciting aspects of today's assignment
<To be filled>

## Additional resources used 
<To be filled>
