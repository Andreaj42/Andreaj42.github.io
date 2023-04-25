---
layout: default
permalink: /
---

{% include landing.html %}

<div class="newstitle"> Latest projects:</div>
{% assign projects_list = site.projects | sort: "release-date" | reverse %}

<ul>
{% assign projects_counter = 0 %}
{% for projects in projects_list %} 
    {% if projects_counter < 5 %}
        <li><b>{{ projects.release-date | date: '%-d %B, %Y'}} :</b> {{ projects.name }}, {{ projects.description }} </li>
        {% assign projects_counter = projects_counter | plus: 1 %} 
    {% endif %} 
{% endfor %}
</ul>