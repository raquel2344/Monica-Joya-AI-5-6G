# Module 01 - Telecommunications Fundamentals

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026  
**Module dates:** June 1 - June 8, 2026

## Overview

Module 01 covered the fundamentals of telecommunications, starting from no prior background. The main idea is that any communication system has three parts working in order: a transmitter, a channel, and a receiver, with noise affecting the signal along the way. It also covered analog versus digital signals, the four metrics for judging a link, the main types of communication, and how network topology affects reliability and cost.

## Artifacts in this folder

- [`Joya_Assignment 1_ITAI 4370_06082026.pdf`](Joya_Assignment%201_ITAI%204370_06082026.pdf) - Five written questions on the fundamentals of a communication system, cited to the slides and the Forouzan networking textbook.
- [`Part 2_Analysis_Joya_ITAI4370_06082026.ipynb`](Part%202_Analysis_Joya_ITAI4370_06082026.ipynb) - Python notebook that sends bits through a communication system with BPSK and plots each stage (executed, with output).
- [`Part 3_Report_Joya_ITAI4370_06082026.pdf`](Part%203_Report_Joya_ITAI4370_06082026.pdf) - Written lab report for the signal-flow analysis.
- [`Part 1_Diagram_Joya_ITAI4370_06082026.png`](Part%201_Diagram_Joya_ITAI4370_06082026.png) - The communication system drawn in draw.io.

## Problem statement

Build a working picture of a communication system end to end: describe its parts on paper, then follow a single message through the full chain in code so the theory is grounded in a concrete example.

## Methods and tools

draw.io for the block diagram; Python with NumPy and Matplotlib for the signal-flow analysis using BPSK (Binary Phase Shift Keying) over an additive-noise channel.

## Results and interpretation

The diagram traces the path from source to modulator to channel to demodulator to receiver, colored by function. In the notebook, 20 random bits were placed on a 5 Hz carrier and passed through a channel with noise at a 10 dB signal-to-noise ratio. All 20 bits were recovered correctly, because at 10 dB the signal stays above the noise. The four-stage BPSK plot is in the notebook above.

![Communication system diagram](Part%201_Diagram_Joya_ITAI4370_06082026.png)

*Figure 1. The communication system, drawn in draw.io.*

## What I learned

I learned the four metrics that judge a link: signal-to-noise ratio, bandwidth, latency, and throughput. I also learned to compare network topologies by how they fail: a bus or ring goes down if one point fails, a star depends on its central hub, and a mesh is the most reliable but the most expensive, so real networks combine them. From running the lab I learned how BPSK works, and that a receiver can pull a clean message back out of a noisy signal by multiplying by the same carrier and reading each bit period.

---
[Back to portfolio home](../README.md)
