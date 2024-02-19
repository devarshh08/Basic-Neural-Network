# Basic-Neural-Network

This is a Neural Network created with reference to the Neural Networks From Scratch Video series by Youtuber Sentdex and his book Neural Networks from Scratch.

## Model Explained:

This model first creates a dataset for the required neural network with the help of the function create_data which takes points and classes as input.

This formula returns two arrays X and y, where the data is formed by a pattern in a 2-Dimensional Array in a spiral form, with some added noise for variability.

Then we create a scatter plot with the spiral data, to show how its distributed.

Now to create the layers of the Neural Network, we have the Layer_Dense function, which takes inputs and neurons as input,
with the help of these inputs and neurons we get the weights and biases to be used in the neural network.
Applying the forward function, we get the output with the formula:
Output = Weights*Inputs + Biases

The we apply the Rectified Linear Activation function and update the output.
(
Rectified Linear Activation function states that, 
    if x is less than or equal to zero, y is zero
    else y is equal to x
)

Since we are looking for our model to classify, next we use the Softmax Activation function
(
In this case, the rectified linear function is unbounded and not normalized with other units, so its values can be anything, without any context and each output is independent of the others.

Due to this lack of context, we use the Softmax Activation function which can take in non-normalized and uncategorized inputs and produce a normalized distribution of probabilities.

Simply put, it is like a generalization for linear regression.
)

After using the softmax function, we have an even more efficient output dataset.
So, now we calculate the loss by the Sparse Categorical Cross Entropy function
(
In linear regression, the most common loss function used is the Mean Squared Error loss,
but since we are performing classification on this Neural Network, we use a different loss function.

Since we are getting probabilites as output as a result of the Softmax Activation function,
The Cross Entropy loss function is used to compare y(or targets) to y-hat(or predictions)
)

Example:
```
import math
#An example output from the output layer of the neural network
softmax_output = [0.7, 0.1, 0.2]
#Ground truth
target_output = [1, 0, 0]
loss = -(math.log(softmax_output[0])*target_output[0] +
math.log(softmax_output[1])*target_output[1] +
math.log(softmax_output[2])*target_output[2])

#o/p:
#loss = 0.35667494393873245
```
NOTE: This was just an example taken to explain the categorical cross entropy loss function and it does not use any data from the code so it has no relation with the actual model

Now after applying the loss function, we can simply print the loss, which gives us the output.