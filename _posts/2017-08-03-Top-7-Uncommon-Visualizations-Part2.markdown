---
layout: post
title: Top 7 Uncommon-Visualizations Part2
date: 2017-08-03 00:00:00 +0300
description: I discuss the most some not so common visulizations on Tableau
img: tableau-logo.png
tags: [DataViz, Tableau, Charts] # add tag
---

Some of the other uncommon visualizations include:
1. Marimekko charts
2. Pareto charts
3. Word clouds

## Marimekko charts
There is a phenomenon in Statistics called the Simpson’s paradox, in which a trend appears when we look at data as a whole, but then reverses direction when the data is broken down into groups. This paradox is often encountered in the field of social sciences and becomes apparent with the Marimekko chart. A classic example of this, is the UC Berkeley study of gender bias in the graduate admission process which has become stuff of urban legend.
Marimekko charts visualize data over a pair of variables. It is a 100% stacked bar graph which is divided into segments. The axes are drawn to scale based on the pair of variables, and this determines the height and width of each segment. This makes it possible to determine the relationship between categories and their subcategories.
The main downfall of the Marimekko is the readability component which becomes is affected significantly if there are numerous segments. It also cannot be relied on for accurate comparisons between segments.

![]({{site.baseurl}}/assets/img/Tableau_Part2/Marikmekko.png)

[Source](https://i.pinimg.com/736x/79/56/14/795614849e4fcda53b229d26b954f557--marimekko-statistics.jpg)

**When to use this:** This chart is ideal to give a general overview of the data; for example if you want to plot profit margin by industry or the Revenue split for different markets. It also enables us to understand trends in small subsets of data and identify potential scenarios such as the Simpsons Paradox.

## Pareto charts
A Pareto chart can be used as a tool to learn and identify most frequent defects, or critical factors that can be counted or categorized. It depicts the Pareto effect where 80% of the output is usually produced by 20% of the input.
Pareto chart is a combination of bars and lines, where the bars are arranged from largest to smallest, from left to right. The categories or factors on the left symbolized by the bigger bars are more important than those to the right. A cumulative percentage line then helps understand the contribution of each category. This line is steep for bars with higher contributions and levels off as we move towards the smaller bars.

![]({{site.baseurl}}/assets/img/Tableau_Part2/Pareto_Chart.png)

[Source](http://www.theinformationlab.co.uk/wp-content/uploads/2014/08/Pareto-Chart.png)

**When to use this:** Pareto works really well in highlighting important factors. It helps teams direct their efforts where the biggest impact can be created. By breaking down a problem into smaller pieces Pareto reveals where there is room for improvement.

## Word Cloud
A word cloud is a visualization method that depicts the how frequently words appear. The size of each word is usually determined by the frequency of occurrence, or any other important parameter. It is used to display words that have certain properties (or meta-data) associated with them. For example, a word cloud of countries where sales could be used to determine the size of the country’s name. The major flaw with word clouds is that it becomes harder to visualize longer words whilst certain words inevitably can draw more attention. Another drawback of word clouds are that, the relationship between the words in the cloud and the size of the cloud may not be apparent at a glance. Hence, it is mainly used for aesthetic appeal.

![]({{site.baseurl}}/assets/img/Tableau_Part2/Word_Cloud.png)

[Source](http://www.neoformix.com/2012/DataVisRedCloud.png)

**When to use this:** It can be used to highlight important data points and can transform a dull visualization into a stunning one to convey crucial information.

However, it is important to remember that visualizations are only tools to serve as information maps and highlight the most crucial piece of information; they may not always paint the whole picture!


Shoutout to Samiya Nasim for helping me put this together. Thanks Samiya!
