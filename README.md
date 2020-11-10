# Complete-Neural-Network
Building a complete neural network using Numpy. I will implement all the steps required to build a network - feedforward, loss computation, backpropagation, weight updates etc. 
I will using the MNIST dataset to train the model to classify handwritten digits between 0-9.

The assignment is divided into the following sections:

Data preparation
Feedforward
Loss computation
Backpropagation
Parameter updates
Model training and predictions

Data Preparation
You do not have to write any code in this section (Data Preparation). Please refer to the code provided in the notebook while going through these sections.

 

Firstly, we load the data using the function load_data(). The function data_wrapper() is then applied to the data to get the train and test data in the desired shape. Please note that the code needs to take a batch of data points as the input. Hence, be careful while checking the dimensions.

 

You already know that we have 28x28 greyscale images in the MNIST dataset. Hence, each input image is a vector of length 784. The ground truth labels of a batch are stored in a matrix which is converted to a one-hot matrix. Also, the output of the model is a softmax output of length 10. 

 

Hence, we have the following:

train_set_x shape: (784, 50000)
train_set_y shape: (10, 50000)
test_set_x shape: (784, 10000)
test_set_y shape: (10, 10000)
 

Now that the data is in the required shape, let's look at the next section - feedforward.

 

Feedforward
There are functions assigned to different subparts of feedforward which we will discuss in some time. But before that, there are some things to take into consideration that will help in implementing the code.

The whole data is taken as one batch. No minibatch gradient descent is performed
The cumulative input to the layer 
Z
l
 is now a step in feedforward
The output of the last layer is denoted as 
H
L
 instead of P where layer 
L
 is the final output layer. Hence, there are 
L
−
1
 hidden layers.
For each layer 
l
, the 
Z
l
 is stored as 'activation_memory' and 
H
l
−
1
, 
W
l
, 
b
l
 are stored as 'linear_memory' to use later in backpropagation

