---
layout: page
title: Sound System
permalink: /sound_system/
weight: 3
---

# Sound System

My Sound System is a custom three-way audio system designed and assembled to experiment with acoustics, signal processing, amplification, and loudspeaker enclosure design.

The system is divided into three frequency sections — tops, kicks, and subwoofers — allowing each part of the frequency spectrum to be handled independently.

## Architecture

The Sound System follows a three-way architecture designed to provide independent control over high, mid-bass, and low-frequency reproduction.


### System Configuration

The system consists of three main sections:

* **Tops:** 2 cabinets for high-frequency and full-range reproduction
* **Kicks:** 2 dedicated enclosures for punch and mid-bass reproduction
* **Subwoofers:** 2 dedicated enclosures for low-frequency extension

This modular architecture makes it possible to independently tune the frequency ranges, amplification levels, and crossover points of each section.

{% include sound-system/sound-system-architecture.html %}

## Signal Processing

Frequency distribution between the different sections is handled by a **Behringer DSP DCX2496**.

The crossover separates the incoming audio signal into dedicated frequency ranges for the subwoofers, kicks, and tops. This allows each loudspeaker section and amplifier to operate within its intended frequency range.

<!--
## Crossover Configuration

The system uses a **Behringer CX3400 Super-X Pro V2** active crossover to divide the audio spectrum between the subwoofer, kick, and top sections.

The following configuration is used as a baseline for electronic music and techno, where low-frequency extension and transient impact in the kick region are particularly important.

| Section        | Operating Range | Crossover                  |                    Slope | Role                                |
| -------------- | --------------: | -------------------------- | -----------------------: | ----------------------------------- |
| **Subwoofers** |       ~25–90 Hz | LPF @ 90 Hz                | Linkwitz–Riley 24 dB/oct | Low-frequency foundation            |
| **Kicks**      |       90–180 Hz | HPF @ 90 Hz / LPF @ 180 Hz | Linkwitz–Riley 24 dB/oct | Kick impact and mid-bass            |
| **Tops**       |         >180 Hz | HPF @ 180 Hz               | Linkwitz–Riley 24 dB/oct | Mid and high-frequency reproduction |

### Design Rationale

The **90 Hz crossover** between the subwoofers and kicks separates the low-frequency foundation from the frequency region responsible for most of the perceived impact of a kick drum.

The Schlag-115 subwoofers are therefore primarily used below 90 Hz, while the KTHSR-15 enclosures reproduce the approximately **90–180 Hz** region. This reduces the spectral range handled by each enclosure and allows the kick section to concentrate on transient mid-bass reproduction.

A second crossover at **180 Hz** transfers the signal from the dedicated kick enclosures to the full-range top cabinets. This frequency remains within the intended operating region of the kick loudspeakers while preventing the tops from reproducing the highest-energy part of the low-frequency spectrum.

The crossover uses **fourth-order Linkwitz–Riley filters (24 dB/oct)**. For two acoustically aligned sources, this filter topology provides complementary low-pass and high-pass responses whose summed response remains approximately flat around the crossover frequency.

### Alignment

Crossover frequencies alone do not guarantee a coherent acoustic response. The acoustic centres of the subwoofers, kicks, and tops are physically separated, introducing different propagation delays at the listening position.

The propagation delay associated with a path-length difference $$\Delta d$$ can be approximated by:

$$
\Delta t = \frac{\Delta d}{c}
$$

where $$c \approx 343\ \mathrm{m.s^{-1}}$$ is the speed of sound.

As a practical approximation, a displacement of **34.3 cm corresponds to approximately 1 ms of delay**.

The delay and polarity settings should therefore be adjusted from acoustic measurements rather than from enclosure dimensions alone. The objective is to maximize constructive summation around the **90 Hz** and **180 Hz** crossover regions.

### Low-Frequency Protection

The CX3400 **25 Hz low-cut filter** is enabled to reduce unnecessary subsonic energy before amplification.

This filter should however be considered a basic protection rather than an optimized high-pass filter for the Schlag-115 enclosure. A dedicated DSP with adjustable high-pass frequency, filter topology, equalization, delay, and limiting would provide more precise loudspeaker protection and system alignment.

### Gain Structure

The three frequency sections should not be balanced solely from amplifier knob positions. Their acoustic sensitivities, amplifier gains, enclosure efficiencies, and number of loudspeakers differ.

The output gains are therefore treated as calibration parameters:

$$
L_{\mathrm{system}}(f)
=
L_{\mathrm{sub}}(f)
+
L_{\mathrm{kick}}(f)
+
L_{\mathrm{top}}(f)
$$

with the practical objective of obtaining a controlled frequency response while preserving sufficient headroom in every amplification channel.

For techno-oriented playback, the target is not necessarily a perfectly flat response. A moderate emphasis of the low-frequency section may be desirable, but it should be introduced only after crossover alignment and gain calibration.

> **Note:** These settings represent an engineering baseline rather than a definitive system calibration. Final crossover gains, delays, polarity, and equalization depend on loudspeaker placement and should ideally be validated using acoustic measurements.

-->
## Hardware

| Section          | Cabinet                                                                         | Driver                            | Amplifier        |
| ---------------- | ------------------------------------------------------------------------------- | --------------------------------- | ---------------- |
| **Top ×2**       | Ibiza Disco 15B                                                                 | Integrated                        | Ibiza AMP600     |
| **Kick ×2**      | [HSR Sonorisation KTHSR-15](https://hsrsonorisation.fr/downloads/kthsr-15/)     | Eminence KAPPA PRO-15A — 15", 8 Ω | the t.amp E-1200 |
| **Subwoofer ×2** | [HSR Sonorisation Schlag-115](https://hsrsonorisation.fr/downloads/schlag-115/) | Eminence Delta-15LFC, 15", 4 Ω    | the t.amp E-1200 |

## Design

The system was built around a modular approach where each loudspeaker section has a dedicated acoustic role.

* **Top section:** Handles the upper part of the frequency spectrum and provides the main full-range reproduction.
* **Kick section:** Reinforces the mid-bass region to provide impact and punch.
* **Subwoofer section:** Handles the lowest frequencies and provides the low-end foundation of the system.

Separating these roles makes the system easier to tune and allows the amplification and filtering of each frequency range to be adjusted independently.

## Acknowledgements

This project was designed and built with **Tonin Dechavanne** and **Cyprien Larue**.
