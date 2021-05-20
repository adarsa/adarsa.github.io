---
layout: post
title:  "Recommendation Engine"
date:   2016-07-01 12:06:43 +0530
image: 
  path: /assets/projects/RE/thumbnail.png
  thumbnail: /assets/projects/RE/thumbnail.png
tags: []
---

Built different recommendation engines (RE) for the Ekstep Genie App. The extensive project served as a testbench for evaluating different flavors of recommendation for Multimedia Content consumption (in Edtech) which later evolved to Sunbird and Diksha.

Objective:

On the consumption side, drive metrics :
- Time spent on content
- Number of visits to Content, Content sharing
- Proficiency of learner 
On the creation side, drive metrics:
- Portal Visit
- Creation of new content
- Coverage of concepts
- Quality of content

Tools: R, Python, Scala, C, Neo4j

#### A user - device factorisation machine
Identified target variable to *show content that a user is likely to Use more*.
Built a usage based RE for user-specific recommendation using libFM model. Usage metrics are fed in through summarisation data products and recommendation scores computed through cron jobs for scheduled batch processing.

#### End of Content RE
An NLP task of Document Recommendation involves recommending n similar documents for a given document. Every Content is parsed and a text embedding is computed. Similarity scores are computed through scheduled batch processing. 

#### Authoring tool RE
Build an orchestration layer on the graph database to interpret recommendations through graph queries. This was aimed at recommending 'right' assets to Content creators in the authoring tool portal.

An evaluation pipeline was set up for monitoring the models and create performance reports. Retrieval ranking, Q score and feature exploration and monitoring dashboard where developed using Shiny  in R.