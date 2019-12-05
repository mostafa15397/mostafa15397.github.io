---
title: "Markdown Extra Components"
layout: post
date: 2016-02-24 22:48
image: /assets/images/markdown.jpg
headerImage: false
tag:
- markdown
- components
- extra
category: blog
author: jamesfoster
description: Markdown summary with different options
---

##  **``Thyroid``** **``Diseases``**

## ``introduction``

1-*Background* *and* *motivation*

Recently, thyroid diseases are more and more spread
worldwide. In Romania, for example, one of eight women
suffers from hypothyroidism, hyperthyroidism or thyroid
cancer.

our project is prediction  about  Thyroid Diseases and it classification: predict
a patient is normal (1) or
suffers from hyperthyroidism (2) or hypothyroidism (3).
by using ML by three methodes (decision tree , naive ,K-NN ) and our data set is  [here ](https://sci2s.ugr.es/keel/dataset/data/classification/newthyroid.zip)


 ## **``Pre-processing``**

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
