---
title: Fake News Detection.
summary: Fake news is rampant in today's date and verifying the authenticity of a news article is paramount. The aim of this project is to train various machine learning models to classify a given news article as authentic or fake. This task falls under the domain of Natural Language processing. The machine learning models explored in this project are Naive Bayes classifier, Random forest classifier and Logistic Regression.
tags:
- Machine Learning
date: "2016-04-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo from the LFW dataset.
  focal_point: Smart

links:
# - icon: twitter
#  icon_pack: fab
#  name: Follow
#  url: https://twitter.com/georgecushen
url_code: "https://github.com/SaiPrahladh/FakeNewsClassification"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example
---
**MOTIVATION:**

Content moderation has been a challenging task for major corporations and news agencies as the authenticity of news is of paramount importance. With that consideration in mind, we wanted to apply machine learning tools and algorithms to tackle the issue of fake news, by observing recurring patterns that can be found in articles which can be deemed fake. These patterns are then compared with authentic news to determine the criteria used to classify an article as fake or authentic.

**HOW IS THE CLASSIFICATION PERFORMED?**

The first stage of the ML pipeline is to collect news articles over the past year which are deemed to be true from reputed sources such as the New York Times and the Guardian.
The next step is to collect news articles which are preclassified as fake. For this purpose, we take help of a fake news dataset hosted by the following Kaggle competition: https://www.kaggle.com/c/fake-news/data. The above two datasets are merged into a mixed dataset consisting of a shuffled dataset. The machine learning algorithms such as Logistic Regression, Naive Bayes and a Random Forest were applied on this mixed dataset to see which would be more suitable for our classification task. 

**EVALUATION:**
The evaluation metric chosen was classification accuracy. The three algorithms employed exhibited the following test accuracy on the mixed dataset.
1. Naive Bayes: 79.83%
2. Random Forest: 88.88%
3. Logistic Regression: 88.68%

Check out the documents attached in the GitHub repository for visualizations and a deeper insight into the results!

