---
name: Moodle Scraper
tools: [Python]
image: /images/projects/Moodle/Moodle.png
description: Alerting system to track new grades on Moodle
release-date: 2023-01-01
weight: 1
---

# The Moodle Alert Project

The Moodle alert project is a collaborative initiative between me and my classmate <a href = "https://fr.linkedin.com/in/lucas-perfeito"> Lucas Perfeito</a>. Using web scraping on our school's Moodle website, we've set up an alert system, via Discord or by e-mail, to inform our classmates when a new note is added or modified. The script used for this project is hosted on our own servers and executed using services systemd.


### Mail alert sample
![notify](/images/projects/Moodle/mail.png)

### Discord alert sample
![notify](/images/projects/Moodle/discord.png)


<p class="text-center">
{% include elements/button.html link="https://github.com/Andreaj42/Moodle-Grades-Scraper" text="GitHub Repository" %}
</p>