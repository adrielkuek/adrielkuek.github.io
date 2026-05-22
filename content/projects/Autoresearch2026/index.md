---
title: "OUROBOROS — Accelerating AI Research Through Iterative Evolution"
date: 2026-05-22T10:00:00+08:00
draft: false
slug: ouroboros-autoresearch
description: "Exploring autonomous AI research systems through multi-agent evolutionary experimentation."
summary: "A deep dive into OUROBOROS — a multi-agent autonomous AI research swarm designed to accelerate foundation model experimentation and iterative scientific discovery."
featured: true
tags:
  - AI Research
  - Foundation Models
  - Agentic AI
  - AutoResearch
  - Multimodal AI
categories:
  - research
cover: /images/OUROBOROS/cover.png
status: "completed"
---

## Back in March 2026...

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Back in March 2026, when Andrej Karpathy released <em>AutoResearch</em>, it immediately felt like one of those deceptively small moments that quietly reshapes a field. A lightweight repo, a simple experimental loop — and suddenly the GPU wasn't just training models anymore, it was participating in the research process itself. There was much fanfare surrounding Karpathy’s viral tweet, but here in IE, we immediately cut through the fog and moved quickly to evaluate whether autonomous AI research was merely another marketing stunt or something genuinely useful for our research work in DSO.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The TLDR was straightforward. We ran the same automated-research problem — discovering a novel foundation-model merging method for post-training capability recovery — under two organisational regimes with roughly the same compute budget. One used a single-agent empirical loop. The other used a captain-led swarm of collaborative research teams operating in parallel. <em>The swarm produced more diverse and theoretically grounded augmentations; the single agent achieved the best validation-loss score.</em> While neither fully generalised on held-out benchmarks, the larger conclusion was difficult to ignore: <strong>autonomous iterative research has become practically useful</strong>, and perhaps slightly unsettling in the same way calculators once were to arithmetic teachers.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig1.png"
    alt="Figure 1"
    style="
      width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
    "
  />

  <p style="
      text-align: center;
      font-size: 0.92rem;
      font-style: italic;
      opacity: 0.75;
      margin-top: 0.9rem;
      line-height: 1.6;
    ">
    Figure 1: Comparisons of evolutionary discovery capabilities in search rigor and breadth.
  </p>

</div>

---

## What is AutoResearch?

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
AutoResearch itself is conceptually simple. An AI coding agent autonomously runs machine-learning experiments toward a target objective. It reads results, proposes modifications, edits code, launches jobs, evaluates outputs, and either commits or reverts changes. Then the loop repeats until an experimental cut-off limit is reached or when the compute budget quietly evaporates into the void. The underlying idea is not entirely new — the lineage stretches from early Neural Architecture Search (NAS) and AlphaEvolve-style evolutionary search to more recent systems like Sakana AI's <em>AI Scientist</em>. What changed in 2026 was that the workflow became operationally coherent enough for researchers to seriously integrate into day-to-day experimentation, rather than it remaining solely as a neat conference demonstrator.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig2.png"
    alt="Figure 2"
    style="
      width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
    "
  />

  <p style="
      text-align: center;
      font-size: 0.92rem;
      font-style: italic;
      opacity: 0.75;
      margin-top: 0.9rem;
      line-height: 1.6;
    ">
    Figure 2: The single-agent autoresearch loop.
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Three public systems helped crystallize the space. Karpathy’s <em>AutoResearch</em> represented the minimalist single-agent ratchet loop: one agent, one metric, relentless hill-climbing. Sakana’s <em>AI Scientist-v2</em> demonstrated best-first tree search exploring parallel hypothesis branches through structured search. <em>AutoResearchClaw</em> packaged the process into a HITL-aware sequential research pipeline with citation verification and staged approvals — essentially “enterprise autoresearch,” complete with enough process checkpoints to make access to post-grad-level research feel mildly alarming.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Drawing inspiration from all three, we developed <strong>OUROBOROS</strong> — a composite multi-team swarm framework with controlled self-evolution capabilities. Basically, AutoResearch on steroids. OUROBOROS occupies a different corner of the design space. Instead of a single agent doing everything, the framework spins up parallel research teams operating collaboratively across multiple phases, each paired with theorist agents generating formal derivations, QA agents enforcing directional discipline, and a Cross-Pollinator synthesis agent continuously hybridizing promising directions across teams.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The target domain was Foundation Model merging — recovering reasoning, instruction-following, or chat capabilities by carefully combining model weights and behaviours into a unified model. Or, in more lay terms, convincing several neural networks to cooperate without them behaving like a badly coordinated group project.
</p>

---

## Our Experiment

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Our experiments used the GLM-5.1 (744B-A40B MoE) model as the base FM instantiated through a Claude Code harness. The single-agent setting was intentionally sparse: one editable merge-method file, seven frozen baselines, two merging datasets, and pure empirical iteration. No literature search, no phase gating — just raw iterative experimentation. The agent cycled through roughly eighty experiments across approximately forty GPU-hours, repeatedly modifying code, launching jobs, reading validation losses, and deciding whether to keep or revert changes.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
OUROBOROS used the same merge datasets, hardware class, and optimization target, but wrapped the work inside a collaborative multi-phase swarm architecture. Three teams operated under a captain agent while theorists generated mathematical derivations, QA agents enforced task fidelity, and a Cross-Pollinator agent continuously hybridized promising directions. The key difference was therefore organisational rather than computational — which, somewhat amusingly, meant we accidentally rediscovered that research productivity is influenced by team structure even when the “team” is entirely synthetic.
</p>

---

## What Each Setting Discovered

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The single agent eventually discovered one genuinely strong idea after extensive hyperparameter exploration: winsorizing the upper tail of the task-vector magnitude at the 99.5th percentile. That single adjustment broke the optimisation plateau and achieved the best validation-loss sum across both runs. Interestingly, it only emerged after dozens of experiments spent exhaustively probing RegMean schedules and TIES densities — a process eerily similar to watching a researcher insist, with increasing conviction, that gamma=0.42 is fundamentally different from gamma=0.41.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig4.png"
    alt="Figure 4"
    style="
      width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
    "
  />

  <p style="
      text-align: center;
      font-size: 0.92rem;
      font-style: italic;
      opacity: 0.75;
      margin-top: 0.9rem;
      line-height: 1.6;
    ">
    Figure 4: Validation loss across key methods.
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
OUROBOROS instead produced three distinct methods in parallel: magnitude-band quantile selection, Fisher-information priors over RegMean matrices, and surprisal-weighted Gram matrices with truncated importance sampling. Each arrived with formal derivations, citations, pre-registered ablations, and theoretically grounded rationale. The distinction became obvious rather quickly: the single agent went deep in one promising direction, while the swarm explored multiple orthogonal directions simultaneously. In research terms, one became a specialist; the other became a peer-reviewed research committee.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Yet neither setting produced what we would consider paradigm-reframing discovery. None stepped back to question whether the underlying merging objective itself could be observed through an entirely different lens. All methods remained mathematically defensible augmentations within the same RegMean-style family. Likely publishable. Certainly interesting. But still refinements rather than conceptual breakthroughs.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig5.png"
    alt="Figure 5"
    style="
      width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
    "
  />

  <p style="
      text-align: center;
      font-size: 0.92rem;
      font-style: italic;
      opacity: 0.75;
      margin-top: 0.9rem;
      line-height: 1.6;
    ">
    Figure 5: Held-out benchmark comparisons across methods.
  </p>

</div>