This course is one of the most famous courses on Coursera. Now I go two weeks ahead of the deadline and reach Week 5, I plan to finish it in the flowing few days. 

This course is the perfect choice if you are not satisfied with just being able to drive some machine learning framework to work but also eager to know what is under the hood, this course will teach you the most concrete mathematical principles and equations underlying most AI applications. Overall in this course, Prof. Ng delivered profound knowledge in a comprehensive way. But this course isn't flawless, for example Week 5 uses intuition to explain backpropogation and example applications, which I would say verbose and useless. 

Bellow is my note of important concept, it may be incomplete and biased, feel free to leave comment and let me know, I will keep it updated.

The Syllabus skeleton is left, to remind readers in which section that concept is taught.

# Week 1: Introduction

Supervised Learning and Unsupervised Learning

# Week 2:

## Multivariate Linear Regression

### Multiple Features

### Gradient Descent For Multiple Variables

### Gradient Descent in Practice I - Feature Scaling

### Gradient Descent in Practice II - Learning Rate

### Features and Polynomial Regression

## Computing Parameters Analytically

### Normal Equation

### Normal Equation Noninvertibility


# Week 3: Logistic Regression

Questions:

1. Is the gradient too small?

2. Why logistic regression has advantage over linear regression when it comes to classification.

http://www.theanalysisfactor.com/why-logistic-regression-for-binary-response/

## Classification and Representation

### Classification

### Hypothesis Representation

$\theta(x)=g(\theta^Tx)$
$z=\theta^Tx$
$g(z)=\frac{1}{1+e^{-z}}$

### Decision Boundary

TODO
convex function

## Logistic Regression Model

###Cost Function

$J(\theta)=-\frac{1}{m}[\sum_{i=0}^{m}y^{(i)}\log h_\theta(x^{(i)})+(1-y^{(i)})\log(1-h_\theta(x^{(i)}))] + \frac{\lambda}{2m}\sum_{j=1}^{n}\theta_j^2 $

$J(\Theta)=−\frac{1}{m}\sum_{i=1}^m\sum_{k=1}^K[y^{(i)}k\log((h_\Theta(x(i)))_k)+(1−y_ k^{(i)})\log(1−(h_Theta(x^{(i)}))_k)]+\frac{λ}{2m}\sum_{l=1}^{L−1}\sum_{i=1}^{sl}\sum_{j=1}^{sl+1}(\Theta^{(l)}_{j,i})^2$

# Week 4: 

###Simplified Cost Function and Gradient Descent

### Advanced Optimization

fminunc in Octave is very useful to auto generate cost and gradient

## Multiclass Classification

### Multiclass Classification: one-vs-all

## Solving the Problem of Overfitting

### The Problem of Overfitting

### Cost function

### Regularized Linear Regression

### Regularized Logistic Regression

# Week 4

## Non-linear Hypotheses

## Neurons and Brains

## Neural Networks

### Model Representation

#### How to determine the dimension of one layer?
If network has $s_j$ units in layer j and $s_j+1$ units in layer j+1, then $\theta(j)$ will be of dimension $s_{j+1}(s_j+1)$.

#### Forward Propagation

## Applications

### Examples and Intuitions 

# Week 5: Neural Networks: Learning

## Cost Function and Backpropagation

### Cost Function

### Backpropagation Algorithm

Error(delta) of cost for Node

### Backpropagation Intuition

## Backpropagation in Practice

### Implementation Note: Unrolling Parameters

### Gradient Checking

gradApprox ≈ deltaVector

The code to compute gradApprox can be very slow

### Random Initialization 

Initialization theta can't be set all to 0, otherwise the backpropagation will get all same theta. So theta matrix should be initialize randomly. This is also called Symmetry Breaking.

One effective strategy for choosing $\epsilon_{init}$ is to base it on the number of units in the network. A good choice of $\epsilon_{init}$ is $\epsilon_{init} = \frac{\sqrt6}{\sqrt{L_{in}+L_{out}}}$ , where $L_{in} = s_l$ and $L_{out} = s_l+1$ are the number of units in the layers adjacent to $\Theta^{(l)}$.

