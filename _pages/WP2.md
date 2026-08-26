---
title: "Structured Machine Reasoning"
permalink: /episteme/
redirect_from:
  - /sie/
author_profile: true
---

A language model trained to predict the next token learns *doxa* — opinion that is plausible, fluent, and carries no account of why it should be believed. It can be right without being justified, and it cannot tell the two apart. We build the other thing: the **episteme**, the space of admissible conclusions, written down in mathematics, that a model computes *inside* rather than merely aims at.

If you are interested in any of this project, please feel free to contact me. :)

# The Episteme

> An **ontology** defines what exists. An **episteme** defines the space of valid reasoning over it. We construct the second one — as factor graphs, automata, symmetry groups and curvature — and make a language model inhabit it.

## Doxa and Episteme

The distinction is old and unusually well suited to what has gone wrong. *Doxa* is belief that may be true but has no *logos* — no account of its own warrant. *Episteme* is knowledge that comes with the structure that makes it knowledge. In the Foucauldian reading the episteme is stronger still: not a set of true statements, but the conditions that determine what could count as a valid claim at all.

That is the object we are building, and the reason "add more data" is the wrong instinct. A frontier model is an extraordinary doxa machine. In medicine, finance and science, doxa is not a lower grade of knowledge — it is a liability with a fluent surface. A synthetic patient record asserting *Viral Pneumonia* without *Infectious Disease* is not slightly wrong; it is a well-formed falsehood, and no amount of scale makes a well-formed falsehood detectable from inside the distribution that produced it. Retrieval, fine-tuning and prompting are all *doxastic* interventions: they move a probability. None of them change what is **possible**.

The engineering claim is that the conditions of validity are formalisable — as constraint systems, graphical models, invariances and metric geometry — and that once formalised they can be imposed on a network rather than hoped for. The scientific claim is sharper, and it is the result the programme rests on: **in-context learning is approximate belief propagation.** If a transformer's forward pass already runs message passing over an implicit factor graph, then it is already doing inference inside an episteme — just an accidental one, inherited from pretraining and unavailable for inspection. The work is to make that episteme explicit, correct, and ours to specify.

This is neuro-symbolic AI without the apology. The symbols are not a filter bolted to the output; they are the coordinate system the network computes in.

## I. Defining the Episteme

*The Moonshot*: A generative model that **cannot** emit an inadmissible artefact — not "rarely does", not "validates afterwards", but cannot — while staying diverse enough to be worth sampling from.

**The Hard Problem**: Admissibility and diversity pull against each other. Every mechanism that pins output to a schema — templates, rejection sampling, grammars — collapses the distribution onto a few safe modes, and a synthetic corpus with no entropy teaches a downstream model nothing. Worse, validity in real domains is not local: ICD hierarchies, netlist connectivity and financial schemas impose *global* consistency that no token-by-token filter can see.

* **The Blueprint Layer**: Before a token exists, we sample a *structural plan* — a joint configuration of attributes and their relations — from a probabilistic factor graph. Entropy is spent where it is safe (the plan) rather than where it is dangerous (the surface form). This is what lets us move along the diversity–reliability frontier instead of trading one against the other.
* **The Constraint Compiler**: The domain's hard rules compile to finite automata, intersected with the decoder. A token that would leave the admissible space is assigned probability *zero* — not low, zero. The guarantee is automaton-theoretic, so it holds for every sample rather than in expectation.
* **Joint Decoding, Not Greedy Decoding**: Autoregressive decoding is a left-to-right heuristic for a genuinely joint problem. We build empirical pairwise factor graphs over the output's fields and decode by Bethe-style consensus, so a commitment made early remains answerable to evidence arriving late.
* **Causal Rather Than Correlational Admissibility**: A record can satisfy every schema constraint and still be counterfactually absurd. Generating against a causal graph makes interventions on the data-generating process behave as the domain says they must.
* **The Boundary of the Episteme**: Hard constraints say what is impossible; they say nothing about what is *warranted*. Over the masked space we run single-pass conformal inference on the graphical model, using cavity distributions to emit prediction sets with finite-sample coverage. Calibration for structured outputs, at the cost of one forward pass rather than a resampling loop — the episteme acquires a measurable edge, not just walls.
* **Perception Under the Same Discipline**: Vision gets no exemption. Rather than describing an image, we synthesise a *program* over set-based visual representations, so compositional visual reasoning is executed and checkable instead of narrated.

## II. Traversing the Episteme

*The Moonshot*: Reasoning that stays inside the admissible space for thousands of steps, and that can be **repaired** at the point it departs rather than resampled from scratch.

**The Hard Problem**: Long chain-of-thought is now the dominant way to buy accuracy at test time, and it is built on sand. Representations of distinct intermediate facts drift into one another as context grows, so a chain rarely fails with a visible error — it fails by quietly forgetting what it had established. And because traces are generated forwards only, one corrupted step contaminates everything downstream of it.

* **Orthogonal Subspace Anchoring**: Reasoning states are assigned to near-orthogonal subspaces of the representation, so holding one fact does not overwrite another. Interference stops being an emergent mystery and becomes a geometric quantity we can bound.
* **Bidirectional Logic**: A valid path should be checkable from both ends. Equipping the model with backward as well as forward entailment lets a broken link be localised and rewritten against the conclusion it was meant to support — repair rather than restart.
* **Reasoning That Survives Distillation**: Small models inherit a teacher's answers far more readily than its warrant. We align *gradients* rather than outputs, transferring the invariances that constitute the reasoning instead of the surface behaviour that flatters a benchmark. (See §IV.)

## III. Computing the Episteme

*The Moonshot*: Inference machinery that is **correct by symmetry** — where the invariances and curvature of the domain are properties of the architecture, not lessons we hope the data will teach.

