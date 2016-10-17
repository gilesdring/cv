---
layout: default
profile: base
---

# Profile

{{ site.profile | where: "slug",page.profile }}

# Expertise

{% assign expertise = site.expertise | where:"display","true" %}
{% for e in expertise %}
* {{ e }}
{% endfor %}
