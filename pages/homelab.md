---
layout: page
title: HomeLab
permalink: /homelab/
weight: 3
---

# HomeLab
My HomeLab is a personal infrastructure environment where I experiment with virtualization, networking, system administration, and self-hosted services.

## Architecture
My HomeLab runs on a virtualized Proxmox infrastructure hosting several internal services and development workloads.

### Remote Access
Remote administration is centralized through a dedicated bastion VM. The bastion is reachable through a private Tailscale network and acts as an SSH jump host for controlled access to internal workloads.

{% include homelab/homelab-architecture.html %}

### Workload Distribution

Services and workloads are distributed according to their role. The R730 hosts the primary virtualized workloads, while the R720 provides a separate backup and recovery target.

{% include homelab/homelab-workloads.html %}

## Infrastructure & Technologies

My HomeLab serves as a practical environment for experimenting with virtualization, networking, system administration and self-hosted services.

- **Virtualization:** Proxmox VE, virtual machines and containers
- **Systems:** Debian, Linux administration
- **Networking:** Tailscale, SSH, private networking
- **Remote access:** Bastion host and SSH jump host
- **Automation:** CI/CD runners and infrastructure automation
- **Monitoring:** Service availability and infrastructure monitoring

## Self-Hosted Services

I use my HomeLab to deploy and maintain several services for development, experimentation and infrastructure management.

- **<a href="https://github.com/actions/runner"> GitHub Actions Runners </a>** — Self-hosted CI/CD workloads
- **<a href="https://www.sonarsource.com/products/sonarqube/"> SonarQube </a>** — Static analysis and code quality
- **<a href="https://uptime.kuma.pet/"> Uptime Kuma </a>** — Service monitoring and availability

## Hardware

| Device | Role | CPU | Memory | Storage | Network |
|---|---|---|---|---|---|
| **Dell PowerEdge R730** | Compute / Virtualization | 2 × Xeon E5-2650L v4 (14 cores, 1.70 GHz) | 64 GB DDR4 | 6 TB SSD, 250 GB NVMe SSD | — |
| **Dell PowerEdge R720** | Backup / Storage | 2 × Xeon E5-2609 (4 cores, 2.40 GHz) | 72 GB DDR3 | 2 TB SSD | — |
| **Raspberry Pi 4 Model B** | Monitoring | Quad-core Cortex-A72 (ARMv8), 1.8 GHz | 4 GB | 32 GB | — |
| **Dell PowerConnect 2848** | Network switch | — | — | — | 48 × GbE, 4 × SFP |



## Acknowledgements

Special thanks to **Lucas Perfeito** for his valuable help in building, configuring, and maintaining this HomeLab.


<!--
## 3D Printers
**Creality Ender 3 Pro**
- Remote-controlled by a Rasberry Pi


# Software

## Operating Systems
- **Proxmox VE 8.0**: A free virtualization solution based on the Linux hypervisor KVM, it also offers a container solution with LXC.
- **OctoPi 1.0.0**: A Debian image for the Raspberry Pi that already includes OctoPrint and MJPG-Streamer for live viewing of prints and timelapse video creation.

## Self-Hosted Tools

I've set up and maintained a collection of self-hosted tools on my Homelab. These tools have not only empowered me to streamline various tasks but have also fostered collaborative work and resource optimization.

- **JupyterHub**: I've deployed a <a href="https://jupyter.org/hub">JupyterHub</a> on my Homelab, which allowed me to offload computational tasks from my personal computer during coursework. It also facilitated collaboration with colleagues.
- **Pi-hole**: It serves as a network-wide ad blocker, effectively blocking unwanted ads across all devices on my home network. Furthermore, <a href="https://pi-hole.net/">Pi-hole</a> offers local DNS resolution management, enhancing security and privacy while maintaining a fast and efficient DNS resolution process.
- **GitHub Runners**: These runners empower my continuous integration and deployment (CI/CD) workflows, allowing me to build, test, and deploy my projects with speed and flexibility. By running these runners on my Homelab, I have greater control over my development pipeline, ensuring resource optimization for my projects.
- **SonarQube**: A static code analysis tool that helps me maintain code quality by identifying code smells, bugs, and security vulnerabilities. By hosting <a href="https://www.sonarsource.com/products/sonarqube/"> SonarQube </a> on my Homelab, I can continuously monitor and improve the quality of my software projects, ensuring they meet the highest standards.
- **Uptime Kuma**: A monitoring tool that helps me track the availability and performance of websites and services. By hosting <a href="https://uptime.kuma.pet/"> Uptime Kuma </a> on my Homelab, I can receive alerts and notifications in case of downtime.


## Other Tools
- **Tailscale**: For seamless and secure remote access to my home network, I use on <a href="https://tailscale.com/">Tailscale</a>, a versatile and user-friendly VPN solution. By incorporating Tailscale into my network infrastructure, I've gained the flexibility and reliability needed to stay connected and in control, regardless of my physical location.
<!-- Cloudflare -->
