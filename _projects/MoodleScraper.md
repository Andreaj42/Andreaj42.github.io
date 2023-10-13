---
name: Moodle Grades Scraper
tools: [Python, Docker, MariaDB]
image: /images/projects/Moodle/Moodle.png
description: Alerting system to track new grades on Moodle
release-date: 2023-01-01
weight: 3
---

# Moodle Grades Scraper

The Moodle Grades Scraper project is a collaborative initiative between me and my classmate <a href = "https://fr.linkedin.com/in/lucas-perfeito"> Lucas Perfeito</a>. Using web scraping on our school's Moodle website, we've set up an alert system, via Discord or by e-mail, to inform our classmates when a new note is added or modified. The script used for this project is hosted on our own servers.

This project is designed with Python, Docker and MariaDB. Alerts can be send by e-mail or with Discord notifications (via a webhook), as shown in the following images.

![notify](/images/projects/Moodle/discord.png)

![notify](/images/projects/Moodle/mail.png)


<p class="text-center">
{% include elements/button.html link="https://github.com/Andreaj42/Moodle-Grades-Scraper" text="GitHub Repository" %}
</p>
