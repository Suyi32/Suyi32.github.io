---
layout: post
title: First post!
image: /img/hello_world.jpeg
---

In this post, I will go through several text-to-SQL models.

#### SEQ2SEQ [Paper](https://www.aclweb.org/anthology/P17-1089.pdf)
* feedback-based learning approach is adopted to correct the enlarge the dataset and improve the model quality
* encoder-decoder model with global attention, where the anonymized utterance (see Section 4.2) is encoded using a 
bidirectional LSTM network, then decoded to directly predict SQL query tokens
* Entity Anonymization is used to process the utterance: handle entities in the utterances and SQL by 
replacing them with their types

#### SEQ2SQL
* Encoder-decoder model: The encoder encodes input using two-layer bidirectional LSTM, the decoder network uses a two layer, unidirectional LSTM.

