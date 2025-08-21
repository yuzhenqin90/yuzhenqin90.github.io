---
layout: page
permalink: /publications/
title: Publications
description: 
sections:
  - bibquery: "@article"
    text: "<h1>Journal Articles</h1>"
  - bibquery: "@inproceedings"
    text: "<h1>Conference and Workshop Papers</h1>"
  - bibquery: "@preprints"
    text: "<h1>Preprints</h1>"
social: true
nav: true
nav_order: 3
---

An up-to-date list is available on [Google Scholar](https://scholar.google.com/citations?hl=en&user=C6BNYB0AAAAJ&view_op=list_works&sortby=pubdate).

<div class="publications">
{%- for section in page.sections %}
  <a id="{{section.text}}"></a>
  <p class="bibtitle">{{section.text}}</p>

  {% bibliography -f {{site.scholar.bibliography}} -q {{section.bibquery}} --sort=year:desc --reversed %}

{%- endfor %}


</div>
