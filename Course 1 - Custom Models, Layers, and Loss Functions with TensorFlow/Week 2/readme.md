# Custom Loss

1. One of the ways of declaring a loss function is to import its object. Is the following code correct for using a loss object?

    ```python
    import tensorflow.loss import mean_squared_error
    model.compile(loss=mean_squared_error , optimizer = "sgd")
    ```
    * True
    * ***False***

2. It is possible to add parameters to the object call when using the loss object.
    ```python
    model.compile(loss = mean_squared_error(param = value) , optimizer="sgd")
    ```
    * ***True***
    * False

3. You learned that you can do hyperparameter tuning within custom-built loss functions by creating a wrapper function around the loss
   function with hyperparameters defined as its parameter. What is the purpose of creating a wrapper function around the original loss function?
    ```python
    def huber_loss_wrapper(thresold):
        def huber_loss(y_true , y_pred):
            error = y_true - y_pred
            return_type = tf.abs(error) <= thresold
            r1 = 0.5 * tf.square(error)
            r2 = thresold * (tf.abs(error) - (0.5*thresold))
            return tf.where(return_type , r1 , r2)
        return huber_loss
    ```
   
    * No particular reason, it just looks neater this way.
    * That’s one way of doing it. We can also do the same by passing y_true, y_pred and threshold as parameters to the loss function itself.
    * The loss ( model.compile(..., loss = ) ) expects a function that is only a wrapper function to the loss function itself.
    * ***The loss ( model.compile(..., loss = ) ) expects a function with two parameters, y_true and y_pred, so it is not possible to pass
      a 3rd parameter (threshold) to the loss function itself. This can be achieved by creating a wrapper function around the original loss function.***
  
4. One other way of implementing a custom loss function is by creating a class with two function definitions, init and call. Which of the following is correct?
    
    ```python
    class Huber(...):
        .
        .
        .
        def __init__(self , ...):
            super().__init__()
            .
            .
            .
        def call(self , ...):
            .
            .
            .
            return ...
    ```
    
    * We pass the hyperparameter (threshold) , y_true and y_pred to the call function, and the init function returns the call function.
    * We pass y_true and y_pred to the init function, the hyperparameter (threshold) to the call function.
    * We pass the hyperparameter (threshold) , y_true and y_pred to the init function, and the call function returns the init function.
    * ***We pass the hyperparameter (threshold) to the init function, y_true and y_pred to the call function.***
    
5. The formula for the contrastive loss, the function that is used in the siamese network for calculating image similarity, is defined as following:

    `Y * D ^ 2 + (1 - Y) * max(margin - D , 0) ^ 2`
    * ***Y is the tensor of details about image similarities.***
    * Ds are 1 if images are similar, 0 if they are not.
    * ***If the euclidean distance between the pair of images is low then it means the images are similar.***
    * Margin is a constant that we use to enforce a maximum distance between the two images in order to consider them similar or different from one another.
