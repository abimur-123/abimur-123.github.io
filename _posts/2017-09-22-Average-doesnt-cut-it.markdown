---
layout: post
title: When average does not cut it - Simpson's Paradox
date: 2017-09-22 00:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: Simpsons.jpg # Add image post (optional)
tags: [Statistics, Trends] # add tag
---

Let's suppose you go to a doctor to consult regarding treatment for your kidney stones. The doctor tells you that you have two options - a state of the art and new clinically approved treatment B and the old traditional treatment A which your grandad probably had. You then proceed to ask the pros and cons of both the treatment and the doctor says, "So a recently conducted study found that treatment A has a higher probability of success and is hence better than treatment B"

I'm sure if you're like most people you say, "I'll go with treatment A, thank you!"


![]({{site.baseurl}}/assests/img/Borat_thumbs_up.jpg)
Image source from https://imgflip.com/memetemplate/24895147/Borat-Thumbs-Up

But then your doctor stops you to say, "The same study also observed which treatment worked better depending on whether the patient had large or small kidney stones." Now you're confused if you have large or small kidney stones and proceed to question the doctor regarding the same to which the doctor says, " At the end of the day it actually doesn't matter. The study found treatment B to have a higher probability
of success when compared to treatment A irrespective of which one you're suffering from."

Now you're confused and left wondering what you just heard/read about.

![]({{site.baseurl}}/assests/img/george_tense_optimistic.jpg)
Image source from https://pbs.twimg.com/profile_images/1606408825/RShea_400x400.jpg

Guess what? It's actually true! An actual study that was conducted comparing the success rates of 2 treatments - treatment A, which is the open surgical procedure and treatment B, which is percutaneous nephrolithotomy (small puncture surgery) had the
following figures -

|                  | **Treatment A**   | **Treatment B**   |
|------------------|-------------------|-------------------|
| **Small Stones** | Group 1 -  93% (81/87)       | Group 2 - 87% (234/270)     |
| **Large Stones** | Group 3 - 73% (192/263)     | Group 4 - 69% (55/80)       |
| **Both**         | **78% (273/350)** | **83% (289/350)** |

The table clearly shows Treatment A works better for Small stones as well as large stones but at the end of the day Treatment B has a better success rate! This phenomenon is known as **Simpson's paradox**. I'll pause for a while so that you can add up the numbers to verify and let this table sink in.

## **What is Simpson's paradox?**

Simpson's paradox is shocking the first time you meet it or hear about it. A bit like Donald Trump I would say. It is not a mere oddity or exception that you'll find.

> Simpson or the Simpson-Yule paradox essentially states that a trend/correlation which appears in different groups of data either reverses or disappears when these groups are combined.

Most explanations have 2 variables - the explained and the *observed* explanatory variable, but what most people don't realize is often there is a third *lurking* explanatory variable which impacts the results as well. When the effect of the observed explanatory variable on the explained variable changes direction or disappears when the *lurking* variable is accounted for is when you have a Simpson's paradox.

#### **So what was the *lurking* variable in the kidney stone problem?**

It is the *severity* of the case. Doctor preferred to go with treatment B for less severe cases, which was not previously considered as important until the effects were included.

Simpson's paradox occurs in the above example for 2 reasons -
1. Size of the groups combined is different when the lurking variable is ignored. Groups 2 and 3 dominate as doctors prefer treatment A for severe cases and B for less severe cases.
2. Lurking variable severely impacts the ratios. It is affected more by the severity of the case rather than the treatment. This is why the ratio is bad when Large Kidney stones are treated with B rather than A.

Based on this a paradoxical result seems to arise by downplaying the severity of the case in the analysis.  

A mathematical representation for the above case -

$a/b < A/B$

$c/d < C/D$

$(a+c)/(b+d) > (A+C)/(B+D)$

where $a,b,c,d,A,B,C,D$ are numbers.

This is the *Simpson's Reversal of Inequalities*. The arithmetic inequalities which are based on this:

$81/87 > 234/270$

$192/263 > 55/80$

$273/350 < 289/350$

Hence it is not right to conclude that relations between ratios or percentages when data are grouped together or pooled will conform to the same inequalities that were observed in the partitions of the data.

## **Why does it matter?**

Simpson's paradox usually deceives us on the results of a test. Advocating incorrect treatment(treatment B in the above case) based on a combined dataset without considering the lurking variable could result in serious ramifications like the death of the patient!

Another famous example involves batting averages. It is possible for one player to have a better batting average than an another player each year for a number of years, but to have a lower average when the seasons are combined. In professional baseball, this was observed when the batting averages of Derek Jeter and David Justice was calculated in 1995 and 1996.

It can be disconcerting to imagine that what we believed was a causal relationship between 2 variables actually does not exist or worse is found to be opposite once we find the lurking variable.

## **How does one recognize Simpson's paradox?**

The explanation for the Simpson's paradox sounds relatively simple but it is difficult to find when it will occur. In research, where participants are randomly distributed, Simpson's paradox will not occur as there are no lurking variable which explains how the distribution has occurred but in case of a non-randomized assignment, Simpson's paradox can be avoided if certain conditions are met but it is hard to find out and understand what these conditions/ variables are beforehand.

## **References**

1. https://en.wikipedia.org/wiki/Simpson%27s_paradox
2. https://plato.stanford.edu/entries/paradox-simpson/
3. Title inspiration - https://www.brookings.edu/blog/social-mobility-memos/2015/07/29/when-average-isnt-good-enough-simpsons-paradox-in-education-and-earnings/
4. http://vudlab.com/simpsons/
