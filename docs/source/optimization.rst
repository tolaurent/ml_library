Optimization
============

It is very important to tweak the weights of the model during the training process, to make our predictions as correct and optimized as possible. But how exactly do you do that? How do you change the parameters of your model, by how much, and when?


Adagrad
-------

Adagrad sets the learning according to a parameter.

- Parameters having higher gradients or frequent updates should have slower learning rate (Opposite for parameters with low gradient)
- Division by the sum of the squares of all previous gradients of the parameter (learning rate will be lower in case of high values)

.. math::
  \theta_{t+1} = \theta_t - \frac{\eta}{\sqrt{\sum_{i=1}^{t}{g_{i}^{2}} + \epsilon}} \odot g_{t}
   
    

The updated parameter vector at time step t+1 :math:`\theta_{t+1}`

Momentum
--------

Momentum takes into account past gradients to smooth out the update. This is based on an exponential weighted average of the gradient on previous steps. 
This results in minimizing oscillations and faster convergence.

.. math::
  v_t = \beta v_{t-1} + (1 - \beta) g_t

  \theta_{t+1} = \theta_{t} - \alpha v_t
  
 :math:`v(t)` is the weighted average of the past gradients at time step t

 :math:`\alpha` is the learning rate

 :math:`\beta` is the hyperparameter to be tuned

Adam
----

Adaptative Moment Estimation (Adam) consists of the following steps:

- Computation of the exponentially weighted average of post gradients
- Computation of the exponentiallu weighted average of the squares of past gradients
- The average have a bias toward zero and to counteract this a bias correction is applied
- The parameters are updated based on the calculated averages

.. math::
  m_t = \beta_1 m_{t-1} + (1 - \beta_1) g_t

  v_t = \beta_2 v_{t-1} + (1 - \beta_2) g_t^2

  \hat{m}_t = \frac{m_t}{1 - \beta_1^t}

  \hat{v}_t = \frac{v_t}{1 - \beta_2^t}

  \theta_{t+1} = \theta_t - \frac{\alpha}{\sqrt{\hat{v}_t} + \epsilon} \hat{m}_t

 :math: `m(t)` is the exponentially weighted average of the past gradient at time step t

 :math:`v(t)` is the weighted average of the past squares of the gradients at time step t

 :math:`\beta_1` is the hyperparameter to be tuned for bias correction of the exponentially weighted average of the past gradients

 :math:`\beta_2` is the hyperparameter to be tuned for bias correction of the exponentially weighted average of the square of the past gradients

 :math:`\theta_{t+1}` is the parameter to be updated at time step t

 :math:`\alpha` is the learning rate

 :math:`\epsilon` is a very small value to avoid dividing by zero

