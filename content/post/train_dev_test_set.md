+++
title = "Dividing train/dev/test sets in machine learning"
date = 2018-07-27T22:44:28-04:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Jaehyuk Park"]

# Tags and categories
# For example, use `tags = []` for no tags, or the form 
# `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["machine learning", "training", "know-how", "deep learning"]
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its 
# filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true
+++

# 1. Why Does It Matter? Or When Does It Matter?

In one of my current projects, our team try to generate a machine learning model
to predict whether some rare event would be happened or not.
Since we don't want to use any information from our test set, even in overall 
descriptive statistics, how to divide our whole dataset into train/dev/test 
sets becomes one of our concern before further analyses. 
Training set is the data to be used for training our model, 
and dev set is the data to compare and select among multiple models
(having different hyperparameters, layers, evaluation functions, etc.),
while test set is to finally test the accuarcy of our selected model. 

Hence, I decided to survey some tips and advices from existing works 
such as machine learning blog articles and academic papers. 
Although some of them are not related to our current concern, I 
put it here if it seems useful in other future cases.

# 2. Advices from blogs and online lectures

## (1) Sequential splitting vs. Random splitting
[Amazon Machine Learning Developer Guide](https://docs.aws.amazon.com/machine-learning/latest/dg/splitting-types.html)
seems supporting the sequential splitting in our case. 
Similar to our prediction problem, it introduces prediction during certain
time range based on previous time range as a representative 
example for sequential splitting.

## (2) Proportion of train/dev/test sets
What proportions of dataset are generally assigned for dev and test sets?
According to the online lecture "[Train/Dev/ Test sets](https://www.coursera.org/lecture/deep-neural-network/train-dev-test-sets-cxG1s)" by 
Andrew Ng, it depends on the size of dataset.
For example, if the total number of data is about 100, 1000, or 10,000, 
dividing train/dev/test into 60%/20%/20% is more general. 
However, if your dataset including more than about a million records,
assigning 10,000 records for each of dev and test sets would be okay
to obtain a reliable accuracy test result.

Our dataset has far more than a million records so assigning 10,000 to 
100,000 records during the last time period would be okay according to
the lecture. However, if I consider the number of events in the dataset, 
because it's a rare event, 10,000 records would only
include 10 to 100 events which makes me not sure whether this is enough
size to measure the accuracy correctly.

## (3) When most of training data and upcoming target data have different distribution
The Medium article, 
[Mismatched training and dev sets in Deep Learning](https://medium.com/@anilvedala/mismatched-training-and-dev-sets-in-deep-learning-5c84b2b6d207),
deal with the situation when the distribution of train set would be different 
from that of test set or future target data. For instance, to develop a deep learning
algorithm that classifies cat pictures from non-cat pictures in mobile phone,
developer collected a large amount of high-quality of pictures and 
comparatively small number of low-quality mobile pictures, which is closer
to the target data.

In that situation, the article recommends dividing the small mobile picture data 
into the three sets of dataset --- train, dev (using in validation process), 
and test sets --- with the ratio about 2:1:1. Then, by comparing the accuracies 
on four sets of data --- train, train+dev, dev, and test, 
we can diagnose the model whether it's overfitted or underfitted. 
Additionally, the lecture "[Train/Dev/Test sets](https://www.coursera.org/lecture/deep-neural-network/train-dev-test-sets-cxG1s)" emphasizes to make sure
that dev set and test set are from a same distribution.

The dataset of our project doesn't have the different distribution issue,
so this section is more for the future.  

# 3. Examples from previous researches

## (1) 25% - 25% - 50% 
In a [recent research](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5176360/)
on the prediction of short-term mortality, 
dataset is generated through random sampling of 20,000 patients for
each type of target diseases, from the national samples including 0.8 to 
2.7 million people depending on disease. Then they split equally into
train and test sets, that is, 10,000 for each set. The train set is again
splited into train and dev sets for parameter optimization, that is, 
5,000 samples for each.  

Similar to our case, the target class of the prediction is a rare cases
(10% or under), they applied both oversampling - creating duplicates of 
the minority class - and undersampling - random sampling of non-events
only for train set and validate it with original (non-event biased) dev set.

 
 


