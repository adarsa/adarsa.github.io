---
layout: post
title:  "ML as a Service"
date:   2020-05-20 12:06:43 +0530
image: 
  path: /assets/projects/MLasService/thumbnail.png
  thumbnail: /assets/projects/MLasService/thumbnail.png
tags: [ML as service, multimedia, Product design,Microservice Architecture, Topic modelling, Multilingual language model]
---

The existing pipelines in *Daggit* - Sunbird ML Workbench were rebundled into independent solutions for general usecases beyond Sunbird. This involved extending individual *DAG* nodes and operators as microservices and develop REST api's for *Daggit* tasks.

![Architecture diagram](/assets/projects/MLasService/architecture_diagram.png)

Different services developed:
- Profanity check for English and Hindi text
- Topic modelling for English and Hindi text
- Multimedia (Youtube, pdf) text extraction
- Keyword extraction for English text using DBpedia ontology 

Tools: REST, Python, Kafka

