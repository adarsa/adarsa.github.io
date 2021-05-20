---
layout: post
title:  "Mugal art the Python way"
date:   2020-05-20 12:06:43 +0530
categories: python
tags:
  - Jali
  - Turtle graphics
  - Symmetry
  - Architecture
  - Python
---

From the megalithic temples of Malta to indulgent study of symmetric proportions by the likes of Vitruvius and Da Vinci to the current study of hemispheres of the brain by neuroscientists, our fascination and emotional pleasure from symmetric structures and ordered geometric shapes is undeniable. 

This fascination is reflected in architectures around the world spanning millennia. One such example is Jali (from *Jala* in Sanskrit, *Jalaka* in Hindi) described in ancient Indian architecture texts and popularised through the Mugal architecture.  While originally carved in stone with much diligence, drawing them on paper with the ruler and protractors is a much satisfying endeavor, maybe similar to the therapeutic use of Mandala art today (I haven't tried one myself yet!), but maybe more exciting if you love geometry. 

After spending an hour drawing the neatly stacked nonagon on paper, I decided to program it. After all, it is an iterative process of moving from one point in space to another with a fixed set of rules. 

![Paper drawing](/assets/posts/mugal_art_and_python/image1.jpg)

Turtle graphics on Python seemed the right tool.
(Fun Fact: Turtle was part of the original Logo programming language developed by Wally Feurzeig, Seymour Papert, and Cynthia Solomon in 1967.)

What I needed to replicate the pattern from paper was a combination of 9-sided regular polygon and 6-sided regular polygon. Some iterations until the Jala was perfected:

#### 4-sided regular polygon
<figure class="video_container">
  <video width="400" height="300" autoplay loop >
    <source src="/assets/posts/mugal_art_and_python/video1.mp4" type="video/mp4">
  </video>
</figure>

#### Stacked 9-sided regular polygon
<figure class="video_container">
  <video width="600" height="340" autoplay loop >
    <source src="/assets/posts/mugal_art_and_python/video2.mp4" type="video/mp4">
  </video>
</figure>


And Finally:
#### Mosaic, of 9-sided regular polygon and 6-sided regular polygon
<figure class="video_container">
  <video width="800" height="360" autoplay loop >
    <source src="/assets/posts/mugal_art_and_python/video3.mp4" type="video/mp4">
  </video>
</figure>

Wandering further into the edges of symmetry, it is fascinating how pentagonal (5-sided) and decagonal (10-sided) *Girih-tile* pattern (an aperiodic tilling similar to famous *Penrose tiling* ) is found in  Darb-i Imam shrine, Iran, built-in 1453 C.E. Seems the architects found it in aesthetics before mathematicians formulated it!
