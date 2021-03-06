---
title: "ML for Thyroid Diseases "
layout: post
date: 2019-12-5 20:08
image: /assets/images/markdown.jpg1
headerImage: false
tag:
- markdown

category: blog
author: jamesfoster
description: Markdown summary with different options
---

#  Thyroid Diseases

## introduction

Machine learning algorithms :
The most common learning algorithms are supervised and unsupervised
Supervised learning that we are going to teach the computer how to do something
Unsupervised learning that we are going to let it learn by itself

1-*Background* *and* *motivation*

Recently, thyroid diseases are more and more spread
worldwide. In Romania, for example, one of eight women
suffers from hypothyroidism, hyperthyroidism or thyroid
cancer.

our project is prediction  about  Thyroid Diseases and it classification: predict
a patient is normal (1) or
suffers from hyperthyroidism (2) or hypothyroidism (3).
by using ML by three methodes (decision tree , naive ,K-NN ) and our data set is  [here ](https://sci2s.ugr.es/keel/dataset/data/classification/newthyroid.zip)

##  Pre-processing

we faced a problem
 that our data have 5 feature which all don't have the same range so  we used Feature normalization to make them have the same range

before normalization

<img src="https://mostafa15397.github.io/assets/images/befor.png" width="" height="" />


after normalization

<img src="https://mostafa15397.github.io/assets/images/after.png" width="" height="" />

we took dataset randomly not to be biased

```
{
  library(caTools)
set.seed(123)
split = sample.split(dateset$Class, SplitRatio = 0.8)
training_set = subset(dateset , split == TRUE)
test_set = subset(dateset , split == FALSE)
}
```  
we make visualize dataset feature by feature against  class
Box and whisker plots for each attribute
![Box and whisker plots for each attribute](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/assets/images/Box%20and%20whisker%20plots%20for%20each%20attribute.jpg?raw=true)

## Naive Bayes

Call: naive_bayes.formula(formula = Class ~ ., data = training_set)

---------------------------------------------------------------------------------------------------

Laplace smoothing: 0

---------------------------------------------------------------------------------------------------

A priori probabilities:

       1         2         3
0.6976744 0.1627907 0.1395349

---------------------------------------------------------------------------------------------------

Tables:

---------------------------------------------------------------------------------------------------
::: T3r (Gaussian)
---------------------------------------------------------------------------------------------------

T3r             1          2          3
 mean  0.1089921 -1.2493848  0.9126548
 sd    0.6337014  1.2185633  0.8845801

---------------------------------------------------------------------------------------------------
::: Thyrox (Gaussian)
---------------------------------------------------------------------------------------------------

Thyrox          1          2          3
 mean -0.1252081  1.6696129 -1.3218410
 sd    0.4247462  0.9424178  0.4001422

---------------------------------------------------------------------------------------------------
::: Triiodothyronine (Gaussian)
---------------------------------------------------------------------------------------------------

Triiodothyronine          1          2          3
           mean -0.2016876  1.5151860 -0.7592789
           sd    0.3318362  1.6278951  0.3813936

---------------------------------------------------------------------------------------------------
::: Thyroidstimulating (Gaussian)
---------------------------------------------------------------------------------------------------

Thyroidstimulating           1           2           3
             mean -0.26849191 -0.34055218  1.73977040
             sd    0.09949892  0.08119780  1.92356990

---------------------------------------------------------------------------------------------------
::: TSH (Gaussian)
---------------------------------------------------------------------------------------------------

TSH              1           2           3
 mean -0.20685042 -0.52342939  1.64491971
 sd    0.22302501  0.03347533  1.94831655

---------------------------------------------------------------------------------------------------

plotting naïve bias

![naive bias](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/assets/images/ploting%20naive%20bias.png?raw=true)


Confusion Matrix and Statistics

               y_pred
test_set_labels  1  2  3
              1 27  0  1
              2  0 11  0
              3  0  0  4

Overall Statistics

               Accuracy : 0.9767          
                 95% CI : (0.8771, 0.9994)
    No Information Rate : 0.6279          
    P-Value [Acc > NIR] : 5.401e-08       

                  Kappa : 0.9548          

 Mcnemar's Test P-Value : NA              

Statistics by Class:

![Cv](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/Capture.PNG?raw=true)


![plot that explains the relation between different features in class dataset](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/assets/images/plot%20that%20explains%20the%20relation%20between%20different%20features%20in%20class%20dataset.jpg?raw=true)

## KNN
 KNN is a Supervised Learning algorithm that uses labeled input data set to predict the output of the data points.
    It is one of the most simple Machine learning algorithms and it can be easily implemented for a varied set of problems.
    It is mainly based on feature similarity. KNN checks how similar a data point is to its neighbor and classifies the data point into the class it is most similar to.

![Error in prediction at k = 3 ](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/assets/images/78956474_480467589246964_4235545560171413504_n.jpg?raw=true)

## decision tree
in this method we classifier classes as tree first algorism as if is normal or not
if normal it is class 1 if not normal ask if hyperthyroidism class (2)  , or hypothyroidism (3)
![decision tree plot](https://github.com/mostafa15397/mostafa15397.github.io/blob/master/assets/images/desetion%20tree.jpg?raw=true)

and we get accuracy= 90%  after applying cross validation 
