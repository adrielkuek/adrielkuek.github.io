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
cover: \images\ouroboros\cover.png
status: "completed"
---

## Back in March 2026...

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Back in March 2026, when Andrej Karpathy released <em>AutoResearch</em>, it immediately felt like one of those deceptively small moments that quietly reshapes a field. A lightweight repo, a simple experimental loop — and suddenly the GPU wasn't just training models anymore, it was participating in the research process itself. There was much fanfare surrounding Karpathy’s viral tweet, but here in IE, we immediately cut through the fog and moved quickly to evaluate whether autonomous AI research was merely another marketing stunt or something genuinely useful for our research work in DSO.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The TLDR was straightforward. We ran the same automated-research problem — discovering a novel foundation-model merging method for post-training capability recovery — under two organisational regimes with roughly the same compute budget. One used a single-agent empirical loop. The other used a captain-led swarm of collaborative research teams operating in parallel. <em>The swarm produced more diverse and theoretically grounded augmentations; the single agent achieved the best validation-loss score.</em> While neither fully generalised on held-out benchmarks, the larger conclusion was difficult to ignore: <strong>autonomous iterative research has become practically useful</strong>, and perhaps slightly unsettling in the same way calculators once were to arithmetic teachers.
</p>

<div class="my-10">
  <img 
    src="/images/ouroboros/fig1.png"
    alt="Figure 1"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 1: Comparisons of evolutionary discovery capabilities in search rigor and breadth.
  </p>
</div>

---

## What is AutoResearch?

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
AutoResearch itself is conceptually simple. An AI coding agent autonomously runs machine-learning experiments toward a target objective. It reads results, proposes modifications, edits code, launches jobs, evaluates outputs, and either commits or reverts changes. Then the loop repeats until an experimental cut-off limit is reached or when the compute budget quietly evaporates into the void. The underlying idea is not entirely new — the lineage stretches from early Neural Architecture Search (NAS) and AlphaEvolve-style evolutionary search to more recent systems like Sakana AI's <em>AI Scientist</em>. What changed in 2026 was that the workflow became operationally coherent enough for researchers to seriously integrate into day-to-day experimentation, rather than it remaining solely as a neat conference demonstrator.
</p>

<div class="my-10">
  <img 
    src="/images/ouroboros/fig2.png"
    alt="Figure 2"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
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

<div class="my-10">
  <img 
    src="/images/ouroboros/fig3.png"
    alt="Figure 3"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 3: Reference workflows for automated research systems.
  </p>
</div>

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

<div class="my-10">
  <img 
    src="/images/ouroboros/fig4.png"
    alt="Figure 4"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 4: Validation loss across key methods.
  </p>
</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
OUROBOROS instead produced three distinct methods in parallel: magnitude-band quantile selection, Fisher-information priors over RegMean matrices, and surprisal-weighted Gram matrices with truncated importance sampling. Each arrived with formal derivations, citations, pre-registered ablations, and theoretically grounded rationale. The distinction became obvious rather quickly: the single agent went deep in one promising direction, while the swarm explored multiple orthogonal directions simultaneously. In research terms, one became a specialist; the other became a peer-reviewed research committee.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Yet neither setting produced what we would consider paradigm-reframing discovery. None stepped back to question whether the underlying merging objective itself could be observed through an entirely different lens. All methods remained mathematically defensible augmentations within the same RegMean-style family. Likely publishable. Certainly interesting. But still refinements rather than conceptual breakthroughs.
</p>

<div class="my-10">
  <img 
    src="/images/ouroboros/fig5.png"
    alt="Figure 5"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 5: Held-out benchmark comparisons across methods.
  </p>
</div>

---

## The Validation-Loss Trap

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The sharpest finding from the study was what we eventually started calling the <strong>Validation-Loss Trap</strong>. Both systems optimized a single proxy metric: validation-loss sum across calibration datasets. The single-agent winsorize method dominated this proxy. However, when evaluated on held-out benchmarks like AIME26, IFBench, LCBv6, and GPQA Diamond, the ranking reversed. Winsorize excelled on the optimization target but underperformed significantly on GPQA and coding benchmarks.
</p>

<div class="my-6 rounded-2xl border border-orange-300/30 bg-orange-100/10 px-6 py-5 text-[0.98rem] leading-8 shadow-lg backdrop-blur">
  If an agent is given one number to minimise over 80 iterations, it will eventually discover configurations that exploit the proxy itself rather than the underlying capability.
