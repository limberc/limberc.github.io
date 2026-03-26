---
title: "Infra"
permalink: /WP1/
author_profile: true
---

We build autonomous agents that reason over distributed, high-stakes data (Bio & Finance) without ever centralizing it. We replace trust with cryptography and replace correlation with causal/structural reasoning.

If you are interested in any of this project, please feel free to contact me. :)

# Infrastructure

> We replace "Trust" (Institutional Reputation) with "Math" (Cryptography) and "Incentives" (Game Theory).

## Proof-of-Learning (PoL): The ZK-Training Protocol

*The Moonshot*: To create the "SSL/TLS" of Machine Learning—a standard protocol where a node proves it trained a model correctly on private data without revealing a single byte of that data.

**The Hard Problem**: Currently, Zero-Knowledge (ZK) protocols are slow and mostly work for inference (proving a model ran). Proving training (Backpropagation, SGD) involves millions of floating-point multiplications, which is computationally prohibitive for current ZK-SNARKs.

* **Recursive Proof Composition**: Instead of one massive proof for the whole training run, we builds a recursive system (like Plonky2 or Halo2) where the proof for Step $N$ verifies the proof for Step $N-1$.
* **Optimized Circuits for Gradients**: We design custom Arithmetic Circuits specifically for Matrix Multiplication and ReLU derivatives, optimizing the "constraints per step" (the metric of ZK speed).
* **Verifiable Randomness**: Use an on-chain Verifiable Random Function (VRF) to seed the SGD batches, ensuring the node didn't cherry-pick "easy" data to fake a high loss reduction.

## The Holographic Neural Fabric

*The Moonshot*: Construct a single, coherent, trillion-parameter intelligence that "lives" purely on the dormant, fragmented compute of the world’s existing infrastructure—consumer GPUs, hospital servers, and idle research workstations—connected only by standard public internet.

**The Hard Problem**: To maintain a unified global intelligence across a network where **physical latency** fractures real-time inference, **localized learning** drives mathematical divergence, and **hardware asymmetry** destabilizes synchronization.

* **Chronos**: The speed of light imposes a hard, immutable limit on distributed intelligence, paralyzing model execution whenever a neural network spans across geography. To cheat this physics, the Chronos Module decouples logical thought from network transmission by using lightweight local "ghost" models to hallucinate the outputs of remote experts instantly, only consulting the network when a compressed "Holographic Sketch" detects a deviation from reality. This architectural sleight-of-hand effectively erases the latency penalty of the open internet, allowing a global mesh to infer with the responsiveness of a single local chip.
* **Spectral State Synchronization**: In a decentralized system where independent nodes learn from private, local data, their internal mathematical definitions inevitably drift apart until they are speaking mutually unintelligible languages. This module prevents this "Tower of Babel" scenario by continuously projecting local weight updates into a lower-dimensional "Spectral Space," broadcasting these tiny mathematical sketches to the rest of the network as a unifying signal. This mechanism acts as a form of mathematical gravity, constantly pulling thousands of isolated, evolving models back toward a coherent global consensus without ever clogging the bandwidth pipes with raw heavy parameters.

**Relevant Publications**:

1. **Zehua Cheng**, Rui Sun, Jiahao Sun and Yike Guo. (2025). "Scaling Decentralized Learning with FLock." In Procedings of 2025 IEEE/WIC International Conference on Web Intelligence and Intelligent Agent Technology (WI-IAT). [**WI-IAT 2025 - Best Paper Award (Industrial)**] [[Paper]](https://arxiv.org/abs/2507.15349)
2. **Zehua Cheng**, Manying Zhang, Jiahao Sun, and Wei Dai. "On weaponization-resistant large language models with prospect theoretic alignment." In Proceedings of the 31st International Conference on Computational Linguistics, pp. 10309-10324. 2025. [[Paper]](https://aclanthology.org/2025.coling-main.687.pdf)

## Nash-Equilibrium Data Valuation: The Shapley Protocol

*The Moonshot*: Solving the "Free Rider Problem." In current federated learning, a hospital that contributes junk data gets the same model as a hospital that contributes gold. This protocol automatically pays data owners based on the exact marginal utility of their contribution.

**The Hard Problem**: Calculating the true Shapley Value is $O(N!)$—impossible to compute for thousands of nodes.

* **Gradient-Based Influence Functions**: Instead of retraining the model $N$ times to measure value, we approximate value by analyzing the cosine similarity of a node's gradient update relative to the "Gold Standard" validation set held by the protocol.
* **The Payment Stream**: A smart contract layer (L2) that acts as a "Streaming Payment" engine. Every time a node sends a gradient that reduces the global loss, micro-payments flow to their wallet. If they send noise, they get slashed (fined).
* **Equilibrium Discovery**: We prove mathematically that "Honest Contribution" is the Nash Equilibrium of this game—cheating is always less profitable than contributing.
