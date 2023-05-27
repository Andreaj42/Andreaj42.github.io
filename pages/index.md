---
layout: default
permalink: /
---

{% include landing.html %}

<div style="font-size: 18px; color: #333; font-weight: bold; padding-bottom: 10px;">Latest projects:</div>
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

<div style ="padding-top :80%; position = relative; overflow : hidden;">
    <iframe style =" position: absolute; top: 0; left: 0; width: 100%;  height: 100%; border: 0;"
        src="https://www.google.com/maps/d/embed?mid=1IDVrNma3ORrPVoXOg7vDJWTnHwe65z0&output=embed&ehbc=2E312F">
    </iframe>
</div>
