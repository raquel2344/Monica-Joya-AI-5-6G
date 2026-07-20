# Module 10 - Midterm Project: Network Simulation and Predictive Optimization

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026  
**Milestone:** Midterm Project

## Overview

The midterm combined three ways of studying a network in one project: a discrete-event simulation, an agent-based model, and a machine learning predictor. Each part approached the same theme, how traffic moves through a network and how a network can manage its own load, from a different angle.

## Artifacts in this folder

- [`Midterm/Joya_Midterm_3NetworkSimulations_ITAI4370.ipynb`](Midterm/Joya_Midterm_3NetworkSimulations_ITAI4370.ipynb) - One notebook with all three parts, each built on the starter code and extended (executed, with all three plots).

## Problem statement

Study one network three ways: measure packet latency and throughput, model routers that reroute around congestion on their own, and forecast traffic to steer routing before congestion forms.

## Methods and tools

Python with SimPy (discrete-event simulation), Mesa (agent-based modeling), and scikit-learn (regression), plus NetworkX, NumPy, pandas, and Matplotlib.

## Results and interpretation

**Part 1 (SimPy):** packets queue at single-capacity routers, so queueing turns into latency, and the run produces a throughput figure for the chain.

**Part 2 (Mesa):** this part needed two fixes. The starter used an older Mesa scheduler that was removed in the current version, and it only printed a message when a router was overloaded without moving any load, so I connected that step so a congested router actually offloads to neighbors. The busiest router then recovered each time as its load spread out.

**Part 3 (scikit-learn):** a regression model forecasts traffic using past-only features, so there is no target leakage, and new flows are routed to the quieter predicted path before congestion can form.

All three plots (latency and throughput, network load over time, and prediction with routing) are in the notebook above.

## What I learned

From Part 1 I learned that a discrete-event simulator turns the timing of events into latency numbers and a throughput figure. From Part 2 I learned that useful behavior can emerge without a central controller, since the network recovered because each router acted on its own. From Part 3 I learned that forecasting is only half the work, and the value comes from letting the forecast drive the routing decision, which is what self-optimizing means in practice.

---
[Back to portfolio home](../README.md)
