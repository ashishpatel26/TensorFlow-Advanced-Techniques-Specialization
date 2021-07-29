# Object Detection

1. Check all the techniques that can be used to improve the accuracy of detecting objects and encapsulating them entirely within a single bounding box.
    * ***Increase the size of the bounding box until the object fits entirely in it.***
    * ***Use Selective Search technique***
2. Check all that are true for Selective Search.
    * ***It tries to identify larger objects by grouping together initially identified smaller objects***
    * ***Image segmentation is used in this technique***
3. The technique of selecting the best bounding box based on the highest intersection over union (IOU) between the true label and several predicted bounding boxes is called non-maximum ____________ (NMS). 
(Hint: it is a one word answer)
    * ***suppression***
4. Consider the following image, according to the NMS technique which coloured bounding box will be eventually selected as the best bounding box around the football?
    * ***Purple (# 4)***
5. One of the differences between R-CNN and Fast R-CNN is that, Fast R-CNN proposes regions of interest to the input image (generates), whereas in R-CNN regions of interest are expected to be an input
(as opposed to generating them) to the model.
    * ***False***
6. Consider the following code and check all that are true.
    * ***label_id_offsetis an adjustment in case the ‘detection classes’ starting index and actual starting index have an offset between them.***
    * ***min_score_threshis used to leave out object labels and their bounding boxes if their score falls below the set threshold.***
7. The following code initializes a model and restores pre-trained weights, detection_model, using the .config file method 
    * ***False***
8. Which of the following is the correct syntax to print a list of your trainable variables in a model ?
    * ***`for varName in myModel.trainable_variables:    print(varName.name)`***
