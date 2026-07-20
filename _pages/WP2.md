---
title: "Reliable Representations for AI"
permalink: /sie/
---

If you are interested in any of this work, please feel free to contact me. :)

# The Structured Inference Engine (SIE)

> **Core thesis:** Reliable representations are a better harness for AI. When we give models structured, mathematically grounded representations — instead of relying on raw pattern matching — they become more trustworthy across the *entire* AI lifecycle: from data to deployment.

## The Problem

Modern AI is powerful but fragile. Models "guess" well on average, but in high-stakes domains — medicine, finance, science — "mostly correct" is a failure mode. A synthetic patient record that links "Viral Pneumonia" without "Infectious Disease" is not just wrong; it is dangerously wrong. Current approaches (RAG, fine-tuning, prompting) offer soft guidance but cannot *guarantee* structural correctness.

We believe the fix is not bigger models or more data. It is **better representations** — ones that encode the causal, geometric, and logical structure of the problem — so that every stage of the AI pipeline produces outputs that are reliable by construction.

## Our Approach: Reliable Representations Across the AI Lifecycle

The SIE is not a single system but a research programme. Each project addresses a different stage of the AI lifecycle, unified by one principle: *embed structural knowledge into the representation itself*.

| Lifecycle Stage | What We Do | Key Work |
|---|---|---|
| **Data Pipeline** | Generate synthetic data that obeys real-world constraints (medical codes, financial schemas) — so models train on structurally sound data from the start | GraphSynth, CircuitSynth, CausalSynth |
| **Model Pretraining & Alignment** | Distill reasoning ability into smaller models without losing structural consistency, using gradient-level alignment | Invariant Gradient Alignment |
| **Model Inference** | Compile domain rules into hard constraints (automata) that mask out impossible outputs during generation — guaranteeing valid structure at decode time | CircuitSynth (DFA Masking) |
| **Chain-of-Thought Reasoning** | Anchor reasoning chains in geometric subspaces so they stay coherent over long horizons, and repair broken chains with bidirectional logic | HoloCoT, Bidirectional Chain Repair |
| **Structured Perception** | Synthesize visual programs from set-based representations, enabling compositional visual reasoning | Visual Set Program Synthesizer |
| **Large-Scale Systems** | Propagate beliefs through structured graphs using symmetry-aware (equivariant) message passing — scaling reliable inference to complex systems | Equivariant Neural Belief Propagation |

### How It Works (The Three Layers)

At the heart of SIE are three complementary mechanisms:

1. **The Blueprint Layer** — Before generating anything, we sample a *structural plan* (a configuration of attributes and their relationships) using probabilistic factor graphs. This ensures the output’s skeleton is valid before a single token is produced.

2. **The Constraint Compiler** — We compile the domain’s hard rules into finite automata. During generation, these automata act as a mask: any token that would violate the rules is assigned zero probability. Not "low" probability — *zero*.

3. **The Semantic Verifier** — A real-time checker runs alongside generation, verifying each candidate fact (e.g., *Drug X treats Disease Y*) against a knowledge graph. If a fact doesn’t check out, it’s caught immediately — not after the fact.

## Publications

1. **Zehua Cheng**, Wei Dai, Wenhu Zhang, Thomas Lukasiewicz, and Jiahao Sun. "Visual Set Program Synthesizer". In Proceedings of IEEE International Conference on Multimedia and Expo 2026. [Paper](https://arxiv.org/pdf/2603.15997)

2. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*GraphSynth: Resolving the Diversity-Reliability Trade-off with Probabilistic Factor Graphs*". In Proceedings of ACL 2026. [Paper](https://aclanthology.org/2026.acl-long.1969/)

3. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*CircuitSynth: Reliable Synthetic Data Generation*". In Proceedings of ACL Findings 2026. [Paper](https://arxiv.org/abs/2604.10114)

4. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*CausalSynth: Generating Structurally Sound Synthetic Data*". Arxiv. [Paper](https://arxiv.org/abs/2605.17528)

5. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*Imbuing Large Language Models with Bidirectional Logic for Robust Chain Repair*". In Proceedings of ECML-PKDD 2026.

6. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*HoloCoT: Holographic Chain-of-Thought via Orthogonal Subspace Anchoring for Persistent Long-Horizon Reasoning*". In Proceedings of ECML-PKDD 2026.

7. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Invariant Gradient Alignment for Robust Reasoning Distillation*". In Proceedings of ECML-PKDD 2026.

8. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Equivariant Neural Belief Propagation*". In Proceedings of UAI 2026.