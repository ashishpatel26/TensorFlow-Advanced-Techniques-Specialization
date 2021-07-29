# Introduction and Concepts of Computer Vision

1. In a Multi-Class classification scenario, your model can identify all the different items and people that are present in a given input image.
    * ***False***
    
2. Which of the following statements correctly describes the difference between object detection and object localization?
    * ***Object localization is where you get a bounding box around the main subject of the image, while in object detection you get a bounding box around all of the objects  
    within an image.***
    
3. What is the method that locates an object(s) by labelling the pixels, where each similar object(s) is assigned to the same class? Type your response here 
    (two words, all lower case).
    * ***_______________________***
    
4. In the context of Transfer Learning, the initial training task where the model learns reusable patterns is called a downstream task.
    * ***False***

5. Check all the scenarios in which Transfer Learning could be beneficial.
    * ***To reduce computation and processing cost***
    * ***When the task you want to perform is a sub-task of an already trained, larger, model.***
    * ***When you don’t have enough data for the task you want to perform, which resembles another same or similar, already trained task.***
    
6. What is the name of the built-in TensorFlow layer-type which you can use to increase the dimensions of a 2D image ?
    * ***UpSampling2D***

7. You have an image of dimensions 48 x 48, and you want to upscale it to 240 x 240 using the built-in TensorFlow layer-type which is used to perform such a task 
(mentioned in Question 6). What will you pass in as size=____?
    * ***(5,5)***
    
8. Consider the following code:
    ```python
    mylayer = tf.keras.applications.resnet.ResNet50(include_top=False , input_shape=(224,224,3) , weights="imagenet")(inputs)
    ```

    * ***It discards the top most layers of ResNet50 when initializing my_layer using ResNet50.***
    
9. What is the name of the technique used in the output dense layer that is used to predict Bounding Boxes ? (Hint: It is a one word answer)
    * ***regression***
10. Check all the statements that are true regarding Intersection Over Union (IoU), with regards to Bounding Boxes.
    * ***IoU is the area of intersection of the two boxes (true and predicted) divided by the total union area of the two boxes.***
    * ***The closer the value of IoU is to 0 the poorer is the prediction of the bounding box.***
