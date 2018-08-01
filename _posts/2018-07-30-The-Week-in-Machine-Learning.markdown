---
layout: post
title: The week in machine learning wc July 23rd, 2018
date: 2018-07-31 00:00:00 +0300
description: Exploring advancements in machine learning and Artifical intelligence
img: WIML/wc_2307/machine_learning_xkcd.png
tags: [evolutionary algorithms, Gluon, supervisely, data privacy, ethics]
---

This week's first article in the news is also based on a paper. Funny story, the paper did not create as many waves as the news article itself (not surprised). I would definitely encourage more people to summarize papers and write articles or blog posts about them to help expand the reach.

## In the news

### [Evolutionary algorithm outperforms deep-learning machines at video games](https://www-technologyreview-com.cdn.ampproject.org/c/s/www.technologyreview.com/s/611568/evolutionary-algorithm-outperforms-deep-learning-machines-at-video-games/amp/)

Neural networks are finding their way into our everyday lives slowly and this would only continue to grow. Right now there is no tool that is more powerful than a neural network, right?

Not quite. An entirely different type of computing has the potential to be significantly more powerful than neural networks and deep learning. This technique is based on evolution process that helped create the human brain -- evolutionary algorithms.

Dennis Wilson and a few colleagues at the University of Toulouse in France have shown how evolutionary computing can match the performance of deep-learning machines at the emblematic task that first powered them to fame in 2013—the ability to outperform humans at arcade video games such as Pong, Breakout, and Space Invaders.

The process involves randomly creating a code called the “genome” of the program. This genome is then tested to see how well it plays the game and depending on how well it performs, the genome is then reproduced with mutations and tested again, and so on. This is the evolutionary aspect of the algorithm. For this problem, the team tested 10,000 genomes in this way.

Many genomes ended up playing entirely new gaming strategies, often complex ones. But they sometimes found simple ones that humans had overlooked. This in a way mirrors the neural network approach of learning complex representations from data.

**So why am I posting this here if neural networks can achieve similar results? Why do I think this is amazing news?**

The genome or the evolved code is small and makes it easy to see how it works. Compare this to a well-known problem with deep-learning techniques that it is sometimes impossible to know why and how they have made particular decisions. The ramifications of these findings can be huge in a field like medicine.

Link to the paper - https://arxiv.org/pdf/1806.05695.pdf

### [Thousands of leading AI researchers sign pledge against killer robots](https://www.theguardian.com/science/2018/jul/18/thousands-of-scientists-pledge-not-to-help-build-killer-ai-robots)

Thousands of scientists who specialise in artificial intelligence (AI) have declared that they will not participate in the development or manufacture of robots that can identify and attack people without human oversight. Some famous scientists include Demis Hassabis (Google DeepMind) and Elon Musk (SpaceX and possibly Batman).

The pledge was facilitated by "The Future of Life Institute", which is a Cambridge-based nonprofit dedicated to ensuring regulation of dangerous AI technologies. The gist of the pledge was -- "to neither participate in nor support the development, manufacture, trade, or use of lethal autonomous weapons.”  

The military sector is currently one of the largest funders and adopters of AI technology. It is now possible to design weapons that can track, identify and kill without human intervention (killer drones). This pledge can be seen as an effort to ensure this does not happen.

I personally find this to be a fascinating topic of discussion. With so much discussion about signing Nuclear treaties and bio-warfare in the limelight, this has slowly gone under the radar. Would love to hear your thoughts on killer robots, the impact AI could have in the military and the possible pros and cons of using AI in the military.

## Scientific papers

### [When Recurrent Models Don’t Need To Be Recurrent](http://www.offconvex.org/2018/07/27/approximating-recurrent/)

