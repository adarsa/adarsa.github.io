---
layout: post
title:  "Search Relevancy"
date:   2017-10-23 08:00:00 +0530
categories: python
tags:
  - Information retrieval
  - Recommendation engine
  - Explainability
  - Design thinking
---

From being reminded to restock grocery based on your current exercise routine to telling your child what Content to use to learn algebra, our lives are increasingly governed by Information retrieval (IR) systems  (search/recommendation engines).

Hence a view into accountability and explainability in non-technical terms is increasingly becoming important and being discussed in the Machine Learning (ML) community. In addition to explainability, understanding its *effectiveness* and evaluating them is also important not just for Users but all the more for ML system designers and businesses. 

This article tries to understand the evaluation of  IR systems.

> #### Efficiency: How accurately does the system perform on a test data?

In ML based approaches, efficiency translates to model accuracy or other performance measures. With a test sample accuracy or cross-validation techniques, one can compute the efficiency of the system and this may be continuously evaluated and improved through better indexing, reinforcement learning, etc.

> #### Effectiveness: Are the results relevant?

A measure for effectiveness is more subjective than efficiency.  

When building a search/recommender system, we can capture it in two ways:

1. Plan/design to solicit manual feedback from users: Asking the user to rate the results produced by the algorithms

2. Defining *Implicit feedback* KPI's, based on the User’s natural interaction with the system. While this could be a generalized approach, on the flip side, it can particularly be prone to biases, such as *position bias*.

In both, cases integration of this feedback back into the recommendation system requires first to determine the *features* to measure it. An example of the most common measure is the click-through rate.

#### Click-Through Ratio (CTR):
CTR is defined as the ratio of users who click on specific *Content* to the number of total users to whom it was recommended.

CTR can be calculated for individual Content as defined above or for a pair of Content. Pairwise CTR for C1 - C2 is the number of times C1 was clicked when it was recommended for a user who previously viewed C2. Such a measure would be relevant in the case of an end-of-Content recommendation scenario.

It should be noted that integrating such features introduces the biases that come along with it. Some key factors for this are:

- No negative feedback: it is hard to reliably infer which items a user did not like 

- Inherently noisy: Numerical value of explicit feedback indicates a preference, whereas the numerical value of implicit feedback indicates confidence

Hence, implicit feedback for usage-based RE would promote “winner-take-all” and “irrational herding” behaviors in which, similar items receive widely different numbers of recommendations and the system being unable to distinguish high and low-quality Content.


Hence, in building an IR system, there should be a focus on:

1. Extensive feature engineering, with emphasize on measuring and evaluating different parameters that influence user choice

2. Setting up a pipeline that will allow continuous evaluation of the decided feature as well as allow A/B testing of different hypotheses over time.

3. Integrate the parameters into the recommendation/search model


### References:

[1] [Estimating the causal impact of recommendation systems from observational data](http://jakehofman.com/inprint/amazonrecs.pdf)

[2] [Effects of Position Bias on Click-Based Recommender Evaluation](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/ecir-2014-hofmann-effects.pdf)