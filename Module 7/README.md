# Module 07 - IoT and Edge Computing with AI

**Course:** ITAI 4370 - AI in 5G and 6G Communications and ORAN Networks  
**Student:** Monica Joya  |  **Term:** Summer 2026  
**Module dates:** July 14 - July 20, 2026

## Overview

Module 07 covered moving AI from the cloud to the edge, meaning small field devices with limited memory and power. The main question was how to shrink a full-size model enough to run on such a device without losing much accuracy. I also kept a build journal to record the setup problems and how I handled them.

## Artifacts in this folder

- [`Lab 5/Joya_ITAI4370_Lab05_EdgeComputing.ipynb`](Lab%205/Joya_ITAI4370_Lab05_EdgeComputing.ipynb) - Compresses a full model three ways for edge devices and compares cost and accuracy (executed, with output).
- [`Lab 5/Joya_ITAI4370_Lab05_BuildJournal.docx`](Lab%205/Joya_ITAI4370_Lab05_BuildJournal.docx) - My build journal: the real problems I hit and how I solved them.

## Problem statement

Take one full-size model and shrink it so it can run on a small edge device, then measure what each compression method costs in accuracy and saves in size.

## Methods and tools

Python with TensorFlow/Keras. Three compression methods: quantization, pruning, and knowledge distillation, on synthetic IoT sensor data (10,000 samples, 20 features, 3 states).

## Results and interpretation

Part of the starter code was broken: the knowledge distillation section was set up but never connected, so the student model trained on its own and never used the teacher. I connected them so the student trains on the teacher's softened predictions, corrected the temperature, and marked the change as mine. During setup I hit TensorFlow install problems that broke the notebook tools. The full model reaches about 94 percent accuracy, and each smaller version trades a little accuracy for a much smaller size. The size-versus-accuracy chart is in the notebook above.

## What I learned

I learned that on an easy dataset a small model already captures most of the signal, so distillation does not always come out ahead. I also learned to test a fragile step on a tiny model before a full run, which caught the broken distillation early and saved time.

---
[Back to portfolio home](../README.md)
