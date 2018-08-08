---
layout: post
title: The week in machine learning -- July 16th 2018 week
date: 2018-07-23 00:00:00 +0300
description: Exploring advancements in machine learning and Artifical intelligence
img: WIML/wc_1607/wc_16thJuly.jpg
tags: [PoseNet, NIH, Alibaba, BAM, Twitter, Yellowbrick]
---

`print("Hello, World!")`

This is a weekly collection of latest scientific papers, news, resources and tools in the fields of Machine Learning and Artificial Intelligence. These articles should not take up more than ten minutes of your precious time.

I hope you find the weekly issue worthwhile. Feel free to share this with your friends and do drop any suggestions you might have to my inbox - abimur@gmail.com

Abishek

Week in Machine learning

## In the news

### [Google releases new pose-matching ML experiment](https://www.androidauthority.com/google-pose-matching-experiment-move-mirror-887954/)

Announced recently on the [Google blog](https://www.blog.google/technology/ai/move-mirror-you-move-and-80000-images-move-you/), the Move mirror experiment works only using a Web browser and a webcam.

This AI experiment matches your movements in real-time with hundreds of images from the web, of people performing the same movements (mind == blown).

To build this experiment, Google used PoseNet. They describe this as a "model that can detect human figures in images and videos by identifying where key body joints are. Move Mirror takes the input from your camera feed and maps it to a database of more than 80,000 images to find the best match."

### [The National Institue of Health will be hosting a workshop on using AI and ML to advance biomedical research](https://www.nih.gov/news-events/news-releases/nih-host-workshop-using-artificial-intelligence-machine-learning-advance-biomedical-research)

The National Institutes of Health is hosting a full-day public workshop, [Harnessing Artificial Intelligence and Machine Learning to Advance Biomedical Research](https://datascience.nih.gov/community/2018biomedAI). The workshop will feature leading experts from Amazon and IBM, and scientists from the NIH Clinical Center, MIT, Stanford and the University of Cincinnati who are currently using AI/ML in biomedical research settings.

Research areas expected to benefit from AI include medical imaging analyses, diagnostics, genomics, vaccine design, large-scale integrative analysis of data, healthcare analytics, precision medicine, and public health, among others.

This is happening on the 23rd of July, 2018 and their Twitter hashtag can be found [here](https://twitter.com/hashtag/2018biomedAI?src=hash) and the live feed on Facebook can be found [here](https://www.facebook.com/events/222716638375782/).

### [How Alibaba Uses AI And ML](https://www.forbes.com/sites/bernardmarr/2018/07/23/the-amazing-ways-chinese-tech-giant-alibaba-uses-artificial-intelligence-and-machine-learning/#59791b2b117a)

One of the reasons Alibaba and other Chinese tech companies such as Tencent and Baidu, collectively known as BAT, are making extraordinary gains in artificial intelligence is the support, investment and commitment of the Chinese government to become the dominant AI player in the world.

China is fertile ground to develop AI applications, and Alibaba is moving full throttle ahead. In fact, Alibaba invested in seven research labs that will focus on AI, ML, network security, natural language processing and more.

With its City Brain project, Alibaba hopes to help cities run their operations by artificial intelligence. In addition to these examples, Alibaba uses AI to optimize its supply chain, build products and drive personalized recommendations.

Should definitely be interesting to see how Alibaba decides to use AI in the near future.

## Scientific papers

### [BAM: Bottleneck Attention Module](https://arxiv.org/abs/1807.06514v2)

The authors explore the effect of *attention* in deep neural networks and further propose the BAM attention module that can be integrated with convolution neural networks (CNN).

In BAM, the authors decompose the process of inferring a 3D attention map into two streams -- the channel and spatial paths. **Figure 1** shows module architecture.

![]({{site.baseurl}}/assets/img/WIML/wc_1607/BAM.png)

**Figure 1 - BAM architecture**

The module has 2 hyperparameters -- dilation value (d) and reduction ratio (r). The dilation value determines the size
of receptive fields which is helpful for the contextual information aggregation at the spatial branch. The reduction
ratio controls the capacity and overhead in both attention branches.

To verify its efficacy, the authors conducted extensive experiments and confirmed that BAM outperforms all the baselines on three different benchmark datasets: CIFAR-100, ImageNet1K, VOC2007, and MS COCO.

### [Using semantic clustering to support situation awareness on Twitter: The case of World Views](https://arxiv.org/pdf/1807.06588v1.pdf)

There are two key problems that prevent users from gathering valuable insights from social media data -- a massive amount of information shared leading to information overload and the second being the proliferation of **fake news** or misinformation.

The specific goal of this system was to facilitate the analysis of datasets of multiple Twitter posts and allow for the clustering of consistent posts into different worldviews (a cluster of consistent messages that gives a possible view of a scenario).

The authors used a Subject-Verb-Object Semantic Suffix Tree Clustering (SVOSSTC) approach in order to produce worldviews. The advantage of SVOSSTC was found in its ability to create semantically consistent clusters of information with succinct cluster labels.

## Tools and resources

### [New Release of Yellowbrick (Open Source Python Machine Learning Visualization Library)](http://www.scikit-yb.org/en/latest/gallery.html)

Yellowbrick is a visual diagnostic tool that extends the `scikit-learn` API to allow human steering of the model selection process. I found this especially useful while using selecting features for various models and visualizing Confusion Matrices for classification problems.

### [AutoGraph -- tool that converts Python into TensorFlow graphs](https://medium.com/tensorflow/autograph-converts-python-into-tensorflow-graphs-b2a871f87ec7)

AutoGraph bridges the gap between eager execution and Tensorflow Graphs. It takes in your eager-style Python code (operations that return concrete values instead of constructing a computational graph to run later) and converts it to graph-generating code, without having to go through the graph generating meta-code.

Here's a [Google collab notebook](https://colab.research.google.com/github/tensorflow/models/blob/master/samples/core/guide/autograph.ipynb) that describes the tool usage.

## Food for thought

### [Bonding with Your Algorithm](https://www.edge.org/conversation/nicolas_berggruen-bonding-with-your-algorithm)

I found this interesting post on Edge.org, where Nicolas Berggruen, Founder and Chairman of the Berggruen Institute draws parallels between the algorithms we create and the relationship between parents and children. He goes onto state that as creators or the ones enabling the algorithms, we’re the parents. We need to be treating these algorithms the way we treat our children.

He goes on to explain why separating technology and humans, the way we often think about issues, is almost wrong.
