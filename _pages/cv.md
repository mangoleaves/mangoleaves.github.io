---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
**Ph.D. Student**, School of Artificial Intelligence and Data Science, University of Science and Technology of China, 2021.9 - Now.  
**Bachelor**, School of the Gifted Young, University of Science and Technology of China, 2017.9 - 2021.6.

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
