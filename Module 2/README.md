# Module 02 - Network Architecture and Wireless Basics

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026

## Overview

Module 02 moved from a single signal to whole networks. It covered how networks are built and addressed, the TCP/IP model and the protocols that run on it, and the basics of wireless, including why a signal weakens as it travels. It also introduced the 5G core, comparing the older 4G design with the newer service-based 5G design.

## Artifacts in this folder

- [`Joya_Assignment 2_ITAI 4370_06152026.pdf`](Joya_Assignment%202_ITAI%204370_06152026.pdf) - Five written questions on the 5G core, built from industry and standards sources and cited in APA.
- [`Joya_Activity 1_Wireshark Lab Report_ITAI4370.pdf`](Joya_Activity%201_Wireshark%20Lab%20Report_ITAI4370.pdf) - Report on a live packet capture read and filtered in Wireshark, with the capture screenshot.
- [`Joya_Activity2_Lab02_FSPL Output_ITAI4370.ipynb`](Joya_Activity2_Lab02_FSPL%20Output_ITAI4370.ipynb) - Python notebook modeling free-space path loss vs distance (executed, with output).

## Problem statement

Two goals: read real network traffic and see the protocol layers in action, then model how far a wireless signal can travel before it weakens too much.

## Methods and tools

Wireshark for live capture and the ip, tcp, and http display filters; Python with NumPy and Matplotlib for the free-space path loss model.

## Results and interpretation

The capture held 2599 packets from about a minute of browsing. Almost every connection went to port 443 and the http filter returned nothing, which shows that modern web traffic is encrypted over HTTPS and QUIC. Round trip time measured 94 microseconds. The path loss curve (in the FSPL notebook above) climbs steadily with distance and frequency, which is why higher-frequency 5G links reach shorter distances and need towers placed closer together.

## What I learned

What I learned here is how much the core design changed. The 4G core is a fixed set of dedicated boxes, while the 5G core is small software services in the cloud that call each other only when needed, which is what lets it scale and slice. From the path loss model I learned that loss increases with both distance and frequency, so a signal weakens the farther it travels and the higher its frequency.

---
[Back to portfolio home](../README.md)
