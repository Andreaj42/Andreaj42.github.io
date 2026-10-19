---
name: CorteXforge
title: CorteXforge
description: Automated generation of real-world RF datasets using the SLICES-RI/CorteXlab testbed.
tools: [Python, GNU Radio, CorteXlab]
weight: 1
permalink: /projects/cortexforge/
---

# CorteXforge

*CorteXforge is an open-source framework for generating realistic and reproducible radio frequency (RF) datasets through controlled over-the-air (OTA) experiments on the [SLICES-RI/CorteXlab](https://cortexlab.fr/) testbed.*

## Motivation

Deep learning for RF signal characterization relies heavily on annotated datasets. However, synthetic datasets cannot fully reproduce real-world hardware impairments and propagation effects, while uncontrolled RF measurements often lack precise annotations and reproducibility.

**CorteXforge bridges this gap** by combining the experimental control of synthetic data generation with the physical realism of OTA acquisitions.

## How It Works

CorteXforge follows a scenario-based approach: users describe the desired RF environment, and the framework automatically translates it into executable experiments.

The workflow is organized into three main stages:

### 1. Scenario Generation — Planner

The **Planner** converts a high-level experiment configuration into two files:

- `scenario.yaml`: defines the participating SDR nodes and their roles (transmitter, receiver, or synchronization node).
- `timeline.csv`: describes the scheduled transmissions, including modulation, symbol rate, carrier frequency, amplitude, and timing.

Signal parameters can be sampled from user-defined candidate sets, with a fixed random seed for reproducibility. The scheduler also supports overlapping transmissions and multi-emitter scenarios.

### 2. Experiment Execution — Forge

The **Forge** deploys and executes the generated scenario on the CorteXlab testbed using GNU Radio.

Each transmitting node generates and transmits its scheduled waveforms, while receiving nodes acquire the corresponding complex I/Q samples.

To coordinate distributed execution, CorteXforge combines a software synchronization barrier with the hardware timing infrastructure provided by CorteXlab.

#### Node Synchronization

Before starting an experiment, each node reports its readiness to a dedicated synchronization node. Once all participants are ready, a `GO` signal releases the nodes, which then use their synchronized hardware clocks to align transmissions and acquisitions.

{% include research/cortexforge/node-synchronization.html %}

### 3. Dataset Generation

The recorded I/Q samples are exported using the **SigMF (Signal Metadata Format)** standard, together with detailed annotations.

These annotations include:

- **Signal parameters:** modulation, symbol rate, carrier frequency, and bandwidth.
- **Temporal information:** transmission start and duration.
- **Experimental configuration:** transmitter and receiver identities, radio gains, and hardware information.
- **Measured quantities:** received signal power, noise power, and estimated SNR.

By deriving annotations from the experiment timeline, CorteXforge avoids manual signal labeling while preserving the relationship between the intended scenario and the physical acquisition.

## Generated Datasets

CorteXforge has been used to generate **ModForge**, an OTA dataset for automatic modulation recognition.

ModForge contains 24 modulation classes acquired using multiple physical SDR configurations. It provides a realistic counterpart to synthetic modulation datasets and enables the study of the synthetic-to-real domain gap.

Pre-generated datasets can be accessed through the CorteXforge command-line interface:

```bash
pip install cortexforge

cortexforge datasets list
cortexforge datasets download modforge
```

## Source Code

CorteXforge is open-source and available on [GitHub](https://github.com/Andreaj42/CorteXforge).
