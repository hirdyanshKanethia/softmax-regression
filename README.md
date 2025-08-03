<img width="850" height="376" alt="image" src="https://github.com/user-attachments/assets/d3a7cca3-e12e-4a86-832d-2976baa2250e" />

---
# Softmax regression
- This is a classification algorithm used for multinomial classification. It is capable of classifying instances from 2 or more than 2 classes.
- Multiple mathematical concepts and algorithms are implemented from scratch in order to overall implement softmax regression. This includes the softmax function, the cost and gradient functions for implementing gradient descent and ridge regularization to regularize the model.
---
# The iris dataset
- This is model is implemented on the iris dataset.
- It is a flower dataset with 3 target classes. More on that dataset here [Iris dataset](https://scikit-learn.org/1.5/auto_examples/datasets/plot_iris_dataset.html)
---
# Implementation
## Bias Term
- The first steps are to add a bias term to the feature list in order to provide the model with a non-weighted featrue. 
- This increases the degree of freedom of the model and allows it to explore more possible solutions other than the ones passing through the origin. 
  
## One hot encoding
- one hot encoding is used for the target values (the classes) in order to provide the model a clear set of output values and allow it to give the predictions in term of probabilities. 
- the origin target values were single values from 0 to 2 for the 3 classes, implementing one hot encoding allows us to convert target values in the form of [1, 0, 0], [0, 1, 0] and [0, 0, 1] for 0, 1 and 2 classes respectively and get predictions in terms of probabilities i.e -> [0.1, 0.8, 0.1] is an example output predicted heavily to be belonging to the class 1. 

## Logit Equation
- The logit equation given below is used to calculate raw scores (logits) of each class for each instance. 
<img width="646" height="170" alt="Image" src="https://github.com/user-attachments/assets/bfef07f6-e6a0-42c0-8932-211211fd89d2" />

## Softmax function
- The softmax function is implemented on the raw scores calculated by the logit equation to convert logits into probabilities. 
<img width="642" height="182" alt="image" src="https://github.com/user-attachments/assets/fdbafc41-9ec9-4d13-a1a4-d0db27a4700b" />

## Cost function and gradient equation
- The cost function is used to measure the error of the model. The goal is to minimize the cost function in order to minimize the error.  
<img width="294" height="65" alt="image" src="https://github.com/user-attachments/assets/729227be-0b2c-48f6-8305-6512568b88a5" />  
- The minimazation is implemented using gradient descent, a converging algorithm used to minimize convex (bowl-shaped) functions.  
<img width="319" height="58" alt="image" src="https://github.com/user-attachments/assets/a875339b-3359-4b4c-a619-6d8dc735d6f2" />  

## L2 (ridge) regularization
- l2 regularization, also called as ridge regularization is used in order to minimize overfitting in the model and capture the actual trend.  
- It is implemented by adding a regularization term to the cost function that prevents the model weights from increasing too much or fluctuating too much, hence resulting in lesser overfitting by the model. 
<img width="144" height="68" alt="image" src="https://github.com/user-attachments/assets/1a33ec61-b708-4e83-be22-f837722f6203" />

## Final cost function
- The final cost function of the model is given as follows
<img width="694" height="184" alt="image" src="https://github.com/user-attachments/assets/aeabd9ef-40d4-4e09-9600-64f27c684edb" /> 

## Early stopping
- It is a regularization technique used to prevent overfitting 
- It is implemented by analyzing the model regularly on a validation set in order to measure the error of the model. Once the error value on the validation set starts increasing, the model is stopped early as it has started to overfit the training data. 
- Early stopping can result in reduced training times. 
