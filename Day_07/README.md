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

## Challenging, interesting, or exciting aspects of today's assignment
<To be filled>

## Additional resources used 
- [Batch, Mini Batch & Stochastic Gradient Descent | Towards Data Science](https://towardsdatascience.com/batch-mini-batch-stochastic-gradient-descent-7a62ecba642a)
