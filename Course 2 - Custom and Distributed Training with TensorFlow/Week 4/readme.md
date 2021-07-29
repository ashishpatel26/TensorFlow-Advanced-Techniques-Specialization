# Distributed Strategy

1. Which of the following is true about training your model using data parallelism technique? Check all that are true.
    * The same model architectures are used on different machines, and each machine processes the entire data set.
    * ***Weights from different machines are aggregated and updated into a single model.***
    * All of the data is on 1 master machine, and copies of the data are then distributed to machines having different model architectures based on their capacity of processing the data.
    * ***The full data set is split up and subsets of the data are stored across multiple machines***

2. In TensorFlow version 2, tf.distribute.Strategy class supports _______. Check all that apply.
    * ***Eager Mode***
    * ***Graph Mode***
    
3. Which of the following are true of both MirroredStrategy and TPU Strategy? Check all that are true.
    * Uses multiple machines
    * ***The same model is replicated on each core.***
    * ***Uses a single machine***
    * ***Variables are synchronized (mirrored) across each replica of the model***
    
4. To modify training code to work with Mirrored Strategy, which of the following should we do? Choose all that apply.
    * Put the code that creates, compiles and fits the model inside the scope of “with strategy.scope()”.
    * ***Adjust the batch size to equal the batch size per replica times the number of replicas***
    * Increase the batch size as long as the number is 2^n (e.g. 64, 128, 256 etc).
    * ***Put code that creates the model object inside the scope of “with strategy.scope()”.***

5. To modify training code to work with distributed data, which of the following should we do? Choose all that apply.
    * ***Use strategy.experimental_distribute_dataset to convert training and test sets into distributed datasets.***
    * ***Use strategy.run to run the code that updates the model weights (calculating loss, calculating the gradients, and applying the gradients).***
    * Replace the code that updates the model weights (calculating loss, calculating gradients, and applying the gradients) so that each training step handles all replicas at once.
    * ***Use strategy.reduce to aggregate the losses across the replicas.***
6. To use the TPU strategy, there are some steps that you’ll take before running the training code. Please think about which line of code implements each step and choose the set of code that performs these steps in this order.
    1. Get the TPU address
    2. Find the TPU cluster
    3. Connect to the TPU cluster
    4. Initialize the TPU cluster
    5. Create your TPU strategy
    
    ```python
    tpu_address = 'grpc://' + os.environ['COLAB_TPU_ADDR']
    tf.distribute.cluster_resolver.TPUClusterResolver(tpu_address)
    tf.config.experimental_connect_to_cluster(tpu)
    tf.tpu.experimental.initialize_tpu_system(tpu)
    strategy = tf.distribute.experimental.TPUStrategy(tpu)
    ```
