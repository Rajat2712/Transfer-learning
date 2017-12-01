# What is Transfer Learning?

![13elx7-dtqwyqs0izn9fng](https://user-images.githubusercontent.com/23000971/33496406-1a3c819a-d6f0-11e7-85be-8b029d9644ae.png)

The ability of a system to recognize and apply knowledge and skills learned in previous tasks to novel tasks (or new domains).

![c8wh47frr3658meccaupra](https://user-images.githubusercontent.com/23000971/33496483-6839f864-d6f0-11e7-8b61-7f5091228bed.png)

# Keras Pre-trained Models

Keras - High-level neural networks API, written in Python.
Modular, minimalistic and easy to use.
Runs on top of Theano, Tensorflow, CNTK.

## Keras applications (Model Zoo) contains following pre-trained models:
Xception
VGG16
VGG19
ResNet50
InceptionV3

# Why to use pre-trained models ?
It is relatively rare to have a dataset of sufficient size. 
Instead, it is common to use pretrained ConvNet which was trained on a very large dataset (e.g. ImageNet, which contains 1.2 million images with 1000 categories), and then use the ConvNet either as an:
Initialization or 
A fixed feature extractor for the task of interest.
And training of model from scratch requires more time then training the dense layers of pre-trained models.

# Steps for using pre-trained models:-

## 1. Feature extractor :
Remove the Fully Connected (Bottleneck layer) from pre-trained VGG16 model.
Run images from Dataset through this truncated network to produce  image vectors.
Use these vectors to train another classifier to predict the labels in training set.
Prediction is made with second classifier against image vector.
![f6a9qsd1qlkcoe-05hid_w](https://user-images.githubusercontent.com/23000971/33496717-517177e6-d6f1-11e7-8b4d-3a67255426ff.png)

## 2. Fine Tuning :
We train the model partially.
Remove the Fully Connected (Bottleneck layer) from pre-trained VGG16 model.
Make weights of all convolution blocks non-trainable(frozen)except the last few convolutional layers.
Attach our own classifier to the bottom.
Train the resulting classifier with very low learning rate.
Computationally more expensive but still cheaper than training network from scratch.
More robust model.
![f6a9qsd1qlkcoe-05hid_w](https://user-images.githubusercontent.com/23000971/33496759-7fe0bdee-d6f1-11e7-9f8b-057bfdb2f3a3.png)

# Results

## Input
![iyg5vdsptusn4bydauzthq](https://user-images.githubusercontent.com/23000971/33496861-cfc5e38e-d6f1-11e7-9bb4-305d2832e7ee.png)

## Output
![bottleneck_last_layer_viz](https://user-images.githubusercontent.com/23000971/33496946-24a97cc6-d6f2-11e7-9280-8bbf4a56b8b7.png)
