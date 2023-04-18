# Autoencoders

## Topics covered in today's module
* Upsampling 
* Downsampling
* Encoders
* Decoders

## Main takeaways from doing today's assignment
### Upsampling
- Can also be called **expansion**.
- It can describe an entire process of expansion and filtering (interpolation).
- **Decoders perform upsampling**

### Downsampling
- Can also be called **compression**.
- It can describe an entire process of reduction (filtering). 
- **Encoders perform downsampling**

### Autoencoder
![image](https://user-images.githubusercontent.com/70928356/232730848-f4ebd8d6-fc40-4395-bb24-0b3b298bbdc8.png)
- Autoencoder's architecture consists of an **encoder**, **latent space**, and a **decoder**.
- The encoder, maps the input data to a lower-dimensional latent space, and the decoder reconstructs the original input from the encoded representation.
- It is a class of unsupervised network.
- It aims to learn a compressed representation of input data.
- Can be used for unsupervised learning tasks such as anomaly detection, dimensionality reduction, and image denoising.

- Autoencoders are **data-specific**, which means that they will only be able to compress data similar to what they have been trained on.
- Autoencoders are **lossy**, which means that the decompressed outputs will be degraded compared to the original inputs (similar to MP3 or JPEG compression). This differs from lossless arithmetic compression.
- Autoencoders are **learned automatically** from data examples, which is a useful property: it means that it is easy to train specialized instances of the algorithm that will perform well on a specific type of input. It doesn't require any new engineering, just appropriate training data.

#### Encoder
- The encoder maps the input data to a lower-dimensional latent space representation.
- It generally uses a series of dense and/or convolutional layers to encode an image into a fixed length vector which represents the image in a compact form.
- The output of the encoder layer(s) is called the encoding, or latent representation.
- The encoding is a compressed version of the input data that preserves the most relevant information.
- The encoder is typically trained using backpropagation and gradient descent optimization to minimize the difference between the original input data and the reconstructed output from the decoder.
- The encoding can be used for various tasks such as dimensionality reduction, anomaly detection, and transfer learning.

Example:
```py
encoder = tf.keras.models.Sequential([
    tf.keras.layers.Flatten(input_shape = (28, 28)),
    tf.keras.layers.Dense(512),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(256),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(128),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(64),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(LATENT_SIZE),
    tf.keras.layers.LeakyReLU()
])
```

#### Decoder
- The decoder reconstructs the original input data from the lower-dimensional latent representation produced by the encoder.
- It uses dense and/or convolutional layers to convert the latent representation vector back into that same image or another modified image.
- The output of the decoder layer(s) is the reconstructed data, which should ideally be as close as possible to the original input data.
- The decoder is typically trained together with the encoder using backpropagation and gradient descent optimization to minimize the difference between the original input data and the reconstructed output from the decoder.
- The reconstructed data can be used for various tasks such as denoising, image synthesis, and transfer learning.
- The decoder can also be combined with other neural network models, such as convolutional neural networks (CNNs), to improve the performance of the autoencoder for specific tasks.

Example:
```py
decoder = tf.keras.models.Sequential([
    tf.keras.layers.Dense(64, input_shape = (LATENT_SIZE,)),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(128),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(256),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(512),
    tf.keras.layers.LeakyReLU(),
    tf.keras.layers.Dropout(0.5),
    tf.keras.layers.Dense(784),
    tf.keras.layers.Activation("sigmoid"),
    tf.keras.layers.Reshape((28, 28))
])
```
#### Latent Space
- The latent space is the lower-dimensional representation of the input data that is learned by the encoder in an autoencoder neural network.
- Can sometimes be referred to as the encoding, bottleneck, or compressed representation.
- The size of that vector is called latent size. This value is a crucial hyperparameter. If this value is too small, there won't be enough data for reconstruction and if the value is too large, overfitting can occur.
- The latent size can also be considered as the dimensions we model the middle of an autoencoder where the encoder and decoder are connected.

## Challenging, interesting, or exciting aspects of today's assignment
- It is very interesting to see how the model can be able to pick up the patterns in the image, and reconstructed after it gets compressed.

## Additional resources used 
- [Upsampling | Wikipedia](https://en.wikipedia.org/wiki/Upsampling)
- [What are Autoencoders? | Simplilearn](https://www.simplilearn.com/tutorials/deep-learning-tutorial/what-are-autoencoders-in-deep-learning#:~:text=Autoencoders%20are%20a%20type%20of,important%20part%20in%20image%20construction.)
