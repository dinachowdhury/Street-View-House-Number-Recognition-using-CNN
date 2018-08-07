# Street-View-House-Number-Recognition-using-CNN
I try to explore a model build by the convolutional neural network (CNN), a popular and modern technique for street view house number recognition. And got 92% accuracy with a small loss of data.


The dataset I am considering for this project is street view house numbers dataset taken from http://ufldl.stanford.edu/housenumbers/. The SVHN dataset has more than 600,000 labeled characters and the images are in .png format. After extract the dataset I resize all images in 32x32 pixels with three color channels. There are 10 classes, 1 for each digit. Digit '1' is label as 1, '9' is label as 9 and '0' is label as 10. The dataset is divided into three subgroups: train set, test set, and extra set. The extra set is the largest subset contains almost 531,131 images. Correspondingly, train dataset has 73,252 and test data set has 26,032 images.


I perform my analysis only using the train and test dataset due to limited technical resources. By preprocessing the data from the original SVHN dataset a pickle file is created which being used in my experiment. For the implementation, I randomly shuffle valid dataset and then used the pickle file and train a 7-layer Convoluted Neural Network. 


At the very beginning of the experiment, first convolution layer has 16 feature maps with 5x5 filters, and originate 28x28x16 output. A few ReLU layers are also added after each convolution layer to add more non-linearity to the decision-making process. After first sub-sampling the output size decrease in 14x14x10. The second convolution has 512 feature maps with 5x5 filters and produces 10x10x32 output. By applying sub-sampling second time get the output size 5x5x32. Finally, the third convolution has 2048 feature maps with same filter size. It is mentionable that the stride size =1 in my experiment along with zero padding. During my experiment, I use dropout technique to reduce the overfitting. Finally, SoftMax regression layer is used to get the final output. 


Weights are initialized randomly using Xavier initialization which keeps the weights in the right range. It automatically scales the initialization based on the number of output and input neurons. After model buildup, start train the network and log the accuracy, loss and validation accuracy for every 500 steps. Once the process is done then get the test set accuracy. To minimize the loss, Adagrad Optimizer used. After reach in a suitable accuracy level stop train the network and save the hyperparameters in a checkpoint file. When we need to perform the detection, the program will load the checkpoint file without train the model again. 
