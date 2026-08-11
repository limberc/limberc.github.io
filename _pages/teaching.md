---
title: "Teaching"
permalink: /teaching/
author_profile: true
---

I teach **Secure AI Systems** at the [School of Cybersecurity](https://security.korea.ac.kr/), Korea University, where I am an Adjunct Professor.

# Secure AI Systems

*Graduate course · School of Cybersecurity, Korea University · Spring 2026 (first offering)*

The course addresses, with the rigour a graduate program demands, the question of how to design, build, deploy, evaluate, and govern systems whose central component is a large language model. Machine-learning training teaches the mathematics of optimization and the practice of empirical evaluation, but not the adversarial mindset by which systems are tested against motivated attackers. Security training teaches the adversarial mindset, threat modelling, and structured disclosure, but not the mechanics of stochastic systems whose specification is the joint product of training data, training procedure, and runtime configuration. A serious treatment of LLM systems requires both — and that requirement is the motivation for the course.

## Textbook

I wrote a textbook for the course, and it is free to download.

<a href="{{ base_path }}/files/Secure_AI_Systems.pdf" class="btn btn--large" download>Download the textbook (PDF, 227 pages, 5.1 MB)</a>

> **Secure AI Systems — A Graduate Textbook on the Security and Reliability of Large Language Model Systems.**
> Zehua Cheng. School of Cybersecurity, Korea University. Edition v0.12

The notes are designed to be read *alongside* the assigned papers rather than in place of them: they situate the papers, give working mental models, and provide the structural memory that makes the papers stick. Each chapter aligns with one week of the lecture plan, opens with a set of guiding questions, and closes with a key-papers list, a short self-check, and a look-ahead to the next chapter.

A note on shelf life. The field these notes survey did not exist as an organised subject in 2020; most of what is currently believed to be true about secure LLM systems was discovered in the last three years. **Anything in these notes can be obsolete within a year**, and the assigned reading list is updated each semester accordingly. Treat the notes as scaffolding, not scripture.

## Syllabus

The textbook follows the **LLM lifecycle** — data sourcing, pretraining, post-training, evaluation, packaging, deployment, monitoring, governance. Each chapter addresses one stage of the lifecycle or one cross-cutting concern, and each asks three questions: what fails at this stage, which attacks apply, and which defences actually work.

**Part I — Foundations**

1. Why "Secure AI" is a new field
2. Threat modelling for AI systems (STRIDE → MAESTRO, attack trees, the capability–context square)
3. The LLM lifecycle as the attack surface
4. Threat landscape & adversary models (incl. the OWASP LLM Top 10)

**Part II — Data & training-time security**

5. Data pipeline: security & reliability (poisoning at web scale, PII filtering and Korean PIPA, deduplication, drift)
6. Training-time attacks (backdoors, model supply chain, fine-tuning attacks on aligned models)
7. Alignment, RLHF & safety training (reward hacking, sleeper agents, alignment-faking)

**Part III — Inference-time attacks**

8. Direct prompt injection and jailbreaks
9. Indirect prompt injection and agentic LLM security (autonomy budgets, computer-use agents, MCP)
10. Multi-modal attacks & RAG security

**Part IV — Privacy & deployment**

11. Privacy & confidentiality attacks (membership inference, extraction, DP, machine unlearning)
12. Secure deployment & efficient inference (vLLM and KV-cache attacks, quantisation × safety tradeoffs, cost-DoS, incident response)

**Part V — Governance & methodology**

13. Governance, regulation & responsible disclosure (EU AI Act, U.S. EO 14110 → AISI, Korea AI Basic Act, NIST AI RMF)
14. Red-team methodology (rules of engagement, attack reports, automated red-teaming)
15. Evaluation, benchmarks, and the contamination problem
16. Future directions (2026–2028) and open problems for a thesis

**Appendices**

- **A** — Lab guides
- **B** — Background primer for readers coming from other backgrounds (self-attention from scratch, RLHF/DPO mathematics, DP-SGD, quantisation, retrieval, notation cheat-sheet)
- **C** — Mock interview questions for aspiring researchers

## Labs & project

Assessment is built around five hands-on labs and a term project.

| Lab | Topic | Weeks |
|-----|-------|-------|
| 1 | Threat model a real LLM product | W3 → W4 |
| 2 | Poison-resilient data filter | W4 → W6 |
| 3 | Jailbreak suite | W8 → W9 |
| 4 | Harden a RAG | W10 → W11 |
| 5 | Deploy + monitor | W12 → W13 |

The term project runs on tracks (attack, defence, evaluation, governance) and is described in Appendix A.

## Prerequisites

You should already know: how a Transformer block computes attention; what self-supervised pretraining means; the rough shapes of an SFT and an RLHF/DPO pipeline; how an HTTP request and a Docker container work; what STRIDE, the CIA triad, and a threat model are.

These prerequisites are not gating — a student lacking them can still pass — but they are foundational, in the sense that the course's material assumes them without re-derivation. Chapters 1–4 introduce the security vocabulary at a working level, so a student with an ML background can acquire the security side during the course; the reverse is less true, since the chapters do not introduce ML concepts from scratch. Students uncertain about their preparation should take the **Week 1 calibration quiz**, which routes those below the threshold to a supplementary reading packet (Appendix B). The intervention works much better in Week 1 than in Week 8.

## Invited lectures

- 04/2026 — Invited Guest Lecture, *AI Safety and Governance in the Era of LLM*, COMP60272 AI Security & Privacy, University of Manchester.
- 04/2026 — [Invited Lecture, *Building Reliable and Trustworthy LLM*](https://security.korea.ac.kr/m06_04/105), Korea University.

---

Corrections, questions, and reports of things that have already gone obsolete are welcome.
