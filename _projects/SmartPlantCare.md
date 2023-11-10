---
name: Smart Plant Care
tools: [C++, ESP32, InfluxDB, Grafana, HomeAssistant]
image: /images/projects/SmartPlantCare/SmartPlantCare.png
description: Creation of a homemade connected autonomous system for plant care
pinned: false 
release-date: 2023-05-01
weight: 2
---

# Smart Plant Care 

## Overview

The Smart Plant Care project is a homemade connected autonomous system designed to optimize plant care using innovative technologies. Utilizing an ESP32 microcontroller programmed in C, the system incorporates various sensors and smart features to ensure optimal growing conditions for plants.

## Architecture

#### Plant Sensors

The plant is equipped with a hygrometric sensor to measure soil moisture levels. If the moisture level is insufficient, an integrated pump waters the soil. Additionally, a light sensor assesses ambient light levels. If the light is insufficient during specific time intervals, a LED lamp is activated.

#### Data Transmission

Each sensor's data is transmitted via MQTT from the ESP32 to a Raspberry Pi located on the local network. To ensure secure communication with my remote storage servers, I have integrated the Raspberry Pi into a VPN network (specifically Tailscale). This setup allows for secure and monitored data transmission, ensuring control over the collected data.

#### Power Optimization

To enhance system efficiency, the ESP32 is programmed to operate in cycles of deep sleep every 10 minutes, conserving power while still maintaining regular monitoring intervals.

## Environmental Monitoring

In addition to plant metrics, I monitor the temperature and humidity in the room where the connected plants are located. Similar to the plant sensors, a DHT11 sensor connected to another ESP32 transmits this data via MQTT to the Raspberry Pi, which then securely forwards it to the remote servers via the VPN.

## Data Hosting and Visualization

All data sent to the servers is hosted in an InfluxDB database and visualized using Grafana. Home Assistant is employed to display comprehensive graphs, providing a centralized interface for monitoring all metrics.

## Aesthetic Design

To complement the technological aspects, the entire system is housed in a specially designed 3D-printed pot and pot cover, adding a touch of aesthetic appeal to the project.


<p class="text-center">
{% include elements/button.html link="https://github.com/Andreaj42/SmartPlantCare" text="GitHub Repository" %}
</p>
