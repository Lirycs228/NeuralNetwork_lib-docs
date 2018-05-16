.. NeuralNetwork_lib documentation master file, created by
   sphinx-quickstart on Wed May 16 22:15:26 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

NeuralNetwork_lib
=================

.. toctree::
   :maxdepth: 0
   :caption: Contents:


Perceptron
==========

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

Genetic Perceptron
==================

Initializing a Genetic Perceptron
---------------------------------
.. code-block:: java

  int num_inputs = 2;
  int num_outputs = 1;
  int population_size = 100;
  int random_per_generation = 10;
  Perceptron gpnn = new Perceptron(population_size, random_per_generation, num_inputs, num_outputs);

Feeding Data through a Genetic Perceptron and receiving the Output
------------------------------------------------------------------
.. code-block:: java

  float[] inputs = new float[] {1, 0};
  float[] outputs = gpnn.overall_best.feedforward(inputs);
  System.out.println(outputs);
  // gives : [0.5345]

Training a Genetic Perceptron
-----------------------------
.. code-block:: java

  float[] answers = new float[] {1};
  int total_generations = 1000;
  for (int generation = 0; generation < total_generations; generation++) {
    Perceptron[] current_generation = gpnn.get_current_generation();
    float[] current_fitness = new float[current_generation.length];
    for (int aspect = 0; aspect < current_generation.length; aspect++) {
      current_fitness[aspect] = answers[0] - current_generation[aspect].feedforward(inputs));
    }
    enn.evolve_best(current_fitness);
  }

  System.out.println(gpnn.overall_best.feedforward(inputs));
  // gives : [0.98799]

Setting extra Variables
-----------------------
.. code-block:: java

  pnn.set_mutation_rate(float);
  pnn.set_evolution_rate(float);
  pnn.set_offspring_mutation_rate(float);

Neural Network
==============

Initializing a Neural Network
-----------------------------
.. code-block:: java

  int num_inputs = 2;
  int[] num_hidden = new int[] {4, 3};
  int num_outputs = 1;
  NeuralNetwork nn = new NeuralNetwork(num_inputs, num_hidden, um_outputs);

Feeding Data through a Neural Network and receiving the Output
--------------------------------------------------------------
.. code-block:: java

  float[] inputs = new float[] {1, 0};
  float[] outputs = nn.feedforward(inputs);
  System.out.println(outputs);
  // gives : [0.5345]

Training a Neural Network
-------------------------
.. code-block:: java

  float[] answers = new float[] {1};
  nn.train_gradient_descent(inputs, answers);

  System.out.println(nn.feedforward(inputs));
  // gives : [0.98799]

use momentum for training
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
**considered as a faster way of training**

.. code-block:: java

  float[] answers = new float[] {1};
  nn.train_momentum_gradient_descent(inputs, answers);

  System.out.println(nn.feedforward(inputs));
  // gives : [0.98799]

Setting extra Variables
-----------------------
.. code-block:: java

  pnn.set_learning_rate(float);
  pnn.set_momentum_rate(float);
  pnn.set_print_interval(int);

Saving and Loading
==================

.. WARNING::
   save() may throw an IOException

Perceptron
----------
.. code-block:: java

  String path = "path\\to\\file.nn";
  Perceptron pnn = Load.Load_Perceptron(path);
  pnn.save(path);

Neural Network
--------------
.. code-block:: java

  String path = "path\\to\\file.nn";
  NeuralNetwork nn = Load.Load_NeuralNetwork(path);
  nn.save(path);
