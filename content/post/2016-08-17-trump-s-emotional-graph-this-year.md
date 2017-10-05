---
title: Trump's emotional graph this year
author: Rajesh Korde
date: '2016-08-17'
slug: trump-s-emotional-graph-this-year
categories:
  - Analysis
tags:
  - sentiment analysis
  - politics
---

Last week, David Robinson published an [excellent analysis](http://varianceexplained.org/r/trump-tweets/) of Trump’s tweets. Given below is a relatively straightforward extension of his work where I plot various emotions in Trump’s tweets over time. Each line is smoothed to remove noise. The y-axis is proportion of a given sentiment in all tweets sent per week. The sentiments were calculated using the [NRC word-emotion lexicon](http://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm). The tweets considered here are limited to ones sent from Android because David’s analysis showed that Trump most likely only tweets from his Android phone.

<!--more-->

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506723785/TrumpTweetsCairo_dkvj89.png">}}

It seems like something pivotal happened in mid-may when several sentiments start changing their direction. This could be related to the fact that Trump became the presumptive nominee in the first week of May and Trump changed his focus from primaries to the presidential election. Few points that jump out:

* Sharp upward trend in anger and especially in negativity since mid-may.
* Decline in positivity,  joy and trust after a bump around mid-may.
* Honestly no idea what’s going on with surprise.

Many thanks to [David Robinson](http://varianceexplained.org/) again for doing majority of the heavy lifting here and publishing the code. My code is available [here](https://github.com/rajkorde/RTestCode/blob/master/Scripts/drob_twitter_trump.R).