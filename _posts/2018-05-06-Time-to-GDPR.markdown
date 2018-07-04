---
layout: post
title: GDPR - boon or bane?
date: 2017-05-26 00:00:00 +0300
description: I discuss pros and cons of GDPR
img: ./GDPR/GDPR_title.png
tags: [data privacy, ethics, GDPR]
---

The Internet has become an indispensable part of our lives now. We cannot think of a world without wi-fi and devices that help us access the internet. In a world that revolves around the internet the value of personal data is growing. Personal data has become the new oil and there is a mad race between companies to obtain more personal data from users.

The EU government is working on GDPR, which is going to take effect starting May 25th and the effects of this will be far-reaching. GDPR believes in giving the power back to the citizens by giving them more control of their personal data. The image below shows the lineage of GDPR and previous attempts at regulating data privacy -

![]({{site.baseurl}}/assets/img/GDPR/image_GDPR.png)

- Image coutesy [Digital Guardian](https://digitalguardian.com/blog/what-data-protection-directive-predecessor-gdpr)

## What is GDPR trying to achieve?

GDPR is built on 2 cornerstones - the ethical use of personal data and keeping that personal data secure. It makes the organizations more answerable in the manner in which they use personal data and steps to protect it. According to this any organization that is established in the European Union or that processes the personal data of individuals in the European Union in order to offer them goods or services or to monitor their behaviour will be affected by this The legislation involves highlighting the organization's responsibility to -
1. Obtaining user content,
2. Data collection procedure and storage and
3. Data security and how they use personal data.

[source](https://www.infolawgroup.com/2016/05/articles/gdpr/gdpr-getting-ready-for-the-new-eu-general-data-protection-regulation/)

The motivation for this legislation is the recent violation of privacy by big companies such as Facebook in [Spain](https://techcrunch.com/2017/09/11/facebook-fined-e1-2m-for-privacy-violations-in-spain/), [France](https://techcrunch.com/2017/12/19/france-puts-facebook-on-notice-over-whatsapp-data-transfers/) and [Google's](https://www.wired.com/story/google-big-eu-fine/) big EU fine to name a few.

One of the key elements of GDPR that is bound to make all companies(not only EU based) take notice is their hefty fines. The fines vary from €500,000 to a maximum of 4% of **annual** global turnover, or 20 million Euros(*whicever is higher*) for a breach of GDPR. To put this into perspective an article from [NCC group](https://www.nccgroup.trust/us/about-us/newsroom-and-events/press-releases/2017/april/last-years-ico-fines-would-soar-to-69-million-post-gdpr/) talks about how fines would have skyrocketed from €880,500 to €69 million!

## How do I think GDPR affect data science?

Data science involves collecting, analyzing and exchanging results of this analysis and which part of this does GDPR affect - EVERYTHING!

GDPR requires companies to obtain consent and supply information regarding why data is being collected. At any point in time if the purpose changes then consent must be obtained from users again. Users have the right to be forgotten which means organizations must scrub their data source within 30 days of notice. This can be extremely time-consuming given that almost all stages of the data science pipeline use personal data in one way or the other. GDPR also places several restrictions on how data must be stored. This could affect the balance between reproducibility of analysis and data anonymization.

As an aspiring data scientist, I see GDPR as a threat and an opportunity at the same time. A lot of the work a data scientist does is exploratory in nature. We might not know what to look for from the onset. Given a dataset, we explore the features of the data and how they affect the results. This could yield results that are unexpected at times. This is where as data scientists one improvises and is able to highlight the most important question we must be asking based on the data.

I feel GDPR to a data scientist would be similar to asking a Bayesian to only think as a frequentist, or telling a quantum physicist to think at a macroscopic level. Suppose I set out to build a model to analyze brain scans to find tumours and I instead find the reason for concussions as a part of the analysis, GDPR would either require me to not report my findings or get the consent of all the patients again before I could report my findings. This is like throwing spanner in the works for a data scientist.

What this could mean is moving the site of analysis from EU countries to other countries like the US, where laws are more conducive when it comes to using personal data of citizens. This could hamper data science growth in EU and lead to a mass exodus of companies.

The one thing I've noticed in most articles that I read about GDPR is how it's used as a moniker to talk about ethics of the use of personal data. Most companies are hurrying to ensure they satisfy the GDPR requirements and look at GDPR as another set of checkboxes they must tick in order to get on with their work starting May. This approach might just defeat the purpose of GDPR of bringing about an holistic/ethical treatment of personal data. Rather organizations must try and address the real problem - a dearth of ethical and transparent systems/models that can help individuals. GDPR does not let us explore the data to find out best possible outcomes from a given dataset. It needs us to have a blueprint from the outset about what the data must be used for. This can hamper companies as well as services for customers.

GDPR also emphasizes on "interpretability" of models to ensure a reasonable explanation is given to citizens on the process. There is a rise in the use of deep-learning models which can model extremely complex datasets. Interpreting every stage of these models is close to impossible given the size of each layer and the combination of hyperparameters. The use of these models might drop after GDPR is enforced which will be a huge blow to many data scientists.

I feel like the policy might make smaller companies come to a crashing halt. This is because the implementation requires restructuring the current infrastructure, which can be time and economically consume. For giants like Google and Facebook, this transition would be less brutal compared to the smaller companies. This is because they have an advanced infrastructure which would let them easily integrate this into their existing process.

## GDPR as an opportunity

I see GDPR as an opportunity for 3 reasons -
1. Bad use of data will reduce as a result of this
2. Earning the trust of customers by asking for consent
3. Applying for the role of Data Protection Officer(DPO) as a data scientist

GDPR feels more like a response to bad models with biased results built by poorly trained data scientist. GDPR would put an end to such models and produce better data scientists in the process. More people are becoming aware of their data privacy and I've noticed a lot more people using the "Private" mode while browsing. It is also no coincidence that the number of installs for Ad-Blockers has risen by 30% [NYtimes](https://www.nytimes.com/2017/01/31/technology/ad-blocking-internet.html). This just hampers the process of targetted marketing for most companies.

GDPR can help buck this trend by getting people on board by making the whole process transparent. By obtaining people's consent we get them on-board the targetted marketing process. Users would engage more actively than passively consuming data the models seem to suggest. I firmly believe that this active participation could result in better quality of data to the system.

This article by [Lee Schlenker](https://towardsdatascience.com/data-science-and-the-dpo-f8bfb31c75b1) uses a brilliant analogy for why it's important to hire a data scientist as a DPO - "Why is hiring a Data Protection Officer who ignores Data Science like buying an armoured car to drive around in circles?". GDPR makes it necessary for companies to hire a DPO. The role of a DPO is to ensure the organization does not violate GDPR. They would be asked to set up a data provenance that will track data processing and audit results. They also act as a bridge between customers and the organization. Their role also requires them to inform customers on how their data is being used and steps are taken to keep this secure.

Article 37 in GDPR requires a DPO to have "expert knowledge of data protection law and practices." This role can be compared to the independent Judiciary body in a few countries such as the UK. The primary role of a DPO would be to understand how and why personal data is being collected. Being a data scientist would help the DPO better appreciate the needs of a data scientist instead of stifling them with the privacy noose. *GDPR should act as directions rather than constraints and who better than a data scientist playing the role of a DPO to do this(elevator pitch for job role).*

![](https://www.computing.co.uk/w-images/9d0ed339-f24d-4147-86f0-fe3a9450b38d/0/dataprotectionknight-580x358.jpg)
- Image coutesy computing.co.uk

## Parting words

I am in favour of what GDPR is trying to achieve in helping create better decision-making models without bias and create a holistic and transparent approach to data-driven decision algorithms. The process in which GDPR tries to implement this is something I feel could backfire. The fines levied seemed unreasonable to smaller companies. It has also received a lot of flak for the designing few laws that are open to interpretation. This is something that the major companies could easily exploit. GDPR might just end up driving data-based companies out of the EU.

### TL;DR ![](https://info.digitalguardian.com/rs/768-OQW-145/images/gdpr-global-data-protection-infographic.png)
