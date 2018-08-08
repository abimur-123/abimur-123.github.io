---
layout: post
title: The week in machine learning -- July 30th, 2018 week
date: 2018-08-07 00:00:00 +0300
description: Exploring advancements in machine learning and Artifical intelligence
img: WIML/wc_3007/blog_title.jpg
tags: [NIMH, brain, mental illness, real-estate, emotions, facial-recognition, keras, fairness, ethics]
---

This week we were greeted to the news of - **OpenAI Bots Crush the Best Human Dota 2 Players in the World**. So, what next for the OpenAI team? 

In this week's post, I explore the use of machine learning in mental health, real-estate and a paper that can accurately predict human emotions. I finally discuss an article on HBR that encourages data scientists to make "fairness by design" a part of the machine learning model development cycle.

## In the news

### [Machine learning explores links between mental illness and brain networks](https://www.eurekalert.org/pub_releases/2018-08/uops-mll080218.php)

 A new study using machine learning, by Theodore D. Satterthwaite's team at Penn Medicine and funded by the NIMH, has identified brain-based dimensions of mental health disorders. The team mapped abnormalities in brain networks to four dimensions of psychopathology: mood, psychosis, fear, and disruptive externalizing behaviour.

In most cases, all psychiatric diagnoses rely on the physician just talking to the patient as we still do not understand how abnormalities in the brain could lead to psychiatric symptoms. Is this something that could be answered using data?

