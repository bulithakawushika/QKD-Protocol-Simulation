# Quantum Key Distribution (QKD) Protocol Simulation with NetSquid

This repository provides **implementations and simulations of BB84, E91, and MDI-QKD quantum key distribution (QKD) protocols** using the [NetSquid](https://netsquid.org/) simulator.  
It is designed as a **research-oriented toolset** for simulating realistic quantum communication networks, focusing on **physical-layer imperfections, channel noise, and hardware limitations**.

---

## 🎯 Motivation

During my final year research project, I identified a major challenge in QKD research:  
> **A lack of publicly available, accurate, and realistic simulation code for QKD protocols.**

Most existing QKD simulations either:
- **Ignore real-world channel noise** and photon loss, or
- **Simplify QKD logic** without accurately modeling physical components.

Building a real-world QKD system requires **extremely expensive equipment**:
- Single-photon sources, detectors, and quantum memories
- Highly precise optical fiber infrastructure
- Specialized synchronization and error correction systems

As a **cost-effective solution**, I developed this simulation framework using **NetSquid**, a discrete-event simulator capable of:
- Modeling **physical components** like photon sources, detectors, and quantum memories
- Simulating **time-dependent noise, decoherence, and photon loss**
- Designing **scalable quantum communication networks**

This repository is built to **help researchers quickly prototype, evaluate, and extend QKD protocols**.

---

## 🔬 Why NetSquid?

| Feature                               | NetSquid                                                                                   | QuNetSim                                                | SimulaQron                                         | Qiskit/Cirq                                          |
|--------------------------------------|-------------------------------------------------------------------------------------------|--------------------------------------------------------|--------------------------------------------------|------------------------------------------------------|
| **Simulation Approach**              | Discrete-event simulation with detailed physical modeling                                  | High-level Python interface for protocol design         | Application-focused, limited low-level modeling  | Quantum circuit paradigm (gate/circuit simulation)   |
| **Physical Layer Realism**           | High: Supports hardware imperfections, photon loss, qubit decoherence                     | Low: High abstraction, not physics-focused             | Low: Minimal physics modeling                     | Low: Focused on circuit logic, not networks         |
| **Scalability**                      | High: Designed for large network simulations                                              | Moderate: Suitable for small-scale networks            | Limited: Application development focus            | Limited: Focused on individual circuits             |
| **Key Advantage for QKD Research**   | Essential for simulating **hardware noise** & **channel imperfections**                  | Good for simple network logic                          | Minimal support for physical realism             | Not designed for network-level QKD simulations      |

Reason for Choosing NetSquid: I selected NetSquid over other simulators because it offers high physical-layer realism, detailed noise modeling, and scalability, making it ideal for accurately simulating QKD protocols and channel imperfections.

---

## 🧩 Implemented QKD Protocols

This project includes **three widely used QKD protocols**:

| Protocol | Description | Reference |
|----------|-------------|-----------|
| **BB84** | The first and most widely used QKD protocol, proposed by Bennett and Brassard in 1984. It uses **photon polarization** to establish a shared secret key and relies on quantum mechanics to ensure security. | [Comprehensive Study of BB84](https://www.researchgate.net/publication/370040044_Comprehensive_Study_of_BB84_A_Quantum_Key_Distribution_Protocol) |
| **E91**  | Proposed by Artur Ekert in 1991, E91 uses **entangled photon pairs** and Bell inequality tests for security verification, making it resistant to eavesdropping. | [Wikipedia - E91 Protocol](https://en.wikipedia.org/wiki/Quantum_key_distribution#E91_protocol:_Artur_Ekert_.281991.29) |
| **MDI-QKD** | Measurement-Device-Independent QKD addresses detector side-channel attacks by allowing an untrusted relay to perform measurements. It enhances security in practical implementations. | [arXiv:1109.1473](https://arxiv.org/abs/1109.1473) |

---

## 📊 Performance Metrics

The simulation measures multiple **network and protocol performance indicators**:

| Metric                        | Definition |
|-------------------------------|-----------|
| **Throughput (qubits/sec)**  | Number of qubits successfully transmitted per second. Higher throughput means more efficient communication. |
| **Synchronization Time (ms)**| Time to align sender and receiver in BB84. Lower is better for secure setup speed. |
| **Raw Key Rate (qubits)**    | Amount of raw key material generated before error correction. |
| **QBER (%)**                 | Quantum Bit Error Rate. Lower QBER indicates higher channel quality. |
| **Latency (ms)**             | Overall delay in qubit transmission and key generation. |
| **Communication Overhead**   | Number of classical messages exchanged for authentication and error correction. |
| **Channel Loss Rate (%)**    | Fraction of qubits lost during transmission. |

---

## 🗂 Repository Structure

This repository contains **two simulation sets**:

| Set                  | Description |
|----------------------|------------|
| **Advanced Set**     | Modular implementation with physical-level customization of devices, channels, and protocol logic. Suitable for **detailed research** and hardware-level analysis. |
| **Basic Set**        | Single-file implementations for **quick demonstrations** and testing. Easier for beginners to modify and run. |

Each simulation can **plot performance results** (e.g., QBER, throughput) for a **10 km fiber link between Alice and Bob**.

---

## ⚙️ Technical Details

- **Simulator**: [NetSquid](https://netsquid.org/)  
- **NetSquid Version Used**: `1.1.1`  
- **Programming Language**: Python 3.x  
- **Dependencies**: `netsquid`, `numpy`, `matplotlib`, and other scientific libraries  

---

## 📈 Example Use Case

This repository is ideal for:
- Researchers exploring **QKD performance under realistic channel conditions**
- Students learning **quantum networking fundamentals**
- Security professionals evaluating **QKD feasibility in TLS and VPN systems**
- Rapid prototyping of **future quantum network protocols**

---

## 📚 Further Reading

- [NetSquid Documentation](https://netsquid.org/docs/latest-release/)  
- [Comprehensive Study of BB84 Protocol](https://www.researchgate.net/publication/370040044_Comprehensive_Study_of_BB84_A_Quantum_Key_Distribution_Protocol)  
- [E91 Protocol - Wikipedia](https://en.wikipedia.org/wiki/Quantum_key_distribution#E91_protocol:_Artur_Ekert_.281991.29)  
- [Measurement-Device-Independent QKD - arXiv:1109.1473](https://arxiv.org/abs/1109.1473)  
