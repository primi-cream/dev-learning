---
layout: page
title: "📂 카테고리별 학습 정리"
permalink: /categories/
---

{% for category in site.categories %}
  - [{{ category | first }}]({{ site.baseurl }}/categories/{{ category | first }}/)
{% endfor %}
