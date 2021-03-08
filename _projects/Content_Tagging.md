---
layout: post
title:  "Content Tagging"
date:   2019-12-15 12:06:43 +0530
image: 
  path: /assets/projects/ContentTagging/thumbnail.png
  thumbnail: /assets/projects/ContentTagging/thumbnail.png
tags: [ML as service, multimedia, Product design, Keyword Extraction, Taxonomy, DBpedia, BERT, LSTM]
---

Developed BERT based model to *tag* multimedia Content (youtube,webm, pdf, html, ecml) in multiple languages. Designed the architecture and lead the backend development in integrating the tags into Content Search for better discoverability of 65k+ Content for 150M+ app users.

[Diksha](https://diksha.gov.in/) is the largest Edtech platform in India that host 65K Content in 15 different langugaes with a userbase of 150M+ students. Given the scale, Content creation and consumption are two of the most important components of the platform.

- *Reuse* of an appropriate existing Content by a teacher looking to cover a specific topic eases Content/course creation. Reuse also reduces onboarding time for ETB usecase (view content linked to the QR
code printed in textbook using the mobile app). This is enabled by building a semantic search.

- Tagging a Content with the right *Textbook topic*, *Grade*, *Board*, *Medium* of instruction is important for its discoverability by Students/Content consumer.

Both search and discovery hence require tagging a multimedia Content puplished on the platform to right textbook topics/*Concepts* in addition to other tags provided by the author such as *Grade*, *Board*, *Medium*. A pipeline was designed for the purpose that gets triggered through a Content publish (Kafka) event and writes back to Content meta in ElasticSearch. The major components of design are listed here:

1. A multimendia parsing pipeline for multiligual Content. 
2. A taxonomy of keywords extracted from different textbooks with a confidence score for different keywords computed using DBpedia ontology.
3. A scalable biLSTM based similarity scoring model between parsed Content and textbook taxonomy to tag Content to textbook keywords.
4. Extending platform Search api for semantics search using pretrained BERT embeddings of computed Content keywords

The pipeline is open sourced as part of *Daggit*: 

- [Content/Textbook keyword extraction pipeline](https://github.com/project-sunbird/sunbird-ml-workbench/blob/master/examples/content_tagging/content_tagging.yaml)
- [Content to Textbook tagging](https://github.com/project-sunbird/sunbird-ml-workbench/blob/master/examples/content_reuse/textbook_to_concept_mapping.yaml)
