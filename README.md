# Deep_Learning_MNIST_First

This project was a first attempt at adapting a homebrew Neural Network to be trained on the MNIST dataset.

Unfortunately there were a number of key issues with this attempt:
1. The first was that the implementation of the network is disgusting. While it is technically correct, it would have been far easier to create a class based system with a "Layer" class, not disimilar to the layer classes in PyTorch or Keras. However, the main issue here comes from the efficiency of the code. As it is a homebrew network, it is NEVER going to run as fast as the Torch or TF versions compiled into C.
2. The second was with my method of saving/loading data. I manually wrote the values to a csv file and would then read them back. This is just horrible in terms of time taken both for the saving/loading of data, and was not written as a class method to a model, but as a main section of code in __main__. The far easier approach is using the inbulit model.save('/path') for keras or torch.save(model.state_dict(), '/path') for pytorch; these will both be more efficient in every regard, and will look much nicer in code.
3. It didn't work. Whether this was because I didn't give it enough time to train (most likely due to the highly inefficient homebrew nature of the network), or because the starting weights/biases were random, or because the loss function used was wrong (categorical cross-entropy would likely work far better for MNIST than Mean squared error). 

All this said, This project is put to rest now and has been replaced by my far more interesting and advanced project DeepLearningGo
