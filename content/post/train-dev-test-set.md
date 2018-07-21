+++
title = "Dividing train/dev/test sets in machine learning"
date = 2018-07-20T22:44:28-04:00
draft = true 

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
descriptive statistics, how to divide our whole dataset into training / test 
sets becomes one of our concern before further analyses. 

The first way we thought was a random sampling --- randomly sampling 20% of
all data then assigning it as a test set, while the remaining 80% would be 
our training set. Soon after, we realized that we're working on "rare event", 
which happens, for example, in only 0.001% of the all records. 
For the rare event, it becomes more probable that 
random sampling can generate training and test sets which include totally 
different portion of event occurance such as 0.0002% vs. 0.003%. 

Then, should be control the portion of event occurance over the two sets?
In this case, we randomly sample the 20% records from the records in which
the rare event was happened and the other records in which it wasn't,
respectively. The merged set of these two 20% samples is assigned as our 
test set, while the remaining ones become our training set. 
It also sounds not perfect because 1) using the information about
our target variable --- occurance rate --- can be problematic, and
2) it can cause the biases in other variables between the two sets
although keeping the occurance rate similar to each other. 

The last method we thought was divide it by time --- if we have records over
ten years, then we keep the records within the last two years as a test set, 
while training the model with the records in the first eight years.
Again, there're pros and cons. A good thing about this approach is 
it sounds clear and natural especially the ultimate goal of our model
is to predict future events. However, in the case where 
some time-related features significantly influence the occurance 
of event, our result algorithm may have a poor accuracy with 
the test set, whose records were made in totally different time period. 

Hence, I decided to survey some tips and advices from existing works 
including machine learning blog articles as well as academic papers. 
Actually some of them are not related to our current concern but I 
put it here if it seems useful in other future cases.

# 2. Approaches / Advices from Existing Works

## (1) When most of training data and upcoming target data have different distribution


# 3. So... What Seems The Best For Our Case?

 