**The Hard Problem**: Belief propagation is the right algorithm for a great deal of structured reasoning and the wrong algorithm for real graphs: exact only on trees, fragile under loops, and indifferent to the fact that most interesting structures are neither flat nor arbitrary. Learned message passing repairs the fragility and immediately forfeits the guarantees — a learned update has no reason to respect the permutation symmetry of a factor, and Euclidean embeddings distort hierarchy at an exponential rate.

* **Equivariant Message Passing**: Learned updates are constrained to be equivariant to the symmetry group of the factor graph. The network cannot learn to treat exchangeable variables differently, because the hypothesis class does not contain that error.
* **Hyperbolic Belief Propagation**: Hierarchies — taxonomies, ontologies, code, institutions — embed into hyperbolic space with vanishing distortion and into Euclidean space with a great deal. Doing inference in the geometry the data actually occupies turns a representational impossibility into a choice of curvature.
* **In-Context Learning as Belief Propagation**: The theoretical spine. If attention implements approximate message passing, then in-context learning's competences *and* its pathologies are jointly predicted by the theory of loopy BP — and everything above becomes a design language for what happens inside the forward pass, rather than a wrapper around it.

## IV. Embodying the Episteme

*The Moonshot*: Read a model's loss geometry and know, **before** training, whether two bodies of competence will compose or destroy each other.

**The Hard Problem**: An episteme, once trained, is embodied in weights — which means composing two of them is a geometric question that we currently answer by trial and error at enormous cost. We can measure that a merge failed or that two objectives interfered; we cannot predict it. The information needed sits in the curvature of the loss surface and in how gradients interact across tasks, and both have been dismissed as too expensive to look at.

* **Curvature Graph Mergeability**: Per-layer Hessian geometry, characterised as a graph, predicts model compatibility — turning "merge and pray" into a computation performed in advance.
* **Gradient Interaction Graphs**: Conflict between objectives is structure, not noise. Modelling the interaction between task gradients explicitly, and optimising over that graph, lets constructive and destructive interference be scheduled rather than suffered.
* **Invariant Gradient Alignment**: The same lens on distillation. Match invariances in gradient space and the reasoning transfers; match outputs alone and only the answers do.

## Where This Is Going

The four sections are one system. Structured perception feeds an admissible generator; a constrained decoder is bounded by conformal inference; the reasoning that drives it runs on an engine with the right symmetry and curvature, over parameters whose geometry was chosen rather than inherited. The target is an inference layer that an autonomous agent can stand on in domains where a confident mistake is expensive — clinical and financial reasoning first — with the property that its guarantees are **stated** rather than benchmarked.

An ontology tells such an agent what the world contains. The episteme tells it what it is entitled to conclude.

# Publications

**I. Defining the Episteme** — admissible generation and structured outputs

1. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*GraphSynth: Resolving the Diversity-Reliability Trade-off with Probabilistic Factor Graphs*". In Proceedings of ACL 2026. [[Paper]](https://aclanthology.org/2026.acl-long.1969/)
2. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*CircuitSynth: Reliable Synthetic Data Generation*". In Proceedings of ACL Findings 2026. [[Paper]](https://arxiv.org/abs/2604.10114)
3. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*CausalSynth: Generating Structurally Sound Synthetic Data*". Arxiv. [[Paper]](https://arxiv.org/abs/2605.17528)
4. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Bethe Consensus Decoding: Joint Inference on Empirical Pairwise Factor Graphs for Structured LLM Outputs*". In Proceedings of CIKM 2026.
5. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Cavity-Calibrated Prediction Sets: Single-Pass Conformal Inference for Structured Outputs over Graphical Models*". In Proceedings of CIKM 2026.
6. **Zehua Cheng**, Wei Dai, Wenhu Zhang, Thomas Lukasiewicz, and Jiahao Sun. "*Visual Set Program Synthesizer*". In Proceedings of IEEE International Conference on Multimedia and Expo 2026. [[Paper]](https://arxiv.org/pdf/2603.15997)

**II. Traversing the Episteme** — long-horizon reasoning and repair

7. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*HoloCoT: Holographic Chain-of-Thought via Orthogonal Subspace Anchoring for Persistent Long-Horizon Reasoning*". In Proceedings of ECML-PKDD 2026.
8. **Zehua Cheng**, Wei Dai, Jiahao Sun, and Thomas Lukasiewicz. "*Imbuing Large Language Models with Bidirectional Logic for Robust Chain Repair*". In Proceedings of ECML-PKDD 2026.
{: start="7"}

**III. Computing the Episteme** — neural inference engines

9. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Hyperbolic Belief Propagation*". In Proceedings of UAI 2026. [**ORAL**]
10. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Equivariant Neural Belief Propagation*". In Proceedings of UAI 2026.
11. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*In-Context Learning as Belief Propagation*". In Proceedings of CIKM 2026.
{: start="9"}

**IV. Embodying the Episteme** — geometry of training and model composition

12. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Curvature Graph Mergeability: Predicting Model Compatibility from Per-Layer Hessian Geometry*". In Proceedings of CIKM 2026.
13. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Gradient Interaction Graph Optimization*". In Proceedings of CIKM 2026.
14. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Invariant Gradient Alignment for Robust Reasoning Distillation*". In Proceedings of ECML-PKDD 2026.
{: start="12"}

Applications

15. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Timescale-Disentangled Generative Models of Protein Dynamics*". In Proceedings of IEEE ICDM 2026.

16. **Zehua Cheng**, Wei Dai, and Jiahao Sun. "*Transition Path Diffusion for Protein Reactive Trajectories*".  In Proceedings of IEEE ICDM 2026.

    {: start="15"}
