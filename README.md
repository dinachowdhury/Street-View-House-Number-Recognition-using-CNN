# Street-View-House-Number-Recognition-using-CNN
I try to explore a model build by the convolutional neural network (CNN), a popular and modern technique for street view house number recognition. And got 92% accuracy with a small loss of data.


The dataset I am considering for this project is street view house numbers dataset taken from http://ufldl.stanford.edu/housenumbers/. The SVHN dataset has more than 600,000 labeled characters and the images are in .png format. After extract the dataset I resize all images in 32x32 pixels with three color channels. There are 10 classes, 1 for each digit. Digit '1' is label as 1, '9' is label as 9 and '0' is label as 10. The dataset is divided into three subgroups: train set, test set, and extra set. The extra set is the largest subset contains almost 531,131 images. Correspondingly, train dataset has 73,252 and test data set has 26,032 images.
