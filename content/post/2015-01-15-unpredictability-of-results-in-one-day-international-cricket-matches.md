---
title: Unpredictability of results in One Day International cricket matches
author: Rajesh Korde
date: '2015-01-15'
slug: unpredictability-of-results-in-one-day-international-cricket-matches
categories:
  - Analysis
tags:
  - sports
  - entropy
---

Ask any fan of any sports team and they would claim their team to be the most unpredictable with no guarantee of any result on a given day. The glorious uncertainties of cricket have been extolled by many a commentator over the years. In this post, I do an analysis of One Day International results to see how unpredictability in cricket has fared over the years and finally answer the question: Which is the most unpredictable team in international cricket?

<!--more-->

But first, lets talk about a few rules for the analysis:

* Only ODI results were compared. So no tests or T20s.
* Results tallied are for all the matches up to Dec 20, 2014. However, for time series analysis, I only took results after 1980 to avoid noise. For unpredictability analysis, I only took results after 1975.
* Results considered were only for matches between the following countries:  Australia, England, India, New Zealand, Pakistan, South Africa, Sri Lanka, West Indies. I have nothing against other countries, its just that they have played enough matches to be able to do statistically significant analysis.

Right then. First, a simple analysis of how interestingness of ODIs results have changed over the year. How interesting was a match can usually be gauged by how many balls remained (if the team batting second won) or what was the run margin (if the team batting first won). The graphs below show the smoothed (using [loess](https://en.wikipedia.org/wiki/Local_regression)) trendlines of how this has changed over the years (the gray area indicates the Standard Error of the metric).

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/OverallRunMargin_wayudi.png">}}

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/OverallBallsRemaining_s6woau.png">}}

The graphs above show a disturbing trend. If the team batting first wins, the matches are getting to be more and more boring and predictable. I think this can be attributed to cricket being dominated by batsmen and larger and larger targets being set. When the team batting second wins, the matches tend to be more interesting. The split between whether team batting first or second wins is roughly 1:1. Also, 1985-1995 was probably the most interesting period in ODI cricket.

### Finding the most unpredictable cricket team

To find this, I had to first find a good measure for unpredictability. There are numerous algorithms for this, but after some research, I decided to go for [Sample Entropy](https://en.wikipedia.org/wiki/Sample_entropy), which is a more robust version of [Approximate Entropy](https://en.wikipedia.org/wiki/Approximate_entropy). Without further ado, here are the results

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/TeamEntropySummary2_pgifg1.png">}}

This probably confirms the suspicion of a lot of people, but Pakistan is the most unpredictable cricket team (and they are only getting more unpredictable). Following behind closely are South Africa and India. The difference between the three is small enough that it can be attributed to noise. On the other end of the spectrum, West Indies is becoming the most predictable team (although probably not in a good way). They are followed by Australia, who have been fairly predictable and continue to be so.

Here’s a scatter plot of Entropy with the winning percentages of the teams.

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/TeamEntropyScatterPlot_iuidqa.png">}}

### Unpredictability in team rivalries

The next logical question would be to find out which two rivalries are the most unpredictable. Unfortunately, most entropy algorithms require atleast 200-300 observations before they stabilize. So I had to settle for a more home grown solution. I created a metric that tracks the consistency of the results. So if the results keep changing over matches (eg WLWLWLWL), the team will have higher inconsistency or fluctuations and if the results are consistent over matches (eg WWWWLLLL), the team will have lower fluctuations. 

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/TeamResultFluctuationSummary_moz1q2.png">}}

As it turns out, Sri Lanka and England results tend to fluctuate a lot. Also (probably unsuprisingly), results from India matches seem to fluctuation a lot more than other teams.

Finally, I want to leave you with two graphs for India and how their Balls remaining and Run Margin has changed over the years.

{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721328/IndiaRunMargin_kh6uec.png">}}


{{< image classes="fig-100 center clear" src="https://res.cloudinary.com/rajkorde/image/upload/v1506721327/IndiaBallsRemaining_kou2nr.png">}}

