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

From the picture it is clear that few classes have large number of labeled images and a few of classes have labeled images less than 500 in each class. This gives hint to augmentation, as suggested in video lectures, deep learning network shines with more data.
Actual labels for dataset are provided in signnames.csv file, let’s look how images from few class look like. 
<img src="images/sign.PNG" width="640" lt="sign" />

Data Preprocessing
---
As a first step, with images in dataset from different lighting conditions, it is necessary to normalize them such that they will have good intensity level distribution on histogram.
Before Normalization:<br /> 
<img src="images/before_normalization.PNG" width="480" lt="before_normalization" /> <br /> 

After Contrast Limited Adaptive Histogram Equalization:<br /> 
<img src="images/hist_equalized.PNG" width="480" lt="hist_equalized" /><br /> 
Contrast Limited Adaptive Histogram Equalization(CLAHE) method is pretty promising and provides great normalization in different lighting conditions.Since we are interested in brightness factor, CLAHE is applied to only Y channel by converting image to YUV.

Augmentation
---
After exploring data-set and trying NN without data augmentation, to make model more reliable and predictable, data augmentation is implemented. Few of classes don't have enough number of images and it is necessary to produce images using this technique. Images from ImageDataGenerator from Keras is a convenient option to augment data with variation in following parameters:
1. Angle of rotation
2. Shift in height
3. Shift in width
4. Shear range
5. Zoom range

Per class 4000 images are augmented..! Now, the data set with these variation and number of images per class looks great..!

Model Architecture
---
