# Digit Classifier on MindSpore

Implemented a basic digit classifier based on the MNIST dataset. Used the powerful MindSpore framework for training the model. This is an example from the [getting started guide](https://www.mindspore.cn/tutorial/training/en/master/quick_start/quick_start.html) from MindSpore.

### Model Accuracy 

![image](https://github.com/OSSome01/MindSpore_digitClassifier/blob/master/images/model_accuracy.PNG)

### Predictions

![image](https://github.com/OSSome01/MindSpore_digitClassifier/blob/master/images/predictions.PNG)

### Errors Encountered

When trying to run the quick start example on google colab I came accross a error. The problem encounter is due the the number of cores in colab. Colab has 2 CPU cores whereas by deafult the MnistDataset() method considers 8 cores. Even when I changed the <mark>num_parallel_workers</mark> argument in the MnistDataset() method to 2 I still got the error.

![image](https://github.com/OSSome01/MindSpore_digitClassifier/blob/master/images/error.PNG)

I was able to solve this error by  adding this line to the code <mark> ds.config.set_num_parallel_workers(1) </mark>. I had to set the <mark>num_parallel_workers</mark> to 1 by setting the global config. This error has also been discussed in this [issue](https://github.com/mindspore-ai/mindspore/issues/134) on Github