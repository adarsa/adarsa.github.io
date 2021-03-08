---
layout: post
title:  "Recommendation Engine"
date:   2016-07-01 12:06:43 +0530
image: 
  path: /assets/projects/RE/thumbnail.png
  thumbnail: /assets/projects/RE/thumbnail.png
tags: []
---

Built different recommendation engines (RE) for the Ekstep Genie App. The extensive project served as a testbench for evaluating different flavours of recommendation for Multimedia Content consumption (in Edtech) which later evolved to Sunbird and Diksha.


#### A user - device factorisation machine
User specific recommendation using libFM model. Usage metrics are fed in through summarisation data products and recommendation scores computed through scheduled batch processing.

#### End of Content RE
An NLP task of Document Recommendation that involves recommending n similar documents for a given document. Every Content is parsed and a text embedding is computed. Similarity scores are computed through scheduled batch processing. 

#### Authoring tool RE
Build a orchestraion layer on graph database to interpret recommendation through graph queries.

An evaluation pipeline was setup for monitoring the models and create performance reports.