# Custom Training

1. What are the names of the two functions which are part of the built in solution for training a model in TensorFlow and Keras?
    * model.configure() and model.map()
    * model.build() and model.train()
    * model.structure() and model.compute()
    * ***model.compile() and model.fit()***
    
2. With regards to the loss function, the derivative that gives you the gradient points away from the minimum loss value, but you can still use it for direction by adding the
   gradient value to your weight, instead of subtracting from it.
    * True
    * ***False***

3. During training one of the parameters which you have to set is the Learning Rate.Which of the following are true statement(s) for Learning Rate? Check all that are true.

    * ***It defines how big a step to take in the given direction during the update step.***
    * A larger learning rate (0.1 as opposed to 0.0001) leads to a bigger update and reaches the minimum loss with fewer iterations, so a larger learning rate is better.
    * ***With a smaller learning rate (0.0001 as opposed to 0.1), the update to the weight is smaller, and will take more iterations to minimize the loss.***
    * It defines the direction in which we should jump while finding the minimum loss value
    
4. For creating your own custom training loop, arrange the following steps in the correct order for each training batch:
    1. Accumulate accuracy metric
    1. Calculate loss
    1. Calculate gradients of loss with respect to the model trainable weights
    1. Calculate logits
    1. Apply gradients on model using optimizer

        * 2, 1, 3, 4, 5
        * 2, 4, 5, 3, 1
        * 4, 1, 5, 2, 3
        * ***4, 2, 3, 5, 1***

5. Consider the code below used in custom batch training:
    Which of the following lines of code performs optimization (should appear where you see the comment “# code for optimizing” ?
    * optimizer.apply_gradients(gradients, model.trainable_weights)
    * optimizer = apply_gradients(zip(gradients, model.trainable_weights))
    * ***optimizer.apply_gradients(zip(gradients, model.trainable_weights))***
    * optimizer = apply_gradients(gradients, model.trainable_weights)
    
6. Metrics in Keras can only be called as functions and not instantiated as Classes.
    * True
    * ***False***
    
7. Which of the following is the correct syntax for querying the current value of metric for display ?
    * ***metric.result***
    * metric.get_state
    * metric.get_result
    * metric.state
