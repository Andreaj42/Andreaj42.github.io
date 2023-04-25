---
layout: default
permalink: /
---

{% include landing.html %}

Latest projects:
{% assign projects_list = site.projects | sort: "release-date" | reverse %} 
{% assign projects_counter = 0 %}
{% for projects in projects_list %} 
{% if projects_counter < 5 %}
{{ projects.release-date | release-date: '%-d %B, %Y'}}: {{ projects.name }}
{% assign projects_counter = projects_counter | plus: 1 %} {% endif %} {% endfor %}