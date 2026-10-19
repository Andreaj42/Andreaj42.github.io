---
name: Calliope
title: Calliope
description: AI-assisted scientific literature monitoring and paper recommendations.
tools: [Python, Ollama, Docker]
weight: 2
permalink: /projects/calliope/
---


# Calliope

*Calliope is an AI-assisted scientific literature monitoring tool designed to streamline the research discovery process.*

## Motivation

Keeping up with the rapidly growing scientific literature is a recurring challenge in academic research.

Calliope automates the collection and evaluation of scientific papers, helping researchers identify relevant publications based on their research interests.

## How It Works

Calliope follows a simple automated workflow:

1. Collects scientific papers from Google Scholar email alerts.
2. Evaluates their relevance using a locally hosted LLM.
3. Generates a ranked digest of selected publications.
4. Delivers the results by email.

## Technologies

Python, Ollama, IMAP, Docker, and Linux systemd.


## Source Code

The project is available on [GitHub](https://github.com/Andreaj42/Calliope).
