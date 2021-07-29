# [Custom and Distributed Training with TensorFlow](https://www.coursera.org/learn/custom-distributed-training-with-tensorflow/home/welcome)

---

Welcome to Custom and Distributed Training with TensorFlow! You’re joining thousands of learners currently enrolled in the course.

I'm excited to have you in the class and look forward to your contributions to the learning community.

To begin, I recommend taking a few minutes to explore the course site. Review the material we’ll cover each week, and preview the assignments 

you’ll need to complete to pass the course. Click Discussions to see forums where you can discuss the course material with fellow students taking the class.

If you have questions about course content, please post them in the forums to get help from others in the course community. For technical problems with the

Coursera platform, visit the Learner Help Center.

Good luck as you get started, and I hope you enjoy the course!

## Content

### 1. Week1 -> Differentiation and Gradients
  * Tensor Basics
    * ```import tensorflow as tf ```
    * ```tf.Variable(initial_values , shape , dtype ) ```
    * ```tf.constant(initial_values , shape , dtype ) ```
    * Different tensors operation : ```tf.multiply() , tf.add() , tf.reduce_sum() , tf.assigned_sum()```
  * Working with Tensors in Eager Mode
  ```python
  def LossFunc(y_pred , y_true):
    return tf.abs(y_pred - y_true)
  def fit_data(x , y):
    with tf.GradientTape(persistent=True) as tape:
        pred = w * x + b
        loss = LossFunc(pred , y)
    w_grad = tape.gradient(loss , w)
    b_grad = tape.gradient(loss , b)

    w.assign_sub(w_grad * learning_rate)
    b.assign_sub(b_grad * learning_rate)

  for _ in range(500):
    fit_data(xs , ys)
  ```
  * Gradient Tape
  ```python
  x = tf.Variable(3.0)
  with tf.GradientTape() as t1:
      with tf.GradientTape() as t2:
          y = x * x * x
      dy_dx = t2.gradient(y , x)
  d2y_dx2 = t1.gradient(dy_dx , x)

  print("dy_dx   : ",dy_dx)
  print("d2y_dx2 : ",d2y_dx2)
  ```
 
### 2. Week2 -> Custom Trainig
 * Custom Training Loops
 <p align="center"><img src="https://user-images.githubusercontent.com/50513363/99905776-ef1b7e00-2cf8-11eb-99a9-8df60b5cd847.png" /></p>
 
 * Custom Training with TensorFlow Datasets
 <p align="center"><img src="https://user-images.githubusercontent.com/50513363/99905784-fe9ac700-2cf8-11eb-9cf5-412720f8818d.png" /></p>

### 3. Week3 -> Graph Model

### 4. Week4 -> Distributed Training
