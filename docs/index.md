---
title: Script Library
layout: default
---

# Script & Tool Library

{% assign groups = "vba,powerquery,tool" | split: "," %}
{% for g in groups %}
## {{ g | upcase }}
{% assign items = site.items | where: "category", g | sort: "title" %}
{% for it in items %}
<details>
  <summary><strong>{{ it.title }}</strong></summary>
  {% if it.source %}- Source: <a href="{{ it.source }}">{{ it.source }}</a><br>{% endif %}
  {% if it.download %}- Download: <a href="{{ it.download }}">download</a>{% endif %}

  {{ it.content }}
</details>
{% endfor %}
{% endfor %}