### Putting It Together

Question: Can we just skip gradient checking?
A: No, we need to check the backpropogation is bug free.

First, pick a network architecture; choose the layout of your neural network, including how many hidden units in each layer and how many layers in total you want to have.

Number of input units = dimension of features x(i)

Number of output units = number of classes

Number of hidden units per layer = usually more the better (must balance with cost of computation as it increases with more hidden units)

Defaults: 1 hidden layer. If you have more than 1 hidden layer, then it is recommended that you have the same number of units in every hidden layer.

**Training a Neural Network**

1. Randomly initialize the weights
2. Implement forward propagation to get hΘ(x(i)) for any x(i)
3. Implement the cost function
4. Implement backpropagation to compute partial derivatives
5. Use gradient checking to confirm that your backpropagation works. Then disable gradient checking.
6. Use gradient descent or a built-in optimization function to minimize the cost function with the weights in theta.

##Application of Neural Networks

### Autonomous Driving

### Programming Assignment

Visualizing the hidden layer

One way to understand what your neural network is learning is to visualize what the representations captured by the hidden units.

# Week 6: 

## Advice for Applying Machine Learning

## Evaluating a Learning Algorithm

### Deciding What to Try Next

### Evaluating a Hypothesis

### Model Selection and Train/Validation/Test Sets

## Bias vs. Variance

### Diagnosing Bias vs. Variance

###Regularization and Bias/Variance

In order to choose the model and the regularization term λ, we need to:

Create a list of lambdas (i.e. λ∈{0,0.01,0.02,0.04,0.08,0.16,0.32,0.64,1.28,2.56,5.12,10.24});
Create a set of models with different degrees or any other variants.
Iterate through the λs and for each λ go through all the models to learn some Θ.
Compute the cross validation error using the learned Θ (computed with λ) on the JCV(Θ) without regularization or λ = 0.
Select the best combo that produces the lowest error on the cross validation set.
Using the best combo Θ and λ, apply it on Jtest(Θ) to see if it has a good generalization of the problem.

### Learning Curves

### Deciding What to do Next Revisited

## Review

### Quiz: Advice for Applying Machine Learning5 questions

### Programming Assignment: Regularized Linear Regression and Bias/Variance3h

## Machine Learning System Design

## Building a Spam Classifier

### Prioritizing What to Work On

### Error Analysis

Accuracy = (true positives + true negatives) / (total examples)

Precision = (true positives) / (true positives + false positives)

Recall = (true positives) / (true positives + false negatives)

F1 score = (2 * precision * recall) / (precision + recall)

## Handling Skewed Data

### Error Metrics for Skewed Classes

### Trading Off Precision and Recall

### Using Large Data Sets

### Data For Machine Learning

## Review

### Quiz: Machine Learning System Design5 questions

TODO
https://www.coursera.org/learn/machine-learning/exam/vrjOT/machine-learning-system-design

# Week 7: Support Vector Machines

Question: What is SVM for?


## Large Margin Classification

### Optimization Objective

### Large Margin Intuition

### Mathematics Behind Large Margin Classification

## Kernels

kernel refers to similarity function.

### SVMs in Practice

### Using An SVM

Do not perform feature scaling before using the Gaussian kernel.

Gaussian kernel, linear kernel.

## Review

### Quiz: Support Vector Machines5 questions

### Programming Assignment: Support Vector Machines

# Week 8

## Unsupervised Learning

### Clustering

#### Unsupervised Learning: Introduction

#### K-Means Algorithm

#### Optimization Objective

#### Random Initialization

#### Choosing the Number of Clusters
https://www.coursera.org/learn/machine-learning/exam/4sGmv/unsupervised-learning
## Dimensionality Reduction

###Motivation

####Motivation I: Data Compression

####Motivation II: Visualization

###Principal Component Analysis

####Principal Component Analysis Problem Formulation

Preprocess is needed: Feature scaling and mean normalization

####Principal Component Analysis Algorithm

###Applying PCA

####Reconstruction from Compressed Representation

####Choosing the Number of Principal Components

####Advice for Applying PCA

###Review

####Programming Assignment: K-Means Clustering and PCA

