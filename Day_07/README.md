# Optimization

## Topics covered in today's module
* Optimization
* Gradident Descent
* Optimizers(SGD, ADAM, etc.)

## Main takeaways from doing today's assignment
### Optimization in ML/DL
- Optimization is a process that is used with the goal to minimize the loss function and improve the model performance.
- To do that, it adjusts (increase/decrease) the weights and other parameters to find the values that result in the minimum loss.

### Gradient Descent 
$$\begin{equation}
\mathbf{θ}= \mathbf{θ} −\eta \times \nabla_\mathbf{θ} J(\mathbf{θ})
\end{equation}$$

- where:
  - $\mathbf{θ}$ are the parameters of the model
  - $\eta$ (eta) is the learning rate
  - $J(\mathbf{θ})$ is the loss (also called $\mathcal{L}$) 
  - $\nabla_\theta J(\mathbf{θ})$ is the **gradient** of the loss with respect to the parameters

![image](https://user-images.githubusercontent.com/70928356/221179139-76c5cc8f-aa53-4480-9c51-c3d69e85381f.png)

- It is the basis for many optimization algorithms such as:
  - Momentum
  - RMSProp
  - Adam
  
- Variants of GD:
  - Batch Gradient Descent
  - Stochastic Gradient Descent (SGD)
  - Mini Batch Stochastic Gradient Descent (MB-SGD)

### Batch Gradient Descent (also just called Gradient Descent)
- All of the data (training examples) are used to calculate the gradient at each epoch
- The average of the gradients of all the data os calculated and used to update the parameters at each epoch
- 👍 The updates of parameters are very smooth, and we move smoothly towards the optimum solution. This is because we are averaging over all the gradients for a single step 
- 👎 However, it is slow and takes a lot of time to make a single update. Therefore, it is not ideal for large training datasets
- 👎 BGD is not compatible with online learning, where we get new examples during training
- 👎 Uses a lot of compute time and memory

### Stochastic Gradient Descent (SGD)
![image](https://user-images.githubusercontent.com/70928356/221186064-17def835-f643-4fbf-ba14-c501922bc2ec.png)

- With SDG, only **one** training sample is used to calculate an estimate of the gradient and update the parameters per epoch
- 👎 Because only one example is considered at a time, the updates in parameters are very noisy and the loss will fluctuate. Therefore, finding the minimum (local or global) is NOT guaranteed
- 👍 It performs well in practice and allows for online learning
- 👍 Having noisy estimates can act as a form of regularization and prevent overfitting
- 👍 We need much less memory and compute power than BGD, since only one training example is used at a time

### Mini Batch Stochastic Gradient Descent (MB-SGD)
![image](https://user-images.githubusercontent.com/70928356/221195645-056d50ce-39ef-4b96-b453-3d80ef82de32.png)

- It is a compromise between batch and stochastic gradient descent
- Here, we use a subset (mini-batch) of the training examples to calculate an estimate of the gradient and update the weights. The number of examples (batch size) that will be used is fixed.
- We still have *some* noise in the gradient estimate and depending on the batch size the updates can be made less noisy (greater batch -> less noise)
- It has the advantages of both between batch and stochastic gradient descent

***In deep learning, we almost always use mini-batch gradient descent. However, it is often referred to simply as SGD***

### Which Optimization algorithm should we use?
This depends on the model and dataset, and there are no specific rules for it.

These are some guidelines:
- **Adam** typically works very well in a large number of settings and is usually a good choice
- **RMSProp** can often outperform Adam for RNNs as well as in RL. If you are working in either of these domains, then it might be worth trying **RMSProp**
- **SGD** and **SGD with momentum** often work just as well as more sophisticated methods like Adam even though they are simple

### Learning Rate
- Also refered to as **step size**
- A configurable hyperparameter that controls how much to change the model in response to the estimated error each time the model weights are updated.
- It has a small positive value, usually ranging from 0.0 to 1.0
![image](https://user-images.githubusercontent.com/70928356/221395688-af3f660e-ab78-42b0-9f97-2c6ca6c8b739.png)

- If the learning rate is too small, then the optimization will be slow. The model is likely to get stuck into a local minimum or plateau
- If the learning rate is too high, then the updates will be very large. This can cause the optimization to diverge
- The learning rate influences the optimizer's convergence, therefore we should pick an appropriate value
![image](https://user-images.githubusercontent.com/70928356/221395699-ef99972f-8ca6-4a7e-9bfa-f6be3336a86f.png)


### Gradient Descent with Momentum
- Momentum helps to accelerate the GD and mive faster towards convergence
- An issue wil vanilla (pure) GD is that the progression of the search can bounce around the search space based on the gradient. While moving downhill, there can be spikes which cause noisy gradients. This can slow down the progress of the search
- Using Momentum is one of the ways to approach this problem. It takes into consideration the history (past gradients)
- It is a configurable hyperparameter `Y` ranging from 0.0 to 1.0. The higher the value, the more past values are taken into consideration. It's usually set to 0.9
![image](https://user-images.githubusercontent.com/70928356/221396164-1f0b62e7-aa2d-4e8a-9586-2025bfb55119.png)


### Adaptive Optimization
- In adaptive optimization, the parameters, such as the learning rate and momentum, **will not stay constant**
- Instead, these values will constantly adapt for each and every weight in the network and hence will also change along with the weights
- Some adaptive algorithms:
  - AdaGrad (Adaptive Gradient)
  - AdaDelta
  - RMSprop
  - Adam
- Adam optimizer is the most popular GD optimization algorithm
- Adam is computationally efficient and has very little memory requirement
- Adam implements the exponential moving average of the gradients to scale the learning rate. It keeps exponentially decaying averages of past gradients

## Challenging, interesting, or exciting aspects of today's assignment
- It was interesting to learn about the many different algorithms we can use to optimize the model

## Additional resources used 
- [Batch, Mini Batch & Stochastic Gradient Descent | Towards Data Science](https://towardsdatascience.com/batch-mini-batch-stochastic-gradient-descent-7a62ecba642a)
- [Variants of Gradient Descent Algorithm
 | Analytics Vidhya](https://www.analyticsvidhya.com/blog/2021/03/variants-of-gradient-descent-algorithm/)
- [Is Gradient Descent central to every optimizer? | Stack Exchange](https://datascience.stackexchange.com/questions/47142/is-gradient-descent-central-to-every-optimizer)
- [Does batch size matter?
 | Jane Street Tech Blog](https://blog.janestreet.com/does-batch-size-matter/)
 - [A DISCIPLINED APPROACH TO NEURAL NETWORK
HYPER-PARAMETERS: PART 1 – LEARNING RATE,
BATCH SIZE, MOMENTUM, AND WEIGHT DECAY | Research paper by Leslie N. Smith](https://arxiv.org/pdf/1803.09820.pdf)
- [Gradient Descent With Momentum from Scratch
 | Machine Learning Mastery](https://machinelearningmastery.com/gradient-descent-with-momentum-from-scratch/)
 - [Understanding Adaptive Optimization techniques in Deep learning | Analytics India Mag](https://analyticsindiamag.com/understanding-adaptive-optimization-techniques-in-deep-learning/)
