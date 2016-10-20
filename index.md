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

# Achievements

{% assign achievements = site.achievements | where:"display","true" %}
{% for a in achievements %}
* {{ a }}
{% endfor %}
