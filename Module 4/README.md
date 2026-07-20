# Module 04 - 5G Architecture and AI Integration

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026  
**Module dates:** June 23 - June 29, 2026

## Overview

Module 04 covered 5G architecture and where AI fits in. The main idea is network slicing, running several tuned virtual networks on one shared physical network so it can serve very different needs at once. It tied this to the three standard service types and to sharing limited resources fairly between them.

## Artifacts in this folder

- [`Hands On Exercise Output.ipynb`](Hands%20On%20Exercise%20Output.ipynb) - Notebook that models the three 5G slices and allocates resources by priority (executed, with the bar chart output).
- [`Hands On Exercise.pdf`](Hands%20On%20Exercise.pdf) - The lab brief and starter code.

## Problem statement

Model the three 5G service types as network slices with different quality-of-service needs, then share a fixed pool of resources among them so priority traffic gets the larger share.

## Methods and tools

Python with NumPy, pandas, and Matplotlib. A proportional allocation algorithm weighted by slice priority and normalized to a fixed 500-unit pool. One fix to the starter code: the demand loop recorded one value per slice instead of one per connection, so I moved that line inside the loop before running it.

## Results and interpretation

The allocation came out URLLC 139, eMBB 278, mMTC 82 out of 500. eMBB takes the largest share from its high bandwidth and strong weight, URLLC holds a solid share from top priority despite fewer connections, and mMTC takes the least since its many devices each ask for very little. The bar chart is in the notebook above.

## What I learned

I learned that the normalizing step is the core of the algorithm, since it turns requests of different sizes into fair shares that always add up to the capacity available, which is how a real network gives the larger share to priority, latency-sensitive traffic while staying within its limits.

---
[Back to portfolio home](../README.md)
