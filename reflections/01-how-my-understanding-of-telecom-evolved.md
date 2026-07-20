# Reflection 1: How My Understanding of Telecommunications Evolved

I began this course with no telecommunications background, so my understanding was built module by module. The clearest way to describe it is by what I could technically do at each stage.

## The physical layer: signals and noise

Module 01 defined a communication system as three parts in order, a transmitter, a channel, and a receiver, with noise added in the channel. I built this in Python as a BPSK link: 20 random bits placed on a 5 Hz carrier, passed through a channel that added noise at a 10 dB signal-to-noise ratio, then recovered by multiplying the received signal by the same carrier and integrating over each bit period. All 20 bits were recovered correctly, which showed concretely why a 10 dB margin is enough for reliable detection. This module also gave me the four metrics I used to judge every link afterward: signal-to-noise ratio, bandwidth, latency, and throughput.

## The network layer: addressing, protocols, and propagation

Module 02 moved to whole networks. I captured 2599 packets of my own traffic in Wireshark and filtered by ip, tcp, and http. Almost all traffic went to TCP port 443, and the http filter returned zero packets, which is direct evidence that current web traffic is encrypted over HTTPS and QUIC rather than plain HTTP. Wireshark also reported a round trip time of 94 microseconds. Separately, I modeled free-space path loss in Python for a 2.4 GHz signal from 0.1 to 20 km and confirmed that loss rises with both distance and frequency, which is the technical reason higher-frequency links cover shorter ranges and need denser cell placement.

## The core: from 4G hardware to 5G software

The 5G core work was where the architecture came together. The 4G core (EPC) is a fixed set of dedicated network functions, while the 5G core (5GC) implements those functions as cloud-native software services that communicate over a service-based interface and scale independently. That design is what makes network slicing possible: one physical network can run several isolated slices, tuned for URLLC (low latency), eMBB (high bandwidth), or mMTC (many low-power devices).

## Open RAN and 6G

Module 05 covered Open RAN, which splits the radio network into the Radio Unit, Distributed Unit, Centralized Unit, RAN Intelligent Controller, and Service Management and Orchestration layer, connected by open interfaces (A1, E2, F1, E1, O1). The technical point is that standard interfaces let an operator mix vendors and let the RIC apply optimization across the stack. The course closed on 6G, with its targets of terabit-per-second peak rates, sub-millisecond latency, much higher device density, terahertz spectrum, and an AI-native design.

## Where I ended

By the end I could read a packet capture and interpret the protocols and ports, calculate and explain path loss, describe how the 5G core enables slicing, trace the components and interfaces of an Open RAN, and place 6G's goals in context. The subject went from unfamiliar to something I can analyze layer by layer.
