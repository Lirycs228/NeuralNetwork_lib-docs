******************
Genetic Perceptron
******************

Initializing a Genetic Perceptron
---------------------------------
.. code-block:: java

  int num_inputs = 2;
  int num_outputs = 1;
  int population_size = 100;
  int random_per_generation = 10;
  Genetic_Perceptron gpnn = new Genetic_Perceptron(population_size, random_per_generation, num_inputs, num_outputs);

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
    gpnn.evolve_best(current_fitness);
  }

  System.out.println(gpnn.overall_best.feedforward(inputs));
  // gives : [0.98799]

Setting extra Variables
-----------------------
.. code-block:: java

  gpnn.set_mutation_rate(float);
  gpnn.set_evolution_rate(float);
  gpnn.set_offspring_mutation_rate(float);
