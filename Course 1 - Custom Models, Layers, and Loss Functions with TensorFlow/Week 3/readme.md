# Custom Layers

1. Lambda layer allows to execute an arbitrary function only within a Sequential API model.

  * True
  * ***False***
  
2. Which one of the following is the correct syntax for mapping an increment of 2 to the value of “x” using a Lambda layer? (tf = Tensorflow)
  * ***tf.keras.layers.Lambda(lambda x: tf.math.add(x, 2.0))***
  * tf.keras.Lambda(x: tf.math.add(x, 2.0))
  * tf.keras.layers.Lambda(x: tf.math.add(x, 2.0))
  * tf.keras.layers(lambda x: tf.math.add(x, 2.0))
  
3. One drawback of Lambda layers is that you cannot call a custom built function from within them.
  * True
  * ***False***
  
4. A Layer is defined by having “States” and “Computation”. Consider the following code and check all that are true:
  * def call(self, inputs): performs the computation and is called when the Class is instantiated.
  * After training, this class will return a w*X + b computation, where X is the input, w is the weight/kernel tensor with trained values,
and b is the bias tensor with trained values.
  * ***You use def build(self, input_shape): to create the state of the layers and specify local input states.***
  * In def __init__(self, units=32): you use the super keyword to initialize all of the custom layer attributes

5. Consider the following code snippet.

  *
  ```python
  def build(self, units=32, activation=None):

  .

  .

  self.activation = activation

  def call(self, inputs):

  return self.activation(tf.matmul(inputs, self.w) + self.b)
  ```

  ```python
  def __init__(self, units=32):

  .

  .

  self.activation = tf.keras.activations.get(activation)

  def call(self, inputs):

  return self.activation(tf.matmul(inputs, self.w) + self.b)
  ```

  ```python
  def build(self, input_shape):

  .

  .

  self.activation = tf.keras.activations.get(activation)

  def call(self, inputs):

  return self.activation(tf.matmul(inputs, self.w) + self.b)
  ```
  * Ans :=>>>>>
  ```python
  def __init__(self, units=32, activation=None):

  .

  .

  self.activation = tf.keras.activations.get(activation)

  def call(self, inputs):

  return self.activation(tf.matmul(inputs, self.w) + self.b)
  ```

