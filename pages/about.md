---
layout: page
title: About
permalink: /about/
weight: 3
---

# **About Me**

Hi I am **{{ site.author.name }}**,<br>
I am currently a student at Télécom Saint-Etienne, specializing in data engineering. At the same time, I work as a digital development support in a Michelin factory.

<div class="row">
{% include about/skills.html title="Programming" source=site.data.programming-skills %}
{% include about/skills.html title="Data Analysis" source=site.data.data-analysis-skills %}
{% include about/skills.html title="Other" source=site.data.other-skills %}
</div>

<div class="row">
{% include about/timeline.html %}
</div>