# Functional API

1. Which of these steps are needed for building a model with the Functional API? (Select three from the list below)
    1. Explicitly define an input layer to the model.
    2. Define the input layer of the model using any Keras layer class (e.g., Flatten(), Dense(), ...)
    3. Define disconnected intermediate layers of the model.
    4. Connect each layer using python functional syntax.
    5. Define the model using the input and output layers.
    6. Define the model using only the output layer(s).

        * 1, 3, 5
        * **1, 4, 5(Answer)**
        * 1, 4, 6
        * 2, 4, 5
    
2. Is the following code correct for building a model with the Sequential API?
    ```python
    def get_model():
        input = Input(shape=(28,28))
        x = Flatten()(x)
        x = Dense(128)(x)
        x = Dense(10 , activation=softmax)(x)
        model = Model(inputs = input , outputs = x)
        
        return model
    ```
    * ***False***
    * True

3. Only a single input layer can be defined for a functional model.
    * True
    * ***False***
    
4. What are Branch Models ?
    * A model architecture where you can split the model into different paths, and cannot merge them later.
    * A model architecture with linear stack of layers.
    * ***A model architecture with non-linear topology, shared layers, and even multiple inputs or outputs.***
    * A model architecture with a single recurring path.
    
5. One of the advantages of the Functional API is the option to build branched models with multiple outputs, where different loss functions can be implemented for each output.
    * False
    * ***True***

6. A siamese network architecture has:
    * 1 input, 2 outputs
    * ***2 inputs, 1 output***
    * 1 input, 1 output
    * 2 inputs, 2 outputs
    
7. What is the output of each twin network inside a Siamese Network architecture?
    * Binary value, 1 or 0
    * A softmax probability
    * A number
    * ***An output vector***

8. What is the purpose of using a custom contrastive loss function for a siamese model?
    * A custom built function is required because it is not possible to use a built-in loss function with the Lambda layer.
    * A custom loss function is required for using the RMSprop() optimizer.
    * ***It is a custom built function that can calculate the loss on similarity comparison between two items.***
    * As a custom built function, it provides better results and it is faster to run.
