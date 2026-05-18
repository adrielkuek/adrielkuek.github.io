---
title: "Toward Agentic Research Workflows"
date: 2026-05-18
draft: false
summary: "Thinking about how AI agents can automate the research lifecycle — from literature review through experimentation to paper drafting."
tags: ["agentic AI", "research automation", "foundation models"]
categories: ["AI Research"]
---

The research workflow — literature review, hypothesis generation, experimental design, execution, evaluation, and writing — is fundamentally a sequence of decisions with feedback loops. Most of these decisions are currently manual. What happens when agents can handle the loop?

## The Current Bottleneck

Modern AI research moves fast. The volume of new papers far outpaces any single researcher's reading capacity. The bottleneck isn't compute — it's the human research cycle:

- **Discovery** — finding relevant work before someone else does
- **Synthesis** — connecting ideas across papers into something new
- **Execution** — designing experiments, writing code, iterating
- **Communication** — writing papers that actually convey the insight

Agents don't solve all of these, but they shift the bottleneck upstream.

## What Agentic Research Looks Like

Rather than treating LLMs as autocomplete for code or prose, the agentic approach treats them as **planning and orchestration layers**:

> An agent that can read a paper, extract the core contribution, file it under the right concept, and suggest experiments that build on it — is already useful.

The key insight from our work with **OmegaWiki** is that **structured knowledge compounding** matters more than raw retrieval. A maintained wiki where concepts link, build, and evolve beats a vector database of embeddings every time.

## Research Wiki as Infrastructure

The idea is simple: instead of RAG over a flat corpus, maintain a **structured knowledge graph** where each entity (paper, concept, method, experiment) has:

1. A canonical summary written by an agent after reading
2. Bidirectional links to related entities
3. A running summary of the current state of the field

This turns the wiki into a **compounding asset** — each new paper ingested increases the value of prior entries through newly discovered connections.

## The Loop

The research loop looks like:

```
ingest → discover → ideate → novelty-check → experiment → evaluate → write
  ^                                                      |
  +------------------------------------------------------+
```

Each step is agent-driven, human-guided. The human sets the direction, constraints, and evaluation criteria. The agent handles the execution, bookkeeping, and synthesis.

## What's Missing

The hard part isn't the agent orchestration — it's **quality control**. Agents hallucinate connections, oversimplify papers, and miss nuance. The current best approach is:

- **Deterministic tooling** for wiki operations (no guessing in file structure)
- **Human review gates** at key decision points
- **Incremental verification** — each agent output gets validated before the next step

This isn't fully autonomous research. It's **augmented research with automation**. And that's already a meaningful step.

## Next Steps

The next iteration involves better **novelty detection** — can an agent survey the current literature and identify genuinely new research directions? Early experiments suggest: yes, with caveats. The signal-to-noise ratio is low, but the hits are worthwhile.

More on this as we iterate.
