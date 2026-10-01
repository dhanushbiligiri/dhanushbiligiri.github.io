---
layout: archive
title: "News"
permalink: /news/
author_profile: true
---

{% assign sorted_news = site.news | sort: "date" | reverse %}

{% for item in sorted_news %}
### [{{ item.title }}]({{ item.url | relative_url }})

**{{ item.date | date: "%B %d, %Y" }}**

{{ item.content }}

{% unless forloop.last %}
---
{% endunless %}
{% endfor %}