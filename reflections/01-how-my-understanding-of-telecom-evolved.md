# Reflection 1: How My Understanding of Telecommunications Evolved

I started this course with no telecommunications background. Networks were something I used every day without any picture of how they actually worked. The early modules built that picture from the ground up, and looking back, I can see my understanding move in clear stages.

## From a single signal to a system

Module 01 gave me the first mental model, and it turned out to be the one everything else hangs on: any communication system is three parts in order, a transmitter, a channel, and a receiver, with noise acting on the signal along the way. That sounds simple, but it only became real when I traced a single message through the whole chain in code. I put 20 bits on a carrier wave with BPSK, ran them through a channel that added noise, and watched the receiver pull the original bits back out. Seeing all 20 bits survive at a 10 dB signal-to-noise ratio taught me something the definition alone could not: noise is not the end of a signal, it is something a system is designed to work through. After that, terms like signal-to-noise ratio, bandwidth, latency, and throughput stopped being vocabulary and became the four dials I could use to judge any link.

## From one link to whole networks

Module 02 widened the view from one signal to whole networks. This is where I learned to read a packet capture in Wireshark, and that was a turning point. Instead of reading about the TCP/IP model, I watched the layers work on my own traffic: private and public addresses, TCP for reliable connections, UDP for fast traffic like QUIC, and my own machine talking to server port 443. The detail that stuck with me was small but clarifying: almost every connection went to port 443 and the plain HTTP filter returned nothing, which is the visible proof that modern web traffic is encrypted. In the same module I modeled free-space path loss and learned why higher-frequency links reach shorter distances, which finally explained something I had always taken for granted about why cell towers are placed where they are.

## From 4G to the 5G core and Open RAN

The middle of the course is where telecom stopped feeling like a fixed set of boxes and started feeling like software. What I learned in the 5G core work is how much the design changed between generations. The 4G core is dedicated hardware, but the 5G core is small software services running in the cloud that call each other only when needed, and that single shift is what makes network slicing possible. Once I understood slicing, a lot clicked: one physical network can act like several tuned networks at once, so it can serve factory robot control and a crowd of low-power sensors at the same time. Module 05 took this further into Open RAN, where I learned that open, standard interfaces between the radio units, distributed units, centralized units, and the RAN Intelligent Controller are what break vendor lock-in and let AI reach across the whole stack.

## Where I landed

By the end of the term the vocabulary that felt like a wall in week one, words like slice, path loss, RIC, and core, had turned into a working map I could actually reason with. I can now read a packet capture, model how far a signal travels, explain how a 5G network shares one physical system among very different demands, and follow where 6G is heading with its move toward terabit speeds and an AI-native design. The biggest change is not any single fact. It is that a network went from being a black box I used to a layered system I can picture, question, and, as the second half of the course showed me, improve.
