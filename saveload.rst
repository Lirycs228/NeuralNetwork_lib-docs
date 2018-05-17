******************
Saving and Loading
******************

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

Genetic Perceptron
------------------

.. IMPORTANT::
  It is only possible to save the best Perceptron and the Genetic_Perceptron can not be reloaded

.. code-block:: java

  String path = "path\\to\\file.nn";
  pnn.overall_best.save(path);

Genetic Neural Network
----------------------

.. IMPORTANT::
  It is only possible to save the best Neural Network and the Genetic_NeuralNetwork can not be reloaded

.. code-block:: java

  String path = "path\\to\\file.nn";
  nn.overall_best.save(path);

Convolutional Neural Network
----------------------------

.. DANGER::
  Convolutional Neural Networks are not yet supported in this
