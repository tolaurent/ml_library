Neural network
==============

Neural network concept
----------------------
Neural network is a type of machine learning that take into accounts multiple hidden layers and non-linear activation functions.
A neural network takes an input that is then passed to hidden neuron and outputs a prediction that represent a combination of hidden neurons.
These neurons are trained using optimization techniques such as gradient descent using backpropagation. Each neuron has a set of parameters (bias and weights)
that can be adjusted to reduce the error of the model.

Neuron
------
A neuron takes a group of weighted inputs, applies an activation function and returns an output.
Original inputs or outputs from a previous layer can serve as input for a neuron. An activation function to the 
"sum of the weighted inputs" is then applied to the neuron.

Weighted input
-------------
A neuron’s input equals the sum of weighted outputs from all neurons in the previous layer. Each input is multiplied by the weight associated with the synapse connecting the input to the current neuron. If there are 3 inputs or neurons in the previous layer, each neuron in the current layer will have 3 distinct weights — one for each each synapse.

**Single Input**

.. math::

  Z &= Input \cdot Weight \\
    &= X W

**Multiple Inputs**

.. math::

  Z &= \sum_{i=1}^{n}x_i w_i \\
    &= x_1 w_1 + x_2 w_2 + x_3 w_3


Notice, it’s exactly the same equation we use with linear regression! In fact, a neural network with a single neuron is the same as linear regression! The only difference is the neural network post-processes the weighted input with an activation function.


Activation function
-------------------

Activations function allows to introduce non linearity in neural networks and build complex relationships.
This include relu, sigmoid and hyperbolic tangent.



Activation functions typically have the following properties:

  * **Non-linear** - In linear regression we’re limited to a prediction equation that looks like a straight line. Activation functions provide non-linearity.

  * **Continuously differentiable** - To improve our model with gradient descent, we need our output to have a nice slope so we can compute error derivatives with respect to weights. 

  * **Fixed Range** - Activation functions typically squash the input data into a narrow range that makes training the model more stable and efficient. 


Loss functions
--------------

Loss function is a cost function that helps evaluatingn how the model is performing. The loss function needs to be
differentiable to estimate the gradient and update the parameters. There are numerous forms of loss functions including MSE and cross-entropy loss.

Optimization algorithms
-----------------------

There exists multiple algorithms to optimize the parameters in neural network.
This includes:

* Adagrad

* Adam

* Momentum 


