---
layout: archive
title: "Reads"
permalink: /reads/
author_profile: true
---

{% assign sorted_reads = site.reads | sort: "date" | reverse %}

{% for item in sorted_reads %}
### [{{ item.title }}]({{ item.url | relative_url }})

**{{ item.date | date: "%B %d, %Y" }}**
{% if item.author %} · {{ item.author }}{% endif %}
{% if item.type %} · {{ item.type }}{% endif %}

{{ item.content }}

{% if item.link %}
[Original source →]({{ item.link }})
{% endif %}

{% unless forloop.last %}
---
{% endunless %}
{% endfor %}