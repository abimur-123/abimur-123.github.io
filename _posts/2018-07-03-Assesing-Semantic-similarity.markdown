---
layout: post
title: You shall know an object by the company it keeps
date: 2017-07-03 00:00:00 +0300
description: Investigating semantic text representation and doc2vec in particular.
img: d2vpost.jpg
tags: [Natural language processing, semantic similarity, doc2vec]
---

## What is semantic analysis?

Text is at the heart of how we communicate with companies online. As humans, we find it easy to interpret semantic meaning of text/conversation in an almost unconcious manner. We use our understanding of the language and context to interpret semantic meaning.

Semantic analysis is the attempt at machines to replicate the process of understanding natural language the way humans do. Semantic analysis is not about teaching the machines, but it’s about getting them to learn. For example, the computer must be able to understand if the word "gray" is referring to the color or a person's state of mind.

## What is semantic similarity?

Semantic similarity can be defined as a metric that is defined over a set of documents, where the distance between documents indicates likeness of the underlying semantic content of the documents rather than just similarity. An intuitive way of thinking about semantic similarity is by grouping terms which are closely related (For example, king and man) and spacing apart the ones that are distantly related [1].

Semantic similarity can be really effective when it comes to addressing problems such as sentiment analysis on Twitter data, a post on Facebook (read Cambridge Analytica) or a review in the comments section of a news website.

## How do we implement this?

In 2014, Mikilov and Le introduced the **doc2vec** approach as a solution to one of the problems in the **SemEval competition** [2]. Mikilov was also one of the authors of the paper that introduced **word2vec**. Word2vec was one of the first methods that could capture semantic meaning of words from the text [3]. This was achieved by training a neural network based on word contexts. The neural network based word vectors are usually trained using stochastic gradient descent via backpropagation. Figure 1 depicts the setup of the word2vec model.

![]({({{site.baseurl}}/assets/img/d2v/word2vec.png)})

Figure 1:  Word2vec -- CBOW architecture predicts the current word based on the context, and the Skip-gram predicts surrounding words given the current word.

I will make an attempt at summarizing the `doc2vec` paper to obtain semantic meaning of text in this post.

### Paper Introduction

The aim is to assess degree to which 2 snippets of text are related in semantic meaning. This is achieved by assigning a score between 0-5, with 0 implying independant sentences and 5 implying semantically similar phrases.

THe paper suggests an unsupervised approach that makes use of paragraph vector to represent sentences. The similarity is compared using 3 metrics -- **Cosine, Bray-Curtis and Correlation**. The approach was ranked first out of fifty-three submissions for the Spanish-English (Spanglish?) track in the STS competetion.

## Research question(s)

The authors raise 3 main research questions in this paper -
- How does vector size matter?
- Better alternative to Cosine metric for measuring similarity?
- Does averaging Doc2vec models for cross-lingual tasks yield an improvement over one model alone?

### Paragraph vector

Documents might not have a logical structure like words, which makes it harder to represent documents of varying length as numeric vectors. Doc2vec helps circumvent this problem by introducing a paragraph vector along with the already existing word vectors present in word2vec. So, when training the word vectors W, the document vector D is trained as well, and at the end of training, it holds a numeric representation of the document. Figure 2 shows the setup of the doc2vec model [4].

![]({({{site.baseurl}}/assets/img/d2v/doc2vec.png)})

In Paragraph vectors, paragraph vectors are concatenated with word vectors to form a single vector. How does this help? *The paragraph vector acts as a memory of what is missing in the current context. Word vectors are shared across all the paragraphs, while paragraph vectors are shared across all contexts generated from the same paragraph. Vectors are trained using `stochastic gradient descent with backprop`.*

*How do we get vectors for new documents?* - paragraph vectors are computed using an inference step. This is also obtained by gradient descent. In this step, the parameters for the rest of the model, the word vectors `W` obtained during training and the softmax weights, are fixed.

There is a really nice implmentation of this algorithm in the [Gensim](www.google.com) library. Gensim claims `doc2vec` is a deep learning library but there's nothing deep about it. It's a simple three-layered neural network - input, hidden and output layer.

### Text analysis

The text was pre-processed to improve predictions. The following 3 steps were performed as part of pre-processing

1. text normalization
2. tokenization
3. lowercasing

Semantic similarity is assessed based on vectors of the sentences. Methods used to calculate proximity between vectors -

1. Cosine
2. Bray-Curtis and
3. Correlation

### Research question(s) answers

- How does vector size matter?
> The authors cannot come to a conclusions from the results, since size 200, 300 and 400 yields best results for various sub-tasks.

- Better alternative to Cosine metric for measuring similarity?
> The results indicate that the Bray-Curtis metric performs betterthan the other two in five out of seven test sets as part of the SemEval tests.

- Does averaging Doc2vec models for cross-lingual tasks yield an improvement over one model alone?
> Averaging the similarity scores for the source and the target language seemed to be a promising approach. This combination led to best Pearson correlation scores for two of the four crosslingual test sets in the SemEval competition.

## Paper Conclusions

Doc2vec is a promising unsupervised approach to solving the semantic similarity problem in NLP. There are various blog posts explaining how this can be implemented using Python.

# References

1. Semantic similarity https://en.wikipedia.org/wiki/Semantic_similarity
2. Semantic text similarity competition benchmark. Available at http://ixa2.si.ehu.es/stswiki/index.php/STSbenchmark#Results
3. Mikolov, T., Chen, K., Corrado, G., and Dean, J. (2013). Efficient estimation of word representations in vector space. arXiv preprint arXiv:1301.3781. Paper link https://arxiv.org/pdf/1301.3781.pdf
4. Quoc V. Le and Tomas Mikolov. 2014. Distributed Representations of Sentences and Documents. CoRR
abs/1405.4053 (2014). Paper link https://arxiv.org/abs/1405.4053

# Useful Blog posts
1. https://rare-technologies.com/doc2vec-tutorial/
2. https://medium.com/scaleabout/a-gentle-introduction-to-doc2vec-db3e8c0cce5e
3. https://github.com/RaRe-Technologies/gensim/blob/develop/docs/notebooks/doc2vec-IMDB.ipynb
