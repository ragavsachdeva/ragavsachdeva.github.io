---
layout: page
permalink: /doodles/
title: doodles
nav: true
---

<div class="news">
  {% if site.doodles  %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {% assign news = site.doodles | reverse %}
      {% for item in news limit: site.news_limit %}
        <tr>
          <th scope="row">{{ item.date | date: "%d %b, %Y" }}</th>
          <td>
            {% if item.inline %}
              {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% else %}
              <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
          </td>
        </tr>
      {% endfor %}
      </table>
    </div>
  {% else %}
    <p>No doodles to show...</p>
  {% endif %}
</div>

