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

# History
{% assign jobs = site.employment | where: "display","true" | sort:"from" | reverse %}

{% for job in jobs %}
## {{ job.role }}, {{ job.company }}, {% include dates.html item=job %}
  {% assign engagements = site.engagements | where:"job",job.slug | reverse %}
  {% for engagement in engagements %}
### {{ engagement.role }}, {{ engagement.client}}
  <div class='engagement_time'>{% include dates.html item=engagement %}
  {% if engagement.duration %}({{ engagement.duration }}){% endif %}
  </div>
{{ engagement }}

  {% endfor %}
{% endfor %}
