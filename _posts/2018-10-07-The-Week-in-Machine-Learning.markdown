---
layout: post
title: The week in machine learning -- week of October 7th, 2018
date: 2018-10-07 00:00:00 +0300
description: Exploring advancements in machine learning and Artifical intelligence
img: WIML/wc_0710/title.jpg
tags: [PyTorch, Famine, RandomForest, Bayesian, Graphs, ethics]
---

Happy Thanksgiving people!

To anyone who's been following (hoping for single digit readers at least) and are thinking if this series is dead, I don't blame you. So, I've moved to a new city and been busy with my new role as a Machine learning engineer. I will try and come out with a post on a bi-weekly basis at-least.

In this week's post I discuss about Google and Facebook coming together to drive AI development, how World Bank wants to use machine learning to predict famine, a method that could possibly replace Random forests. I also discuss about an interesting article about nerd-sightedness of AI.

## In the news

### [PyTorch now on Google cloud](https://cloud.google.com/blog/products/ai-machine-learning/introducing-pytorch-across-google-cloud)
Google and Facebook are teaming up to make each company’s technologies work together.

Google is broadening their cloud platform to support PyTorch, Facebook’s open source machine learning framework. Google will now provide a VM image on the cloud that will let users run PyTorch 1.0 Preview.

Over the past few years, Google has been encouraging developers to use it's Tensorflow framework for AI projects, and it developed its TPUs (Tensor Processing Units) to work best with Tensorflow. The fact that Google is willing to update its TPUs to work with Facebook’s PyTorch software shows that the company wants to support more than its own AI framework. PyTorch is popular within the research community because of the relatively easy learning curve compared to Tensorflow. This move by Google could help draw more cloud computing customers and researchers who may use competing frameworks.

### [Fighting famine with machine learning](https://www.washingtonpost.com/technology/2018/09/23/world-banks-latest-tool-fighting-famine-artificial-intelligence/?noredirect=on&utm_term=.65bcad34d90b)
A famine is hard to predict and can be triggered by a multitude of factors. A drought or some other climatic interference in crop production. Factors such as food price inflation, political instability, military conflict and sometimes even too much rain could trigger or magnify the effect of a famine. Out of the last 10 major famines, nine have resulted from conflict and war. This year, an estimated 124 million people in 51 countries are facing severe food insecurity.

A coalition of international organizations -- which includes the World Bank, the United Nations and the International Committee of the Red Cross are partnering with tech companies such as Microsoft, Google and in an effort to prevent future famines using technology. This could help securing the release of funding to at-risk areas before it’s too late.

These models would be tailored to different regions around the world, each of which has unique vulnerabilities to famine. World Bank claims early interventions could reduce humanitarian costs by as much as 30 percent. I finally explore an interesting article I read about how AI needs to be more philosophical.

## Scientific papers

### [Accelerated Bayesian Additive Regression Trees](https://arxiv.org/pdf/1810.02215v1.pdf)

Random forest and gradient boosting tree based algorithms are probably one of the most widely used machine learning algorithms for supervised learning. Bayesian additive regression trees is closely related but less well-known method that often achieves superior accuracy. And no, it is not simple random forest or gradient boosting with a prior. It has a different tree growing criteria and algorithm, which yields a number of practical advantages — robustness to the choice of user-selected tuning parameters, more accurate predictions, and a natural Bayesian measure of
uncertainty. BART suffers from the downfalls of Bayesian methodology -- intesive computation resources as it uses the Metropolis-Hastings
Markov chain Monte Carlo approach (MCMC) approach. This paper develops a variant of BART that is comparable to fast posterior estimation, making it almost as fast as xgboost, while still retaining BART’s hyperparameter robustness and remarkable predictive accuracy.

The BART prior represents the unknown function as a sum of many piecewise constant binary regression trees. The tree prior is specified by three components:
1. the probability of a node having children at depth `d`
2. the uniform distribution over available predictors for splitting rule assignment at each interior node
3.  the uniform distribution on the discrete set of available splitting values for the assigned predictor at each interior node

The basic BART MCMC proceeds as a Metropolis-within-Gibbs algorithm, with the key update of the individual regression trees being conducted as a local random walk Metropolis-Hastings (MH) update, given all of the other trees as well as the residual variance parameter. MCMC does not work with large number of observations (hundreds of thousands). It follows the Gibbs update framework but replace the Metropolis-Hastings updates of each single tree by a new grow-from-root backfitting strategy.

The author found that this approach was 31% more accurate and 10 times faster than cross-validated XGBoost method. This method is 8 times slower and 3.5 times more accurate than the default untuned XGBoost method.

## Tools and resources

### [Stellar Graph](https://github.com//stellargraph/stellargraph)

Python library for machine learning on graph or network structured data. Graph structured data is used for representing complex interactions between entities (people on social media being a perfect example). The nodes in a graph have attributes and classical problems that could be solved using them are node classification, link prediction and clustering being a few of them. When the networks are huge, analysing them can using standard machine learning techniques do not work well. This is where graph embeddings could really come in handy. Stellar graph can be used to answer the following questions -
 - Representation learning for nodes and edges, to be used for visualisation and various downstream machine learning tasks
 - Classification and attribute inference of nodes or edges
 - Link prediction

Stellar graph uses the `Keras` library which helps flexibility in using existing, or creating new models and workflows for machine learning on graphs.

The StellarGraph library currently includes the following algorithms for graph machine learning:

1. [GraphSAGE](http://snap.stanford.edu/graphsage/)
2. HinSAGE
3. [Node2Vec](https://snap.stanford.edu/node2vec/)
4. [Metapath2Vec](https://ericdongyx.github.io/metapath2vec/m2v.html)

The Google AI blog also has an interesting read on graph related machine learning. You can find that [here](https://ai.googleblog.com/2016/10/graph-powered-machine-learning-at-google.html).

## Food for thought:

### [Why it’s time for AI to get philosophical](https://www.theglobeandmail.com/opinion/article-deep-learning-why-its-time-for-ai-to-get-philosophical/)

We notice that stories about AI now appear in the daily news, and these stories seem to be split between self-congratulatory pieces by people in the AI world, about how deep learning is poised to solve most problems in this world, and the doom enthusiasts who say robots will soon enslave us all.

Algorithms nowadays analyze pretty much all our movements and suggest what we buy or do based on that. We have greatly benefited from this but people are now slowly coming to realize some of the dangers associated with this after the Facebook incident. There have been a few more documented cases about AI/machine learning gone wrong.

The author mentions an interesting concept -- risk of something called nerd-sightedness: the inability to see value beyond one’s own inner circle. There’s a tendency in the computer-science world to build first, fix later, while avoiding outside guidance during the design and production of new technology. I have noticed that there's a rush to integrate ethics into AI and a call for building algorithms without bias. Integrating this with the curicullum could really help a coder understand the implications of a piece of code outside the purview of the system itself.

Should ethics be integrated at an early stage of a computer science/machine learning degree? If so, how could this be done in an effective manner?

Would love to hear your thoughts on this one...  
