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

Convolutional Neural Network
----------------------------

.. ATTENTION::
  Convolutional Neural Networks are not yet supported in this
