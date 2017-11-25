---
layout: post
title: Top 7 Uncommon-Visualizations Part1
date: 2017-07-27 00:00:00 +0300
description: I discuss the most some not so common visulizations on Tableau
img: tableau-logo.png
tags: [DataViz, Tableau, Charts] # add tag
---

I recently came across this publication online — Three charts are all I need. The author, Noah Lorang, makes a strong case about how “problem solving” characteristics of visualizations take a back seat to visual qualities and aesthetics. Although I agree with his line of reasoning I feel that this is a very functional perspective to visualization. When a user looks at a visualization they tend to forget the numbers and remember the impact. Basic charts tend to become repetitive and create less impact when compared to custom visualizations. Unique and custom visualizations also add variety and can offer more insights compared to basic charts. In this article I try to review less common yet useful visualizations –
1. Sankey charts (or Alluvial diagrams)
2. Sunburst or coxcomb charts
3. Box and Whisker plot
4. Steam graph

## Sankey Charts
Sankey charts show how various nodes flow together or apart across multiple groups or time periods. The width of the arrows or streams is proportional the magnitude, so the bigger the arrow, the larger the quantity. This is similar to how rivers split into streams or tributaries join to form larger streams. This can be designed for multiple levels.

![]({{site.baseurl}}/assets/img/Tableau_Part1/Sankey.png)

[Source](https://public.tableau.com/static/images/Su/SuperstoreInteractiveSankeyShowcase/Sankey/1.png)

**When to use this:** To show how groups are related to one another in the case of a many-many relationship or multiple paths through a set of stages (for instance, Google Analytics uses Sankey to show how traffic flows from pages to other pages on a web site). It is useful when it comes to depicting flows of: money, material etc.

## Sunburst or coxcomb charts
This type of visualization shows a hierarchical structure in a circular layout. It consists of a series of rings, sliced by categories with each ring outward representing a deeper level in the hierarchy. The angle of each segment is proportional to the value (or number of members) within that segment. Although this does not offer a precise size comparison between the categories it allows to quickly identify notable segments within a complex, multi layered hierarchy.

![]({{site.baseurl}}/assets/img/Tableau_Part1/Sunburst.png)

[Source](https://learningtableaublog.files.wordpress.com/2016/07/screen-shot-2016-07-15-at-20-10-49.png)

**When to use this:** Sunburst are essentially hierarchical pie charts that adds a dimension of depth to each parent branch. For example, highlighting a particular month in a sales report by highlighting the uneven size of the segment and delving further into that month to gain more insights.

## Box and Whisker plot
Box plot shows a distribution of data and is one of the favourite graphs of statisticians. It is especially useful when a large number of observations are involved and to find potential outliers. It highlights the following values
· First quartile
· Median
· Third quartile
· Outliers

![]({{site.baseurl}}/assets/img/Tableau_Part1/Sunburst.png)

[Source](http://www.theinformationlab.co.uk/wp-content/uploads/2015/06/Box-and-whisker-2nd-dimension.png)

**When to use this:** The type of data you might depict as a histogram. It is useful in depicting the range between which most values lie and the ones that lie outside this range. For example, highlighting various nondiscretionary costs across factories in India to highlight unusually high labour costs to prepare a material.

## Steam graphs
This is a variation of the stacked area chart, which instead of plotting against a fixed axis, has values plotted against a varying central axis. It displays changes in data over time that resembles the flow of a river or stream. The size of the individual stream is proportional to the values in each category. The downsides of a steam graph is that the categories with smaller magnitude are not legible making it harder to read their values.

![]({{site.baseurl}}/assets/img/Tableau_Part1/Steamgraph.png)

[Source](http://www.thedataschool.co.uk/wp-content/uploads/2015/08/Sales-with-Dynamic-Dimensions-Overview1.jpg)

**When to use this:** They are ideal when depicting proportion or group size over time for large datasets, in-order to highlight trends and uncover patterns. Usually reserved for audience who do not spend time exploring data and want a general view and trend over a period. For example, highlighting seasonal trends of sales across categories.

### Benefits of custom visualization
In addition to providing an engaging and memorable experience, custom visualizations help in depicting data complexity clearly. Simplifying complicated information might not be the right answer at times. Rather, one should look to preserve the sophistication where warranted, which involves choosing visualizations that depict the depth of complexity.
There are other visualizations that one could explore such as coxcomb charts, Marimekko charts, Pareto charts and word clouds based on the user base and nature of the underlying data which will be explored in the next post.

#### *To be continued……*

Shoutout to Samiya Nasim for helping me put this together. Thanks Samiya!
