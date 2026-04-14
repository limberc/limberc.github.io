---
title: "Causal & Geometric Reasoning"
permalink: /sie/
---

We build autonomous agents that reason over distributed, high-stakes data (Bio & Finance) without ever centralizing it. We replace trust with cryptography and replace correlation with causal/structural reasoning.

If you are interested in any of this project, please feel free to contact me. :)

# The Structural Inference Engine (SIE)

> We move from "Probabilistic Token Prediction" to "Structural Reasoning." Our agents generate solutions constrained by geometric symmetry (Physics) and causal graphs (Logic).

The Moonshot: Standard LLMs are probabilistic—they 'guess' the next token. We are building the Deterministic Structural Engine—an LLM that generates data (molecules, contracts, causal graphs) that is mathematically guaranteed to obey the strict schema and semantic constraints of the real world.

**The Hard Problem:** In high-stakes domains, "mostly correct" is a failure. A synthetic patient record cannot have disjoint medical codes (e.g., "Viral Pneumonia" without "Infectious Disease"). A financial contract cannot violate regulatory schemas. Current methods (RAG or Fine-tuning) offer "soft" guidance but cannot enforce hard logical consistency.

* **The Blueprint Layer** (Factor Graph Priors): Instead of sampling tokens directly, the engine first samples a target subspace (a configuration of attributes) using a Probabilistic Factor Graph.
* **The Constraint Compiler** (The Hard Mask): Compile the domain's rigid rules into Deterministic Finite Automata (DFA). During inference, these automata project a "Hard Mask" onto the LLM’s vocabulary. Any token that would violate the schema is mathematically assigned zero probability.
* **The Semantic Verifier** (The Loop): A token-level verifier runs in parallel with the generation. It checks candidate facts (Subject-Relation-Object) against a retrieved Knowledge Graph in real-time.

**Relevant Publications**:

1. **Zehua Cheng**, Wei Dai, Wenhu Zhang, Thomas Lukasiewicz, Jiahao Sun. "Visual Set Program Synthesizer". In Procedings of IEEE International Conference on Multimedia and Expo 2026. [Paper](https://arxiv.org/pdf/2603.15997)
2. **Zehua Cheng**, Wei Dai, Jiahao Sun, Thomas Lukasiewicz. "*GraphSynth: Resolving the Diversity-Reliability Trade-off with Probabilistic Factor Graphs*" In Procedings of ACL 2026.
3. **Zehua Cheng**, Wei Dai, Jiahao Sun, Thomas Lukasiewicz. "*CircuitSynth: Reliable Synthetic Data Generation*". In Procedings of ACL Findings 2026. [Paper](https://arxiv.org/abs/2604.10114)