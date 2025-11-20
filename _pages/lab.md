---
layout: default
title: "Working Projects"
permalink: /lab/
---

We build autonomous agents that reason over distributed, high-stakes data (Bio & Finance) without ever centralizing it. We replace trust with cryptography and replace correlation with causal/structural reasoning.

## Infrastructure

> We replace "Trust" (Institutional Reputation) with "Math" (Cryptography) and "Incentives" (Game Theory).

### Proof-of-Learning (PoL): The ZK-Training Protocol

The Moonshot: To create the "SSL/TLS" of Machine Learning—a standard protocol where a node proves it trained a model correctly on private data without revealing a single byte of that data.

**The Hard Problem**: Currently, Zero-Knowledge (ZK) protocols are slow and mostly work for inference (proving a model ran). Proving training (Backpropagation, SGD) involves millions of floating-point multiplications, which is computationally prohibitive for current ZK-SNARKs.

* **Recursive Proof Composition**: Instead of one massive proof for the whole training run, your team builds a recursive system (like Plonky2 or Halo2) where the proof for Step $N$ verifies the proof for Step $N-1$.
* **Optimized Circuits for Gradients**: You design custom Arithmetic Circuits specifically for Matrix Multiplication and ReLU derivatives, optimizing the "constraints per step" (the metric of ZK speed).
* **Verifiable Randomness**: Use an on-chain Verifiable Random Function (VRF) to seed the SGD batches, ensuring the node didn't cherry-pick "easy" data to fake a high loss reduction.

### Swarm-MoE: The Inter-Institutional Mixture of Experts

The Moonshot: A "Global Brain" where the "Neurons" are hospitals. A single logical LLM where the parameters are physically distributed across 1,0000 institutions.

**The Hard Problem**: Latency. If every token generation requires a network call to 5 different hospitals, the model will be unusably slow.

* **Hierarchical Gating**: A lightweight "Router Model" sits on the user's device. It decides: "Is this a generic biology question (Local Inference)? Or a rare cancer question (Route to Mayo Clinic Node)?"

* **Asynchronous Expert Execution**: Unlike standard MoE which waits for all experts, Swarm-MoE uses "Speculative Decoding." It guesses the expert's likely output while waiting for the real encrypted embedding to return from the hospital.

* **Privacy-Preserving Routing**: The Router doesn't send raw text to the hospital; it sends a Homomorphically Encrypted Embedding. The hospital computes the "Expert Layer" on encrypted data and returns the result.

Existing works:

1. Cheng, Zehua, Rui Sun, Jiahao Sun, and Yike Guo. (2025). "Scaling Decentralized Learning with FLock." In Procedings of 2025 IEEE/WIC International Conference on Web Intelligence and Intelligent Agent Technology (WI-IAT). [WI-IAT 2025 **Best Application Award**]