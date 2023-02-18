# Classification Loss Functions

## Topics covered in today's module
* Kullback Leibler Divergence Loss
* Binary Cross-Entropy
* Categorical Cross-Entropy
* Sparse Categorical Cross-Entropy

## Main takeaways from doing today's assignment
- There are three kinds of classification tasks:
  - Binary classification: two exclusive classes
  - Multi-class classification: more than two exclusive classes
  - Multi-label classification: just non-exclusive classes
- Loss functions are a measure of how well the model is performing on a specific dataset
- The loss functions that are used for classification include:
  - Binary Cross-Entropy - *used for a binary classification problem*
  - Multi-class Cross-Entropy - *used when true labels are one-hot encoded*
  - Sparse Multi-class Cross-Entropy - *used when true labels are integer values (label encoded)*
  - Kullback-Leibler Divergence (KLD)
- The outputs in classification are in form of a category. The label or number assigned to the classes do not have a numerical meaning.

### Cross-Entropy Loss
- Also referred to as "Logarithmic Loss", "Logistic Loss", or "Log Loss"
- It measures the performance of a classification model that outputs a probability value between 0 and 1
- Cross-entropy can be thought to calculate the total entropy between the distributions

### Kullback-Leibler Divergence (KLD)
$$KLD(p||q) = \int_x p(x) \log \frac{p(x)}{q(x)} dx$$
- It is a measure of how a distribution (pred distribution) varies from a reference distribution (target distribution)
- If $$KLD loss = 0$$, this means that both probability distributions are identical

### Binary Cross Entropy
$$BCE = -\frac{1}{N} \sum_{i=1}^N y_i \cdot \log(p(y_i)) + (1-y_i) \cdot \log(1- p(y_i))$$

- It is used for binary classification problems (output is 0 or 1)
- Binary Cross-Entropy measures how far away the true value (0 or 1) is from the prediction value for each of the classes, and then averages these class-wise errors to obtain the final loss
- It works for **multi-label** classification, as in, input data can belong to more than one class in a multi-class classification problem, while using `sigmoid` as the output activation function
- Formally, this loss is equal to the average of the categorical crossentropy loss on many two-category tasks

### Categorical Cross Entropy
$$CCE = -\frac{1}{N}\sum_{i=1}^{N}y_i\log(\hat{y}_i)$$ 
- It is used when true labels are **one-hot encoded**.<br>
*For example, we have the following true values for 3-class classification problem: dog, cat, bird = [1,0,0], [0,1,0], [0,0,1]*
- Cross-entropy loss increases as the **predicted probability** strays away from the **actual label**
- It heavily penalizes the predictions that are confident (probability closer to 1), but wrong.
- Used for **multi-class**, **single-label** classification

### Sparse Categorical Cross Entropy
$$SCCE = -\log(\hat{y}_i)$$ for $i$ where $one\text{-}hot\text{-}encoding[i] = 1$ 
- A sparse variant of the Multi-Class Cross Entropy Loss. It has the same loss function as Categorical Cross Entropy
- It is used when true labels are **integer encoded** (label encoded)<br>
*For example, we have the following true values for 3-class classification problem: dog, cat, bird = [1], [2], [3], respectively*
- It does not need the true labels to be one-hot encoded
- This is typically used when we have a lot of classes, since one-hot encoding cause a much higher dimensionality than label encoding. Therefore, it save more time and computation than the usualy one-hot encoded CCE


## Challenging, interesting, or exciting aspects of today's assignment
- The distributions of labels contributing to the calculation of the loss function was something I did not quite expect

## Additional resources used 
- [A Gentle Introduction to Cross-Entropy for Machine Learning](https://machinelearningmastery.com/cross-entropy-for-machine-learning/)
- [How to Calculate the KL Divergence for Machine Learning](https://machinelearningmastery.com/divergence-between-probability-distributions/#:~:text=KL%20divergence%20can%20be%20calculated,of%20the%20event%20in%20P.&text=The%20value%20within%20the%20sum%20is%20the%20divergence%20for%20a%20given%20event.)
- [What loss function for multi-class, multi-label classification tasks in neural networks?](https://stats.stackexchange.com/questions/207794/what-loss-function-for-multi-class-multi-label-classification-tasks-in-neural-n)
- [Should I use a categorical cross-entropy or binary cross-entropy loss for binary predictions?](https://stats.stackexchange.com/questions/260505/should-i-use-a-categorical-cross-entropy-or-binary-cross-entropy-loss-for-binary)
- [Difference between categorical and binary cross entropy](https://stackoverflow.com/questions/52965686/difference-between-categorical-and-binary-cross-entropy)
- [Cross Entropy vs. Sparse Cross Entropy: When to use one over the other](https://stats.stackexchange.com/questions/326065/cross-entropy-vs-sparse-cross-entropy-when-to-use-one-over-the-other)
