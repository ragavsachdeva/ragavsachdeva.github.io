---
layout: page
permalink: /research/
title: research
description:
years: [2020]
nav: true
---

For a (potentially) more comprehensive list of publications see <a href="https://scholar.google.com/citations?user=js1EQ8oAAAAJ&hl=en&oi=ao" target="blank">Google scholar</a>.

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>

