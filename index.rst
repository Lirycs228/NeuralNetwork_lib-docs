.. NeuralNetwork_lib documentation master file, created by
   sphinx-quickstart on Wed May 16 22:15:26 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to the documentation of NeuralNetwork_lib!
==================================================

.. toctree::
   :maxdepth: 0
   :caption: Contents:


Perceptron
==========

Initializing a Perceptron
-------------------------
>>> int num_inputs = 2;
>>> int num_outputs = 1;
>>> Perceptron pnn = new Perceptron(num_inputs, num_outputs);

Feeding Data through a Perceptron and receiving the Output
----------------------------------------------------------
>>> float[] inputs = new float[] {1, 0};
>>> float[] outputs = pnn.feedforward(inputs);
>>> System.out.println(outputs);
[0.5345]

Training a Perceptron
---------------------
>>> float[] answers = new float[] {1};
>>> pnn.train_gradient_descent(inputs, answers);

>>> System.out.println(pnn.feedforward(inputs));
[0.98799]

use momentum for training
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**considered as a faster way of training**

>>> float[] answers = new float[] {1};
>>> pnn.train_momentum_gradient_descent(inputs, answers);

>>> System.out.println(pnn.feedforward(inputs));
[0.98799]

Setting extra Variables
-----------------------
>>> pnn.set_learning_rate(float);
>>> pnn.set_momentum_rate(float);
>>> pnn.set_print_interval(int);

Neural Network
==============

Initializing a Neural Network
-----------------------------
>>> int num_inputs = 2;
>>> int[] num_hidden = new int[] {4, 3};
>>> int num_outputs = 1;
>>> NeuralNetwork nn = new NeuralNetwork(num_inputs, num_hidden, um_outputs);

Feeding Data through a Neural Network and receiving the Output
--------------------------------------------------------------
>>> float[] inputs = new float[] {1, 0};
>>> float[] outputs = nn.feedforward(inputs);
>>> System.out.println(outputs);
[0.5345]

Training a Neural Network
-------------------------
>>> float[] answers = new float[] {1};
>>> nn.train_gradient_descent(inputs, answers);

>>> System.out.println(nn.feedforward(inputs));
[0.98799]

use momentum for training
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**considered as a faster way of training**

>>> float[] answers = new float[] {1};
>>> nn.train_momentum_gradient_descent(inputs, answers);

>>> System.out.println(nn.feedforward(inputs));
[0.98799]

Setting extra Variables
-----------------------
>>> pnn.set_learning_rate(float);
>>> pnn.set_momentum_rate(float);
>>> pnn.set_print_interval(int);

Saving and Loading
==================

.. DANGER::
   save() may throw an IOException

Perceptron
----------
>>> String path = "path\\to\\file.nn";
>>> Perceptron pnn = Load.Load_Perceptron(path);
>>> pnn.save(path);

Neural Network
--------------
>>> String path = "path\\to\\file.nn";
>>> NeuralNetwork nn = Load.Load_NeuralNetwork(path);
>>> nn.save(path);
