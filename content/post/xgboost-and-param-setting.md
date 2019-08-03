+++
title = "Xgboost and Parameter Setting"
date = 2018-08-01T20:53:37-04:00
draft = true

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Jaehyuk Park"]

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ['machine learning', 'xgboost']
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++

# 1. Introduction

# 2. XGBoost

- [Original Paper](https://dl.acm.org/citation.cfm?id=2939785)

- [Tutorial](https://xgboost.readthedocs.io/en/latest/tutorials/index.html)

- [Python package page](https://xgboost.readthedocs.io/en/latest/python/index.html)

- [Example code](https://machinelearningmastery.com/develop-first-xgboost-model-python-scikit-learn/)

# 3. Class imbalance in XGBoost

- [Imbalanced Data XGBoost Tunning](https://www.kaggle.com/saxinou/imbalanced-data-xgboost-tunning)

- There is a parameter in XGBoost, named `scale_pos_weight`, to adjust the balance of positive and negative weights, especially for unbalanced classes. the [XGBoost library page](http://xgboost.readthedocs.io/en/latest/parameter.html) said typical value to consider is the number of negative cases over the number of positive cases. 

