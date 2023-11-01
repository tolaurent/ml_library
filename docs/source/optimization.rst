Optimization
============

It is very important to tweak the weights of the model during the training process, to make our predictions as correct and optimized as possible. But how exactly do you do that? How do you change the parameters of your model, by how much, and when?


Adagrad
-------

Adagrad sets the learning according to a parameter.

- Parameters having higher gradients or frequent updates should have slower learning rate (Opposite for parameters with low gradient)
- Division by the sum of the squares of all previous gradients of the parameter (learning rate will be lower in case of high values)

.. math::
  \theta_{t+1} = \theta_t - \frac{\eta}{\sqrt{\sum{g_{t}^{2}} + \epsilon}} \odot g_{t}
   
    

 :math: `\theta_{t+1}` :the updated parameter vector at time step t+1


