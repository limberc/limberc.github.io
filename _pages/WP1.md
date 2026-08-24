---
title: "Decentralized Machine Learning"
permalink: /infra/
author_profile: true
---

We build machine learning systems that have no center. No node holds the data, no operator holds the model, and no party has to be trusted — the guarantees come from mathematics and mechanism design instead. Two things follow from that: the **systems** that make a global mesh converge, and the **language models** that can be trained and served on top of one. We call it the **Rhizome**.

If you are interested in any of this project, please feel free to contact me. :)

# The Rhizome

> We replace **Trust** (institutional reputation) with **Math** (cryptography) and **Incentives** (game theory).

## The Tree and the Rhizome

Deleuze and Guattari drew the distinction we need. An *arborescent* structure has a root: a trunk, a hierarchy, and a path from every leaf back to a single origin. A *rhizome* has none — any point connects to any other, the things it connects need not be alike, and it can be severed at any point and resume along its old lines or new ones. Cut a tree's root and the tree dies. Cut a rhizome anywhere and it regrows from the fragment.

Contemporary AI is arborescent to an extreme degree. One organisation holds the corpus, the weights, the compute and the authority to decide what the model should value; every capability traces back to that root, and so does every reason anyone has to trust the result. The tree's guarantee *is* the root's reputation.

Remove the root and two things happen at once. The reputational guarantee vanishes — which is why trust has to be reconstructed from cryptography and game theory rather than assumed, and why the line above is a consequence of the topology rather than a slogan attached to it. And failure stops being exceptional: in a mesh of consumer GPUs, hospital servers and idle workstations, nodes leave mid-step, links partition, and some participants are actively adversarial. A rhizome is defined by its capacity to resume after rupture, so churn, partition and Byzantine behaviour are the operating condition, not the edge case. That is the engineering standard the three sections below are held to.

## I. The Substrate

*The Moonshot*: Construct a single, coherent, trillion-parameter intelligence that lives purely on the dormant, fragmented compute of the world's existing infrastructure — consumer GPUs, hospital servers, idle research workstations — connected only by the public internet.

**The Hard Problem**: To maintain a unified global intelligence across a network where **physical latency** fractures real-time inference, **localized learning** drives mathematical divergence, and **hardware asymmetry** destabilizes synchronization.

* **Chronos**: The speed of light imposes a hard, immutable limit on distributed intelligence, paralyzing model execution whenever a neural network spans geography. To cheat this physics, the Chronos Module decouples logical thought from network transmission, using lightweight local "ghost" models to hallucinate the outputs of remote experts instantly and consulting the network only when a compressed *holographic sketch* detects a deviation from reality. This architectural sleight-of-hand effectively erases the latency penalty of the open internet, letting a global mesh infer with the responsiveness of a single local chip.
* **Spectral State Synchronization**: Where independent nodes learn from private, local data, their internal mathematical definitions inevitably drift apart until they are speaking mutually unintelligible languages. This module prevents the Tower of Babel by continuously projecting local weight updates into a lower-dimensional *spectral space* and broadcasting these tiny mathematical sketches as a unifying signal. The mechanism acts as a form of mathematical gravity, constantly pulling thousands of isolated, evolving models back toward a coherent global consensus without ever clogging the bandwidth pipes with raw heavy parameters.
* **Verifiable Contribution**: A node that claims it trained should have to prove it. We compose proofs recursively — the proof for step $N$ verifies the proof for step $N-1$ — so the cost of verification stays sublinear in the length of the training run rather than exploding with it, and we seed SGD batches from an on-chain Verifiable Random Function so that a node cannot cherry-pick easy data to manufacture a convincing loss curve.

## II. Training Without a Curator

*The Moonshot*: Post-train a frontier-scale language model when no single party holds the preference data, and no single party holds the authority to define what the reward should be.

**The Hard Problem**: Alignment as currently practiced presumes a central curator — one organization that collects the preferences, writes the constitution, and owns the reward model. That curator is the root of the tree. Remove it and the problem inverts: preferences arrive from mutually distrustful data owners whose values genuinely differ, the data cannot leave the premises it was collected on, and some fraction of the network has an active interest in making the model *less* aligned.

