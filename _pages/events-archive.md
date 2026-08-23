---
title: "Past events"
layout: single
permalink: /events/archive/
classes: wide
---

{% assign past = site.events | where_exp: "e", "e.date < site.time" | sort: "date" | reverse %}
{% assign recent = past | slice: 0, 4 %}
{% assign older = past | slice: 4, past.size %}

{% if recent.size > 0 %}
<div class="pyw-event-grid">
  {% for event in recent %}
    {% include event-card.html event=event variant="archive" %}
  {% endfor %}
</div>
{% endif %}

{% if older.size > 0 %}
  {% assign older_by_year = older | group_by_exp: "e", "e.date | date: '%Y'" %}
  {% for year in older_by_year %}
  <h3>{{ year.name }}</h3>
  <ul class="pyw-event-list">
  {% for event in year.items %}
  <li>
    <a href="{{ event.url | relative_url }}">{{ event.title }}</a>
    — {{ event.date | date: "%-d %B" }}
  </li>
  {% endfor %}
  </ul>
  {% endfor %}
{% endif %}