This blog post is based on [paper](http://www.offconvex.org/2018/07/27/approximating-recurrent/) by the same authors. When we think sequence tasks we automatically think Recurrent Neural Network (RNNs). Someone who's worked with RNNs understands how time-consuming and complex it is to train one. We still swear by RNNs because of its effectiveness in capturing context. It provides persistence of information, similar to the how the human brain functions. Intriguingly, this added expressivity does not seem to boost the performance of recurrent models.

The authors explore cases where this persistence might actually be given more importance than is due. These tasks include Language modelling, machine translation and speech synthesis to name a few, where feed-forward match results from the best recurrent networks. Recurrent models are fit to data using backpropagation. Backpropagating from time step T to 0 requires large amounts of memory in most cases, so RNNs employs a truncated approach, where it only backpropagates gradient `k` times steps. The sequences that an RNN could learn is somewhat limited by this value `k`.

In the paper, the authors explore the gap between RNNs and feed-forward models trained using gradient descent. They find that feed-forward and stable recurrent models (no vanishing/exploding gradients) trained by gradient descent make identical predictions at test-time.

There are parts of the assumptions that I still need to re-read to ensure I completely comprehend the conditions under which feed forward networks match an RNNs performance. This paper definitely tingled my brain cells and hope you experience the same feeling.

Transformers is an interesting concept. This [paper](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html) by Google talks about how transformers outperform RNNs and CNNs in language translation tasks. One cannot classify it as a feed-forward network or an RNN.

## Tools and resources

### [Gluon NLP](https://github.com/dmlc/gluon-nlp)

GluonNLP is a one-stop shop that centralizes resources for reproducing NLP results and an array of pre-trained models for neural machine translation, sentiment analysis etcetera. It also comes with utilities for data pipelining and public datasets.

### [Supervisely](https://supervise.ly/)

Supervisely helps make and prepare training data for a number of computer vision tasks ranging from pedestrian detection to tumours segmentation [1].

When building an AI product there are three main stages -- data annotation, preparation and designing the neural network. Results at each stage are affected by developments in the stage preceding it. Supervisely helps cover these 3 stages in their tool that they claim will make it easier to build AI products.

Their recent release allows one to train & run the latest neural networks with Supervisely. The problem with cloud offerings is you are forced to use their computational resources, store your data on their servers, use their software. This is designed to keep you forever because the costs involved in exporting solutions across platforms are usually more expensive than sticking to the cloud provider. Supervisely allows you to run models and store data anywhere!

They have all the models on their [GitHub page](https://github.com/supervisely/supervisely). One can modify these networks with the Supervisely library.

[This blog post](https://hackernoon.com/supervisely-goes-beyond-annotation-latest-deep-learning-models-out-of-the-box-144bc372d6f6) should help you get started with the tool.

## Food for thought:

### [What if I paid people for their data?](https://www.economist.com/the-world-if/2018/07/07/what-if-people-were-paid-for-their-data)

I found this article to be fascinating because it's the first time I've come across the word "Data Slavery". This is reflective of our current state according to Jennifer Lyn Morone, an American artist. Jennifer Lyn Morone created dossiers containing different subsets of her personal data and displayed it in a London gallery (see below) in 2016! She also registered herself as a company to profit from her own data.

![]({{site.baseurl}}/assets/img/WIML/wc_2307/artist_personal.png)

**Photograph: Courtesy of the artist and Carroll / Fletcher, London [2]**

This might sound like a bizarre thing to do, but with GDPR kicking in efforts are on the way to give people more control over their own data. But what if people wanted to relinquish this control in exchange for cash. How would you determine how much is each person's personal data worth? This definitely makes for an interesting question and discussion.

I find that it's harder to put a price on this because insights that can be obtained from this data might change based on how the data is analyzed. Mr Weyl predicts in “Radical Markets”, that in the age of AI, it might just make sense to treat data as a form of labour. We provide/generate data that is used to power AI, thus making our data equivalent to labour that drives AI.

The problem arises when we give up our personal data be default to obtain services such as Google and Facebook for free. This might change if these companies had to pay to obtain our data. Do we really want to lose out on such services at the cost of having more control of our data?

With that, I conclude this week's blog post. Any feedback, criticism or suggestions are welcome. You can reach me by email at abimur@gmail.com, or on Twitter (@abimojo).

## Resources

1. https://medium.com/deep-systems/introducing-supervise-ly-57b00f863040
2. https://www.theguardian.com/artanddesign/2016/feb/09/jennifer-lyn-morone-neoliberal-lulz-data-surveillance#img-2
