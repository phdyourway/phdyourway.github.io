---
# title: "Events"
layout: single
permalink: /events/
classes: wide
---


{% assign upcoming = site.events | where_exp: "e", "e.date >= site.time" | sort: "date" %}

<h1>Up Next...</h1>
{% if upcoming.size > 0 %}
  {% assign featured = upcoming.first %}
  {% assign rest = upcoming | slice: 1, upcoming.size %}

  <!-- Featured / next event -->
  <div class="pyw-event-featured">
    {% include event-card.html event=featured %}
  </div>
  
  <h2>Also Coming up...</h2>
  <!-- Grid of remaining upcoming events -->
  {% if rest.size > 0 %}
  <div class="pyw-event-grid">
    {% for event in rest %}
      {% include event-card.html event=event %}
    {% endfor %}
  </div>
  {% endif %}
{% else %}
  <p>No upcoming events right now — check back soon, or see our <a href="{{ '/events/archive/' | relative_url }}">past events</a>.</p>
{% endif %}

<p><a href="{{ '/events/archive/' | relative_url }}">View the archive →</a></p>