---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---


{% comment %} 
Group research posts by “type” (e.g., Working Papers, Work in Progress). 
You can add more categories as needed.
{% endcomment %}
{% assign grouped = site.research | group_by: 'type' %}

{% for group in grouped %}
## {{ group.name }}

{% assign posts = group.items | sort: 'order_number' %}
{% for post in posts %}
### {{ post.title }}

{% if post.coauthors %}
<div class="coauthors"><em>{{ post.coauthors }}</em></div>
{% endif %}

<div class="abstract">
  {{ post.abstract | markdownify }}
</div>

{{ post.content | markdownify }}

{% if post.links %}
{% for link in post.links %}
- [{{ link.label }}]({{ link.url }})
{% endfor %}
{% endif %}

{% endfor %}
{% endfor %}