* **Prospect-Theoretic Preference Aggregation**: Human preferences over risk are asymmetric — losses loom larger than gains — and naive averaging across nodes flattens exactly the asymmetry that makes a model refuse. We aggregate preferences under a prospect-theoretic utility rather than a linear one, so that safety behaviour survives contact with a heterogeneous federation instead of being averaged out of existence.
* **Sketch-Compressed Post-Training**: The gradient sketches that make decentralized pretraining feasible are usually abandoned at the post-training stage, where the updates are assumed small enough not to matter. They are not. We extend the learned sketch operator through the reinforcement phase, keeping the bandwidth cost of alignment on the same order as the bandwidth cost of pretraining.
* **Byzantine-Robust Reward Consensus**: A node that contributes poisoned preference pairs should not be able to move the aggregate reward model, and should not be able to hide the attempt. We treat reward learning as a consensus problem rather than an estimation problem, bounding the influence any single contributor can exert regardless of how much data they claim to hold.

## III. Serving Without an Operator

*The Moonshot*: Run one frontier-scale model across many independent operators, where no operator sees the full prompt, the full weights, or the identity behind the query — and the user still gets an answer at interactive latency.

**The Hard Problem**: Privacy-preserving inference and fast inference have historically been mutually exclusive. Every mechanism that hides the query from the operator — encryption, secret sharing, obfuscation — adds round trips, and every mechanism that adds round trips is fatal on a network whose participants are separated by continents.

* **Identity-Decoupled Retrieval**: Retrieval-augmented generation leaks in a way generation alone does not: the evidence a model retrieves is often more identifying than the question that retrieved it, and for visual evidence this is acute. We decouple the identity carried by a piece of evidence from the semantic content that makes it useful for grounding, so a document or an image can serve as evidence in a multi-modal pipeline without carrying a person into it.
* **Sharded Experts Under Query Obfuscation**: Routing a token stream across operators reveals the stream. We shard experts so that the routing pattern any single operator observes is insufficient to reconstruct the prompt, treating the leak as a property of the sharding topology rather than something to be patched at the application layer.
* **Speculative Serving**: The latency budget for all of the above comes from the same place Chronos finds it — local ghost models that predict remote expert outputs and consult the network only when prediction and reality diverge.

## Where This Is Going

The three sections describe one artefact from three angles: a substrate that converges without a coordinator, a model aligned without a curator, and a service delivered without an operator who can see what it is delivering. None of the three is interesting alone — a mesh that converges but leaks, or a model aligned by a federation but served from one datacenter, has simply moved the root rather than removed it. The target is a full stack with no privileged position anywhere in it, and with each guarantee stated as mathematics rather than as a policy someone promises to follow.

# Publications

**I. The Substrate**

1. **Zehua Cheng**, Rui Sun, Jiahao Sun and Yike Guo. (2025). "*Scaling Decentralized Learning with FLock.*" In Proceedings of 2025 IEEE/WIC International Conference on Web Intelligence and Intelligent Agent Technology (WI-IAT). [**WI-IAT 2025 - Best Paper Award (Industrial)**] [[Paper]](https://arxiv.org/abs/2507.15349)
2. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Decentralized Learning with Communication-Efficient Learned Gradient Sketches*". In Proceedings of International Conference on Parallel Processing 2026.

**II. Training Without a Curator**

3. **Zehua Cheng**, Manying Zhang, Jiahao Sun, and Wei Dai. "*On weaponization-resistant large language models with prospect theoretic alignment*." In Proceedings of the 31st International Conference on Computational Linguistics, pp. 10309-10324. 2025. [[Paper]](https://aclanthology.org/2025.coling-main.687.pdf)
{: start="3"}

**III. Serving Without an Operator**

4. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Identity-Decoupled Anonymization for Visual Evidence in Multi-modal Retrieval-Augmented Generation*". In Proceedings of 16th ACM International Conference on Multimedia Retrieval 2026.
5. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Graph-Driven Context-Preserving Anonymization: Decoupling Identity from Reasoning in LLM Training Corpora*". In Proceedings of CIKM 2026.
{: start="4"}
