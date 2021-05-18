---
title: Speech to text transcription network.
summary: Speech recognition is an interdisciplinary subfield of computer science and computational linguistics that develops methodologies and technologies that enable the recognition and translation of spoken language into text by computers. It is also known as automatic speech recognition (ASR), computer speech recognition or speech to text (STT). This project attempts to create an end-to-end speech transcription network consisting of encoder-decoder structure equipped with attention mechanism. Levenshtein distance was the evaluation metric used to gauge the performance of the network. This architecture obtains an average Levenshtein distance of 24.3.
tags:
- Deep Learning
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
url_code: "https://github.com/SaiPrahladh/Course-Projects/tree/master/Deep_Learning/Speech2text"
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

Face Verification is a problem whereby we are required to confirm if a pair of images depict the same peron's facial features. This task is widely used in modern day applications like the popular 'Face-unlock' feature in smartphones, document id verification etc. This task can essentially split into two steps, face classification followed by face verification. Convolutional Neural Networks are the most popular choice while dealing with such tasks, and usually, these CNNs compute a distance metric between the given pair of images to identify the similarity between the two images.

This task is performed on the 'Labeled Faces in the Wild' dataset which is available here: http://vis-www.cs.umass.edu/lfw/#download

**HOW IS THE VERIFICATION PERFORMED?**

As explained above, the entire verification task can be split into two problems.
1. The classification problem, where we will train our neural network to correctly match the image to its corresponding label.
2. The verification problem, where we will verify the cosine similarity between the embeddings of the images passed through the model. These embeddings are the features extracted from the penultimate layer of the model.

Thus the above two problems are tackled by building a ResNet architecture.

**WHY RESNET?**

ResNets have been known to outperform classical CNNs by allowing us to build deeper networks. The primary shortcomings of classical CNN network like for example VGG-19 network exhibit higher training and validation error as compared to a shallower network. The paper on ResNet https://arxiv.org/pdf/1512.03385.pdf says that "not all systems are similarly easy to optimize.". This could be because of the problem of vanishing gradients, and this is where ResNets have an advantage. ResNets enable the gradients to reach every layer and thus allows us to build deeper networks with better performance.

**EVALUATION:**

Once the classification network is trained, the image embeddings are obtained from the penultimate layer of this network. These embeddings are then obtained for a given pair of images from which the Cosine similarity is calculated. This value is obtained for the entire testing data and the ROC-AUC score for this is calculated. The current architecture accomplishes the face verification task with an ROC-AUC score of 93.45.