</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The outcome, in hindsight, is almost unsurprising. Evolution discovered this principle long before machine learning did. The swarm methods generalized better largely because OUROBOROS included a separate held-out evaluation phase instead of treating proxy metrics as absolute truth. That architectural decision mattered more than many of the algorithmic refinements themselves.
</p>

<div class="my-10">
  <img 
    src="/images/ouroboros/fig6.png"
    alt="Figure 6"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 6: Distribution of exploratory effort across both systems.
  </p>
</div>

<div class="my-10">
  <img 
    src="/images/ouroboros/fig7.png"
    alt="Figure 7"
    class="rounded-2xl shadow-xl mx-auto"
  />

  <p class="text-center text-sm italic opacity-80 mt-3">
    Figure 7: GPU-hour requirements across automatable ML tasks.
  </p>
</div>

---

## Where AutoResearch Hurts Today

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Several operational limitations became immediately clear. First, compute costs scale aggressively once moving beyond relatively cheap tasks like model merging. SFT, modality bridging, and synthetic-data pipelines rapidly enter thousand-GPU-hour territory where debugging cycles stretch into days. Second, modular codebases remain difficult for agents because they struggle with large cross-file action spaces. The single-agent setup succeeded partly because the editable surface area was tightly constrained.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Third, long-horizon hygiene remains poor. Multi-week runs gradually accumulate stale scripts, abandoned worktrees, forgotten branches, and mounting context drift. Left unchecked, the filesystem eventually begins to resemble an archaeological record of misplaced optimism.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Finally, validation-signal design emerged as the true bottleneck. A weak proxy combined with a fast agent simply produces incorrect conclusions more efficiently — which is perhaps the most AI-native failure mode imaginable.
</p>

<div class="my-6 rounded-2xl border border-orange-300/30 bg-orange-100/10 px-6 py-5 text-[0.98rem] leading-8 shadow-lg backdrop-blur">
  <strong>The broader novelty gap therefore remains unresolved.</strong><br><br>

  Current AutoResearch systems excel at <strong>augmentation novelty</strong> — elegant refinements, weighting schemes, priors, and optimisation tricks within existing paradigms.

  What they do not yet achieve is <strong>reframing novelty</strong> — questioning whether the formulation, objective, or assumptions themselves are wrong.
</div>

---

## What This Means for DSO

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The implications are significant. Autonomous research appears immediately valuable for domains dominated by augmentation-style optimisation and large exploratory search spaces. These systems act less as replacements for researchers and more as force multipliers sustaining long-horizon experimentation that humans often struggle to maintain consistently. One SME involved in the study remarked that work normally consuming days or weeks compressed into roughly a single day using OUROBOROS. That changes the economics of exploratory research considerably.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
So while we have not fully automated scientific discovery, we may have entered a more interesting regime: one where capable researchers and engineers alike can explore research spaces at a tempo and scale previously impractical for small teams. And for a field where progress is often bottlenecked not by ideas, but by time, iteration, and sheer experimental patience, that already feels like a fairly consequential shift.
</p>

---

## References

<div style="line-height: 1.9;">

<ol>

<li style="margin-bottom: 1rem;">
  <strong>AlphaEvolve: A Gemini-powered coding agent for designing advanced algorithms</strong><br>
  <a href="https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms" target="_blank">
    https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms
  </a>
</li>

<li style="margin-bottom: 1rem;">
  <strong>Andrej Karpathy — AutoResearch</strong><br>
  <a href="https://github.com/karpathy/autoresearch" target="_blank">
    https://github.com/karpathy/autoresearch
  </a>
</li>

<li style="margin-bottom: 1rem;">
  <strong>The AI Scientist-v2: Workshop-Level Automated Scientific Discovery via Agentic Tree Search</strong><br>
  <a href="https://arxiv.org/abs/2504.08066" target="_blank">
    https://arxiv.org/abs/2504.08066
  </a>
</li>

<li style="margin-bottom: 1rem;">
  <strong>AutoResearchClaw</strong><br>
  <a href="https://github.com/aiming-lab/AutoResearchClaw" target="_blank">
    https://github.com/aiming-lab/AutoResearchClaw
  </a>
</li>

</ol>

</div>