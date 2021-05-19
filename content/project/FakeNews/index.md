---
title: Fake News Detection.
summary: Speech recognition is an interdisciplinary subfield of computer science and computational linguistics that develops methodologies and technologies that enable the recognition and translation of spoken language into text by computers. It is also known as automatic speech recognition (ASR), computer speech recognition or speech to text (STT). This project attempts to create an end-to-end speech transcription network consisting of encoder-decoder structure equipped with attention mechanism. Levenshtein distance was the evaluation metric used to gauge the performance of the network. This architecture obtains an average Levenshtein distance of 24.3.
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

Speech recognition is an interdisciplinary subfield of computer science and computational linguistics that develops methodologies and technologies that enable the recognition and translation of spoken language into text by computers. It is also known as automatic speech recognition (ASR), computer speech recognition or speech to text (STT). The aim of this project is to construct an end to end speech detection system using bidirectional lstms as the cell block, and build an encoder-decoder network to construct the final output with an attention mechanism. This project is inspired by the research paper 'Listen, Attend and Spell' (LAS):  https://arxiv.org/abs/1508.01211

**HOW IS THE TRANSCRIPTION PERFORMED?**

The above architecture is a character level model whereby the model always predicts the next character. The advantage of using a character level model is that the discrete space is much smaller owing to the limited number of unique characters possible in the English Language. Another advantage is that character-level models can spontaneously generate unusual words with some (small) probability. The architecture is composed of two main parts, the Listener and the Speller.
1. **Listener:** Listener is the Encoder, which consists of a Pyramidal Bi-LSTM Network structure that takes in the given utterances and
compresses it to produce high-level representations for the Speller network.
2. **Speller:** Speller is the Decoder, which takes in the high-level feature output from the Listener network and uses it to compute a
probability distribution over sequences of characters using the attention mechanism.
3. **Attention:** Attention intuitively can be understood as trying to learn a mapping from a word vector to some areas of
the utterance map. The Listener produces a high-level representation of the given utterance and the Speller
uses parts of the representation (produced from the Listener) to predict the next word in the sequence.

The above architecture is then augmented using different tricks which can help us achieve optimal performance. Few such tricks are listed below:
1. **Variable Teacher Forcing:** Teacher forcing is a strategy for training recurrent neural networks that uses ground truth as input, 
instead of model output from a prior time step as an input. The network employs a variable teacher forcing rate that reduces as the number of epochs increase.
2. **Weight Tying:** Weight-tying is where you have a language model and use the same weight matrix for the input-to-embedding layer (the input embedding) 
and the hidden-to-softmax layer (the output embedding). The idea is that these two matrices contain essentially the same information,
each having a row per word in the vocabulary.

**EVALUATION:**
The evaluation metric chosen is the Levenshtein distance between the generated sequence and the target sequence. A lower Levenshtein distance indicates a better model.
The architecture described above on the test dataset generated an average Levenshtein score of 24.3.

