---
layout: default
permalink: /
---

{% include landing.html %}

Latest project:
{% assign project_list = site.project | sort: "release-date" | reverse %}
{% assign project_counter = 0 %} {% for project in project_list %} {% if project_counter < 5 %}
{{ project.release-date | date: '%-d %B, %Y'}}: {{ project.info }}
{% assign project_counter = project_counter | plus: 1 %} {% endif %} {% endfor %}