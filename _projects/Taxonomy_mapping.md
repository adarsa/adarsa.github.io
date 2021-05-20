---
layout: post
title:  "Taxonomy mapping"
date:   2020-04-01 12:06:43 +0530
image: 
  path: /assets/projects/RE/thumbnail.png
  thumbnail: /assets/projects/TaxonomyMapping/thumbnail.png
tags: [Search and recommendation, CI/CD, Document Similarity, Topic Modelling, Bertology, Graph Search, User Experience]
---

Search and discovery across a Sunbird instance requires establishing "equivalence" relationship between taxonomies in multiple languages and topics. This is enabled by creating and leveraging a central/reference taxonomy which is a superset of multiple individual taxonomies (Concept map in case of Diksha). 


For each instance of Sunbird, there is a Central/reference taxonomy which is a superset of multiple individual taxonomies (Table of Content - ToC in case of textbooks).   Specifically in Diksha usecase, in order to go from one textbook ToC  to another, required to forge a weighted "equivalence" relationship between one node in a ToC to a node in another ToC. The two ToCs can belong to different boards, grades, medium, etc. Thus, we call see aligning DTBs as aligning Taxonomies.

The core underlying problem in taxonomy alignment is scoring a set of topics on the basis of similarity to a new topic. Meaning, when a new textbook is added to the database, for each *Chapter* or *Topic*, required to find top N similar topics in the existing textbook. 

#### Objective:

Given a *textbook Topic* (for NCERT textbooks, a *Topic* is typically 170 sentences), find similarity score between all the other existing topics in DB and pick top **N** most similar topics. In the first phase, English textbooks are considered and other languages are mapped based on one-to-one correspondence with English medium textbooks of same Subject, Board and Grade.

<figure class="video_container">
  <video width="640" height="360" autoplay loop >
    <source src="/assets/projects/TaxonomyMapping/TOC-Linking.mp4" type="video/mp4">
  </video>
</figure>



Tools: ElasticSearch, Python, Sunbird ML-Workbench, AWS, REST, D3.js

