## Project: Build a Traffic Sign Recognition Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---
In this project, you will use what you've learned about deep neural networks and convolutional neural networks to classify traffic signs. You will train and validate a model so it can classify traffic sign images using the [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). After the model is trained, you will then try out your model on images of German traffic signs that you find on the web.

Solution
---
We first start with basic analysis of training data set. There are a little less than 52k images, split into training, validation and test sets.

Our traffic signs belong to 43 different classes and image below shows the distribution of our training set:
<img src="images/visualize_data.png" width="640" lt="visualize_data" />

The next thing we needed to do was to plot some random images from dataset just for visualization. Below image shows few of those, 
<img src="images/sign.PNG" width="640" lt="sign" />


