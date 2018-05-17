**********
Perceptron
**********

Initializing a Perceptron
-------------------------
.. code-block:: java

  int num_inputs = 2;
  int num_outputs = 1;
  Perceptron pnn = new Perceptron(num_inputs, num_outputs);

Feeding Data through a Perceptron and receiving the Output
----------------------------------------------------------
.. code-block:: java

  float[] inputs = new float[] {1, 0};
  float[] outputs = pnn.feedforward(inputs);
  System.out.println(outputs);
  // gives : [0.5345]

Training a Perceptron
---------------------
.. code-block:: java

  float[] answers = new float[] {1};
  pnn.train_gradient_descent(inputs, answers);

  System.out.println(pnn.feedforward(inputs));
  // gives : [0.98799]

use momentum for training
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**considered as a faster way of training**

.. code-block:: java

  float[] answers = new float[] {1};
  pnn.train_momentum_gradient_descent(inputs, answers);

  System.out.println(pnn.feedforward(inputs));
  // gives : [0.98799]

Setting extra Variables
-----------------------
.. code-block:: java

  pnn.set_learning_rate(float);
  pnn.set_momentum_rate(float);
  pnn.set_print_interval(int);