The team studied both functional MRI scans and a comprehensive evaluation of psychiatric symptoms of a sample of adolescents and young adults, in a study funded by the  National Institute of Mental Health(NIMH). The brain and symptom data were then jointly analyzed using a machine learning method called [sparse canonical correlation analysis](https://arxiv.org/pdf/1705.10865.pdf). The analysis revealed how changes in brain network were strongly correlated with psychiatric symptoms.

According to the findings, when both the brain and symptomatic data are taken into consideration, psychiatric symptoms do not neatly fall into well-defined categories. Instead, groups of symptoms from diverse clinical domains emerged to form dimensions that are linked to specific patterns of abnormality in the brain. They also found that patterns associated with both mood and psychosis became significantly more prominent with age. Additionally, brain connectivity patterns linked to mood and fear were both stronger in female participants than males.

I found the article to be particularly interesting because this might be the first attempts to study clinical mental health using machine learning to draw insights from the both -- psychiatric evaluation and MRI scans. This could provide new insights into mental health issues and how it can be captured at an earlier stage.   

The journal can be found [here](https://www.nature.com/articles/s41467-018-05317-y) and the code can be found on [Github](https://github.com/cedricx/sCCA/tree/master/sCCA/code/final)

### [Skyline AI raises $18M Series A for its ML-based real estate tech](https://techcrunch.com/2018/07/31/skyline-ai-raises-18m-series-a-for-its-machine-learning-based-real-estate-investment-tech/)

Just four months after they got $3 million in seed funding, Skyline AI announced that it raised an $18 million Series A. A quick peek at the [Skyline AI](https://www.skyline.ai/) (a background that hurt my vision), suggests that they are new entrants into the ML-based real estate investment sector. Realtor, Vancouver is another company that comes to mind. Skyline claims to have a 94% average success rate in predicting profits from deals, and they use an ensemble of machine learning models that combine both supervised and unsupervised models.

In June, it teamed up with an unnamed partner in the U.S. to acquire two residential complexes in Philadelphia for $26 million. Then in July, Skyline AI announced a partnership with Greystone to improve the dealmaking and loan underwriting processes. Some of this capital will be spent on growing its research teams in Tel Aviv, and its recently opened sales and real estate office in New York.

You might wonder why I mention an article about AI in real estate?

The real estate market in the US is currently a seller’s market, and housing affordability going down steadily for 2018 as there is a limited supply of homes (source: [Gallup](https://news.gallup.com/poll/233693/home-selling-buying-intentions-point-sellers-market.aspx)). This is where AI could come in handy in helping someone decide the "right time" to purchase a property based on 50 years of data. It is usually hard to deal with time series data and real estate data varies on a daily basis. Any application that could predict these forecast prices in this market could be a gold mine for buyers and sellers. Applications like Zillow try and do this and a general understanding of how recommender systems work could help make a listing attractive to draw potential buyers.


## Scientific papers

### [Helping computers perceive human emotions](https://dam-prod.media.mit.edu/x/2018/05/01/personalized-mixture-supervised_final_tYWcW0Y.pdf)

Michael Feffer et. all from MIT, investigate the use of personalized CNN's for detecting facial expressions. Analyzing facial expressions and interpreting our emotions is an active area of research. The biggest challenge is people express emotions differently based on various factors. Traditional models use a “one-size-fits-all” approach where they train on one set of images depicting various facial expressions, optimizing features — such as how a lip curls when smiling — and mapping them across a new set of images.

The authors combined 'mixture of experts' (MoE) technique with model personalization to help capture nuances in expression that varies between individuals. MoEs refers to an approach that involves multiple neural network models called “experts”. These networks produce similar output for the same type of input but are trained on different subsets of data so that they are better suited to specific contexts (not sure, but this sounds similar to Random Forest where we pass all the features to every decision tree). At test time, all networks receive the same input, and an output for the overall network is created by combining outputs or selecting the 'best' output. Furthermore, we combine the learning of MoEs with [supervised domain adaptation (DA)](https://en.wikipedia.org/wiki/Domain_adaptation) so that the model can adapt to previously unseen subjects. **Figure 1** shows the proposed model architecture.

![]({{site.baseurl}}/assets/img/WIML/wc_3007/MoE.png)

**Figure 1: Proposed model architecture**

These personalized MoE models have clear advantages over the compared “one-size-fits-all” models in terms of how well are able to adapt to the target population when using limited amounts of labelled data from target subjects. Model personalization can be key in working with limited data with many different domains.

## Tools and resources

### [Auto Keras](https://github.com/jhfjhfj1/autokeras)

Another library for automated machine learning. The goal of any AutoML approach (Google, H2O or WEKA) is to allow domain experts with limited machine learning background to tap into the power of deep learning models. This tool is a wrapper to the keras library, which is predominantly used to build deep learning models. AutoKeras automatically searches for the hyperparameters of deep learning models and has a handful of examples to get one started. From close to 200 lines of code to build simple models (read MNIST digit classifier), it is now a mere 10 lines of code to implement it using tools such as AutoKeras. AutoKeras is also open source unlike other AutoML approaches and is currently in its pre-release version. This is an amazing package that will be really useful when they come out with the first production release.


## Food for thought:

### [Make “Fairness by Design” Part of Machine Learning](https://hbr.org/2018/08/make-fairness-by-design-part-of-machine-learning)

We use ML to make personalized predictions or recommendations starting from bank loans to the shows we watch. There are more models that use personalized data as part of their architecture to predict. This article from Harvard Business Review explores the concept of a "fair design" while building an ML model. The authors first explore the cases where ML has gone wrong to set the tone of the article. They discuss bias in models and how it can manifest in various forms across different stages of building an ML model. They discuss three biases - Sampling, performance and confirmation bias. The authors share the design approach they employed for a recent project and suggest the following steps --

1. Pairing data scientist with a social scientist to allow for better awareness of demographic biases
2. Annotating with caution -- Crowd-sourcing is the latest trend in obtaining more annotated data. The authors warn about the inherent human bias that creeps in while annotating.
3. Combining traditional machine learning metrics with fairness measures
4. When sampling, balance representativeness with critical mass constraints -- balanced dataset helps build better models (usually)
5. When building a model, keep de-biasing in mind -- Removing cues such as demographic information is something the authors suggest

There is a growing concern in regards to both privacy and bias, especially after GDPR was implemented. The authors explain that fairness by design isn’t about prioritizing political correctness above model accuracy but it is about building models that are accurate and conscionable. In their project, the authors were able to develop models with higher overall performance, greater generalizability across various demographic segments, and enhanced model stability — potentially making it easier for the health care system to match the right person with the right intervention in a timely manner.

I find bias to always be a fascinating topic when it's discussed in relation to machine learning models. There are people who favour accuracy over fairness and there are others who value fairness more than accuracy while building models. In my article about GDPR, I explain how I think GDPR could tie the hands of the developers to some extent and might yield models that have lower accuracy. The author does prove me wrong in this case but is this an exception to the rule, or is it possible to build models that yield similar accuracy while being fair and stripping bias from models?

Would love to hear your thoughts.
