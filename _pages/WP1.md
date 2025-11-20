---
layout: archive
title: "Infra"
permalink: /WP1/
author_profile: true
---

We build autonomous agents that reason over distributed, high-stakes data (Bio & Finance) without ever centralizing it. We replace trust with cryptography and replace correlation with causal/structural reasoning.

If you are interested in any of this project, please don't feel free to contact me. :)

# Infrastructure

> We replace "Trust" (Institutional Reputation) with "Math" (Cryptography) and "Incentives" (Game Theory).

## Proof-of-Learning (PoL): The ZK-Training Protocol

The Moonshot: To create the "SSL/TLS" of Machine Learning—a standard protocol where a node proves it trained a model correctly on private data without revealing a single byte of that data.

**The Hard Problem**: Currently, Zero-Knowledge (ZK) protocols are slow and mostly work for inference (proving a model ran). Proving training (Backpropagation, SGD) involves millions of floating-point multiplications, which is computationally prohibitive for current ZK-SNARKs.

* **Recursive Proof Composition**: Instead of one massive proof for the whole training run, your team builds a recursive system (like Plonky2 or Halo2) where the proof for Step $N$ verifies the proof for Step $N-1$.
* **Optimized Circuits for Gradients**: You design custom Arithmetic Circuits specifically for Matrix Multiplication and ReLU derivatives, optimizing the "constraints per step" (the metric of ZK speed).
* **Verifiable Randomness**: Use an on-chain Verifiable Random Function (VRF) to seed the SGD batches, ensuring the node didn't cherry-pick "easy" data to fake a high loss reduction.

## Decentralized-MoE: The Inter-Institutional Mixture of Experts

The Moonshot: A "Global Brain" where the "Neurons" are hospitals. A single logical LLM where the parameters are physically distributed across 1,0000 institutions.

**The Hard Problem**: Latency. If every token generation requires a network call to 5 different hospitals, the model will be unusably slow. Security. LLM can have biased and can even be weaponized.

* **Hierarchical Gating**: A lightweight "Router Model" sits on the user's device. It decides: "Is this a generic biology question (Local Inference)? Or a rare cancer question (Route to Mayo Clinic Node)?"
* **Asynchronous Expert Execution**: Unlike standard MoE which waits for all experts, Swarm-MoE uses "Speculative Decoding." It guesses the expert's likely output while waiting for the real encrypted embedding to return from the hospital.
* **Privacy-Preserving Routing**: The Router doesn't send raw text to the hospital; it sends a Homomorphically Encrypted Embedding. The hospital computes the "Expert Layer" on encrypted data and returns the result.

**Relevant Publications**:

1. Cheng, Zehua, Rui Sun, Jiahao Sun, and Yike Guo. (2025). "Scaling Decentralized Learning with FLock." In Procedings of 2025 IEEE/WIC International Conference on Web Intelligence and Intelligent Agent Technology (WI-IAT). [**WI-IAT 2025 - Best Application Award**] [[Paper]](https://arxiv.org/abs/2507.15349)
2. Cheng, Zehua, Manying Zhang, Jiahao Sun, and Wei Dai. "On weaponization-resistant large language models with prospect theoretic alignment." In Proceedings of the 31st International Conference on Computational Linguistics, pp. 10309-10324. 2025. [[Paper]](https://aclanthology.org/2025.coling-main.687.pdf)

## Nash-Equilibrium Data Valuation: The Shapley Protocol

The Moonshot: Solving the "Free Rider Problem." In current federated learning, a hospital that contributes junk data gets the same model as a hospital that contributes gold. This protocol automatically pays data owners based on the exact marginal utility of their contribution.

**The Hard Problem**: Calculating the true Shapley Value is $O(N!)$—impossible to compute for thousands of nodes.

* **Gradient-Based Influence Functions**: Instead of retraining the model $N$ times to measure value, you approximate value by analyzing the cosine similarity of a node's gradient update relative to the "Gold Standard" validation set held by the protocol.
* **The Payment Stream**: A smart contract layer (L2) that acts as a "Streaming Payment" engine. Every time a node sends a gradient that reduces the global loss, micro-payments flow to their wallet. If they send noise, they get slashed (fined).
* **Equilibrium Discovery**: You prove mathematically that "Honest Contribution" is the Nash Equilibrium of this game—cheating is always less profitable than contributing.

## The Holographic Gradient: Bandwidth-Efficient Learning

The Moonshot: Training a 1 Trillion parameter model on a network of consumer-grade internet connections (e.g., connecting Starlink satellites or home GPUs).

**The Hard Problem**: Bandwidth. Sending 1TB of gradients every second is impossible for hospitals or home nodes.

* **CountSketch / TensorSketch**: You don't send the gradient. You send a "Sketch"—a randomized projection of the gradient into a tiny subspace.
* **Error Feedback Memory**: The "compression error" (the part of the gradient you threw away) is stored locally in a "Memory Buffer" and added to the next update. This ensures that over time, all information is eventually transmitted, guaranteeing convergence (unlike simple quantization).
* **"Holographic" Reconstruction**: The central aggregator receives "sketches" from 1,000 nodes and mathematically reconstructs the high-fidelity global gradient, leveraging the fact that noise cancels out at scale.