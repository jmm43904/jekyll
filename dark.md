---
layout: dark
title: dark
example: "Example text in this variable."
---

This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

{% include big-cat.html %}

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size}} animal.
{% endfor %}

## Large animals are the best!

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}-<small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## Small animals only

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}
