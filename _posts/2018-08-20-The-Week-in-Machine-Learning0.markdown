---
layout: post
title: The week in machine learning -- week of August 13th, 2018
date: 2018-08-19 00:00:00 +0300
description: Exploring advancements in machine learning and Artifical intelligence
img: WIML/wc_1308/title.jpg
tags: [comedy, dialogue systems, Descartes, SciNet, TransmogrifAI, Salesforce, sciene]
---

The Google juggernaut keeps chugging along. The behemoth has now turned to AI to help cut down its power bill by close to 30 per cent! DeepMind AI has helped cut electricity use at Google data centres thanks to its efficient use of equipment, such as cooling systems and windows. I might just end up paying them to work there (kidding). In other news, Microsoft is now inviting applications for their [AI idea challenge](https://www.ailab.microsoft.com/challenge). Do sign up for this if this is something that excites you and if you want to win a Surface Book 2.

In this week's post, I explore the use of ML in stand-up comedy, geospatial data and a paper that can is using neural networks to discover concepts in Physics. In the *Food for thought* section, I discuss how machine learning is impacting our understanding of science. Let's get started!

## In the news

### [Artificial intelligence leads to real comedy for PhD student](https://www.ualberta.ca/newtrail/featurestories/2018/may/have-you-heard-the-one-about-the-robot-comedian)

Kory Mathewson, an improv comic and a PhD student at the University of Alberta, is using robots to perform improv on stage. He has two shows in this year’s Edmonton Fringe Fest: TEDxRFT, an improv show that riffs on the popular TED Talks videos, and Human Machine, an AI improv show. The second show is also part of his PhD work. He has been working on the interaction of humans with dialogue systems like Amazon and Siri, and how they can be funny. Mathewson began to draw connections between his comedy (began as a teenager) and his research. He has been using reinforcement learning to interact with this dialogue systems and as part of his thesis, he's building a human-robot improv show. For the project, he uses a robot that is programmed with software called A.L.Ex., the Artificial Language Experiment, made in collaboration with [Piotr Mirowski](https://www.researchgate.net/profile/Piotr_Mirowski). This is briefly how it works
1. It tries to make its own sentence, word for word, that looks like sentences from the database.
1. It reads a database of movie scripts to map what sentences look like.
2. If the new sentence reads as though it could come directly from the database, the system increases the probability of making similar sentences.
3. Over several guesses and corrections, the system improves its language map.
4. When you ask a question, it groups words that occur together, like “hospital, doctor, needle,” into topics.
5. It uses these perceived topics to create responses that stay within the same topic, mimicking a sentence from the database.

[Here](https://youtu.be/P60UdY5rCLM) is a link to the video of a trial run with the improv bot.

This makes me wonder if people would be okay if they could create a robot that has Ricky Gervais' brand of humour, or would people shut down a foul-mouthing robot?

### [Descartes Labs unleashes machine learning on geo-spatial data](https://qz.com/1356945/descartes-labs-unleashes-machine-learning-on-space-data/)

Descartes Labs, a startup focused on applying machine learning to geospatial datasets, announced a partnership with Airbus to obtain high-resolution global imagery. Descartes allowed businesses to analyze satellite imagery it pulls in from NASA and ESA to build predictive models, and now, it is adding weather data to its library, as well as commercial high-resolution imagery thanks to a new partnership with Airbus.

The company’s clients then use this data to predict the growth of crops for example. The company tries to address a big problem in data science -- how can data scientists spend more time applying science to the datasets rather than collecting and cleansing the data.

For geospatial analysts, the goal is not simply detecting a change that has occurred but creating models that can predict change or future events. That requires massive amounts of data and massive computing capabilities. Descartes Labs’, which mostly runs on the Google Cloud Platform, has processed more than 11 petabytes of compressed data! Developers could also choose to bring their own data into the system to build better models.

## Scientific papers

### [Discovering physical concepts with neural networks](https://arxiv.org/pdf/1807.10300.pdf)

Physics is a subject built on formulating theories followed by running experiments to validate them. It is also heavily influenced by our prior knowledge of how the world works. Quantum mechanics, for example, is built on classical mechanics using various mathematical ideas that were prominent at the time. The authors explore an interesting question -- *Are the laws of quantum physics, and other physical theories more generally, the most natural ones to explain data from experiments if we assume no prior knowledge of physics?*

The authors are interested in what the neural networks can learn from experimental data. For example, in the case of a swinging pendulum, the goal is to find some simpler representation of this data. The researchers feed data from a swinging-pendulum experiment into a neural network they call the **SciNet** (architecture in **Figure 1**). They also conduct experiments that include the collision of two balls, the results of a quantum measurement on a qubit, and the positions of the planets and sun in the night sky.

![]({{site.baseurl}}/assets/img/WIML/wc_1308/SciNet.png)

**Figure 1: SciNet architecture**

The authors apply supervised and unsupervised machine learning techniques using ideas from representation learning. The idea is that the physicist (or SciNet) when exposed to some experimental observations pertaining to a physical setting (e.g. a time series describing the movement of a particle at constant speed), finds a simpler representation (e.g. the two parameters initial position and speed). This is the encoder portion of the network

The network is then used to predict a scenario in this physical experiment (e.g., "where is the particle at time *t*?"). This is done using the decoder section of the network. The idea is to use only encoder representation of the data alone to answer the question and not the original data.

Using the pendulum data, SciNet is able to predict the future frequency of the pendulum with an error of less than 2 per cent. The neural network doesn’t reveal the precise equation, but it does show that the network uses only two variables to come up with the solution. Relevant laws of motion use the same number of variables to answer questions such as "where is the particle?".

The network also learns to predict the future position of Mars and the sun using the initial position as seen from Earth. This might be the first demonstration that a neural network can compress data in a way that reveals the nature of the laws of physics.

Could neural networks re-write laws of physics-based solely on experimental data and no prior assumptions?

## Tools and resources

### [Salesforce Open-Sourcing Machine Learning Software Behind Its 'Einstein' AI](https://engineering.salesforce.com/open-sourcing-transmogrifai-4e5d0e098da2)
Salesforce has opened the library that currently powers their Einstein AI platform -- TransmogrifAI (a pun on Transmorgify, which the dictionary defines as the process of transforming, often in a surprising or magical manner).

Salesforce has to build customer-specific machine learning models for any given use case (churn, sales forecast etc.). The data should also be protected and not shared with other organizations. This makes it extremely hard to build an all-encompassing global model. This means Salesforce has to build a model for every single use case (probably a thousand)!

TransmorgrifAI enables data science teams to rapidly produce data-efficient models for heterogeneous structured data at massive scale. It is built using Scala and uses SparkML. This is how it can be useful --

1. It optimizes the feature transformations to make it easier for machine learning algorithms to learn from the data. For example, it might transform a numeric feature like age into the most appropriate age buckets for a particular problem — age buckets for the fashion industry might differ from wealth management age buckets.
2. It has algorithms that perform automatic feature validation to remove features with little to no predictive power — features whose usage has drifted over time, features that exhibit zero variance, or features whose distribution in the training examples varies significantly from their distribution at prediction time.
3. It runs a tournament of several different machine learning algorithms on the data and uses the average validation error to automatically choose the best one. It also automatically deals with the problem of imbalanced data by appropriately sampling the data.

This can be really useful if your company is in a situation where you have to build hundreds of models and you want to automate this process. Check out their [Github page](https://github.com/salesforce/TransmogrifAI) for more use cases and explanations.

## Food for thought:

### [Could machine learning mean the end of understanding in science?](https://theconversation.com/could-machine-learning-mean-the-end-of-understanding-in-science-98995)

We saw how **SciNet** was able to understand a concept in physics by learning from experimental data, without prior assumptions. In this article, Amar Vutha, an assistant professor in Physics at UofT tries to address this question in relation to artificial intelligence and science -- **what AI means for the future of “understanding” in science?**

The basic template of physics has been finding a set of equations that describe a unifying principle/theory. This is how we figured out the Standard Model, which accurately describes the underlying structure of every atom, nucleus or particle. This is how we try and understand gravity, black-holes and superconductivity. We try to understand the universe through mathematical equations at present.

There are problems where we might not have the necessary mathematical tools to explain how nature works. This is where we could employ machine-learning methods to help find answers. It might not have a closed mathematical form, but it does a heck of a job in predicting results. This model could learn complex representations from data obtained from Large Hadron Colliders, that particle physics experiments cannot answer.

*So, what are the implications of using machine learning to answer questions in science?*

Huge!

Machines can do a better job at humans when it comes to prediction. But, is the primary goal of science just prediction?

If we sacrifice understanding for better predictions, does the pursuit of science even make sense?

This article definitely made me wonder about the direction in which science is headed, are we going to let **SciNet** tell us how the world works, or do we stick to the mathematical models developed by Einstein and Newton?

I'll leave you guys with that thought. Until next time...
