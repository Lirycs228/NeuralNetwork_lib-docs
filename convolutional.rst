*****************************
Convolutional Neural Network
*****************************

.. DANGER::
  DO NOT USE!!!
  NOT WORKING!!!

Initializing a Convolutional Neural Network
-------------------------------------------

.. DANGER::
  DO NOT USE!!!
  NOT WORKING!!!

.. code-block:: java

  int input_img_channels = 3;
  int input_img_height = 16;
  int input_img_width = 16;
  int[] input_structure = int[] {input_img_channels, input_img_height, input_img_width};

  int num_conv_layers = 2;
  int num_conv_nodes = 100;
  int filter_size = 3;
  int[] conv_block = int[] {num_conv_layers, num_conv_nodes, filter_size};
  int[][] conv_blocks = int[][] {conv_block, conv_block};

  int num_hidden_1 = 12;
  int num_hidden_2 = 9;
  int num_outputs = 3;
  int[] fully_connected_layer = int[] {num_hidden_1, num_hidden_2, num_outputs};

  ConvolutionalNeuralNetwork cnn = new ConvolutionalNeuralNetwork(input_structure, conv_blocks, fully_connected_layer);

Feeding Data through a Convolutional Neural Network and receiving the Output
----------------------------------------------------------------------------

.. DANGER::
  DO NOT USE!!!
  NOT WORKING!!!

.. code-block:: java

  float[][] red_channel_img = // load image r
  float[][] green_channel_img = // load image g
  float[][] blue_channel_img = // load image b
  float[][][] inputs = new float[][][] {red_channel_img, green_channel_img, blue_channel_img};
  float[] outputs = cnn.feedforward(inputs);
  System.out.println(outputs);
  // gives : [0.5345, 0.4325, 0.6578]

Training a Convolutional Neural Network
---------------------------------------

.. DANGER::
  DO NOT USE!!!
  NOT WORKING!!!

.. code-block:: java

  float[] answers = new float[] {1, 0, 0};
  cnn.train_gradient_descent(inputs, answers);

  System.out.println(cnn.feedforward(inputs));
  // gives : [0.98799, 0.1203, 0.0265]

Setting extra Variables
-----------------------

.. DANGER::
  DO NOT USE!!!
  NOT WORKING!!!

.. code-block:: java

  cnn.set_learning_rate(float);
