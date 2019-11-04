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

#### SEQ2SQL [Paper](https://arxiv.org/abs/1709.00103)
* Encoder-decoder model with Pointer Network: The encoder encodes input using two-layer bidirectional LSTM, the decoder network uses a two layer, unidirectional LSTM.
* Apply reinforcement learning to deal with the sequence problem in WHERE clause. For example, for the question "which males are older than 18", the queries " SELECT name FROM insurance WHERE age > 18 AND gender = "male" " and " SELECT name FROM insurance WHERE gender = "male" AND age > 18 " both obtain the correct execution result despite not having exact string match.

#### SQLNet [Paper](https://arxiv.org/abs/1711.04436)
* **A sketch-based approach** where the sketch contains **a dependency graph** so that one prediction can be done by taking into consideration only the previous predictions that it depends on. The sketch aligns naturally to the syntactical structure of a SQL query.
* SQLNet is then used to predict the content for each slot in the sketch.
* The design of SQLNet introduce two constrcutions: **Sequance-to-Set** and **column attention**.
* Sequence-to-Set is designed to predict an unordered set of constraints instead of an ordered sequence.
* Column attention is designed to capture the dependency relationship defined in the sketch when predicting.
