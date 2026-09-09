---
layout: single
classes: wide
sidebar:
    nav : "resources"
title: "Map of UK Maths PhD Opportunities"
nav_order: 3
toc: false
read_time: false
related: false
hide_meta: true
updated: 2026-09-09
---

<em><small>We hare in the process of collecting the information below about the Universities in the UK which are currently accepting PhD students in the Mathematical Sciences. This information is accurate to the best of our knowledge, but please always confirm things with the institution and do your own research. If you would like to provide information on your university please [get in contact](/contact/). To see all the universities below head to [this page](/resources/phd/maths/applying-maths/all-universities/), or for side-by-side comparisons head [here](/resources/phd/maths/applying-maths/uni-comparison/).</small></em> 

<h2 class="pyw-section__title">Map of UK Maths PhD</h2>
<p class="pyw-legend">
<span class="pyw-legend__label">Colour key:</span>
{%- for a in site.data.research_areas -%}
<span style="color: {{ a.colour }}" title="{{ a.label }}">{{ a.short | default: a.label }}</span>{% unless forloop.last %} &middot; {% endunless %}
{%- endfor -%}
</p>

{% include uni-map.html %}




