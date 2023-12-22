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
years: [2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015]
social: true
nav: false
nav_order: 3
---

An up-to-date list is available on [Google Scholar](https://scholar.google.com/citations?hl=en&user=C6BNYB0AAAAJ&view_op=list_works&sortby=pubdate).

<div class="publications">

{%- for section in page.sections %}
  <a id="{{section.text}}"></a>
  <p class="bibtitle">{{section.text}}</p>
  {%- for y in page.years %}

    {%- comment -%}  Count bibliography in actual section and year {%- endcomment -%}
    {%- capture citecount -%}
    {%- bibliography_count -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] -%}
    {%- endcapture -%}

    {%- comment -%} If exist bibliography in actual section and year, print {%- endcomment -%}
    {%- if citecount !="0" %}

      
      {% bibliography -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] %}

    {%- endif -%}

  {%- endfor %}

{%- endfor %}

</div>