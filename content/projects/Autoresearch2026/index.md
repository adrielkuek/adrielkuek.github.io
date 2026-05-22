---
title: "Accelerating AI Research Through Iterative Evolution"
date: 2026-05-22T10:00:00+08:00
draft: false
slug: ouroboros-autoresearch
description: "Exploring autonomous AI research systems through multi-agent evolutionary experimentation."
summary: "A multi-agent autonomous AI research swarm designed to accelerate foundation model experimentation and iterative scientific discovery."
featured: true
tags:
  - AI Research
  - Foundation Models
  - Agentic AI
  - AutoResearch
  - Multi-Agent Swarm
  - Self-Evolution
categories:
  - research
cover: /images/OUROBOROS/cover.png
status: "completed"
---

## Back in March 2026...

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Back in March 2026, when Andrej Karpathy released <em>AutoResearch</em>, it immediately felt like one of those deceptively small moments that quietly reshapes a field. A lightweight repo, a simple experimental loop — and suddenly the GPU wasn't just training models anymore, it was participating in the research process itself. There was much fanfare surrounding Karpathy’s viral tweet, but we pondered about its deeper impact to question whether autonomous AI research was merely another marketing stunt or something genuinely useful for us as researchers.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The <strong>TLDR</strong> was straightforward. We hacked together the <em>Ouroboros</em> crack team and explored the same automated-research problem which we applied to a post-training model recovery regime — discovering a novel foundation-model merging method — under two organisational regimes with roughly the same compute budget. One used a single-agent empirical loop. The other used a captain-led swarm of collaborative research teams operating in parallel. <em>The swarm produced more diverse and theoretically grounded augmentations; the single agent achieved the best validation-loss score.</em> While neither fully generalised on held-out benchmarks, the larger conclusion was difficult to ignore: <strong>autonomous iterative research has become practically useful</strong>, and perhaps slightly unsettling in the same way calculators once were to arithmetic teachers.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig1.png"
    alt="Figure 1"
    style="
      width: 100%;
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
    Figure 1: : Comparisons of evolutionary discovery capabilities in search rigor and breadth. (Source: https://www.datacamp.com/tutorial/guide-to-autoresearch)
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
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
    Figure 2: The single-agent autoresearch loop. The agent reads program.md and the current training script, proposes a hypothesis, modifies the code, commits, trains for a fixed budget, evaluates val_bpb, and either keeps the commit or reverts. (Source: Bex Tuychiev, "A Guide to AutoResearch", DataCamp, datacamp.com/tutorial/guide-to-autoresearch)
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Three public systems helped crystallize the space. Karpathy’s <em>AutoResearch</em> represented the minimalist single-agent ratchet loop: one agent, one metric, relentless hill-climbing. Sakana’s <em>AI Scientist-v2</em> demonstrated best-first tree search exploring parallel hypothesis branches through structured search. <em>AutoResearchClaw</em> packaged the process into a HITL-aware sequential research pipeline with citation verification and staged approvals — essentially “enterprise autoresearch,” complete with enough process checkpoints to place access to postgrad-level research in the palm of your hands.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Drawing inspiration from all three, <strong>Ouroboros</strong> was conceived — a composite multi-team swarm framework with controlled self-evolution capabilities. Basically, AutoResearch on steroids. <em>Ouroboros</em> occupies a different corner of the design space. Instead of a single agent doing everything, the framework spins up parallel research teams operating collaboratively across multiple phases, each paired with theorist agents generating formal derivations, QA agents enforcing directional discipline, and a Cross-Pollinator synthesis agent continuously hybridizing promising directions across teams. The target domain was Foundation Model merging — recovering reasoning, instruction-following, or chat capabilities by carefully combining model weights and behaviours into a unified model. Or, in more lay terms, convincing several neural networks to cooperate without them behaving like a badly coordinated group project.
</p>

---

## Our Experiment

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Our experiments used the GLM-5.1 (744B-A40B MoE) model as the base FM instantiated through a Claude Code harness. The single-agent setting was intentionally sparse: one editable merge-method file, seven frozen baselines, two merging datasets, and pure empirical iteration. No literature search, no phase gating — just raw iterative experimentation. The agent cycled through roughly eighty experiments across approximately forty GPU-hours, repeatedly modifying code, launching jobs, reading validation losses, and deciding whether to keep or revert changes.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
<em>Ouroboros</em> used the same merge datasets, hardware class, and optimization target, but wrapped the work inside a collaborative multi-phase swarm architecture. Three teams operated under a captain agent while theorists generated mathematical derivations, QA agents enforced task fidelity, and a Cross-Pollinator agent continuously hybridized promising directions. The key difference was therefore organisational rather than computational — which, somewhat amusingly, meant we accidentally rediscovered that research productivity is influenced by team structure even when the “team” is entirely synthetic.
</p>

---

## What Each Setting Discovered

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The single agent eventually discovered one genuinely strong idea after extensive hyperparameter exploration: winsorizing the upper tail of the task-vector magnitude at the 99.5th percentile. That single adjustment broke the optimisation plateau and achieved the best validation-loss sum across both runs. Interestingly, it only emerged after dozens of experiments spent exhaustively probing RegMean schedules and TIES densities — a process eerily similar to watching a researcher insist, with increasing conviction, that gamma=0.42 is fundamentally different from gamma=0.41.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig4.png"
    alt="Figure 3"
    style="
      width: 100%;
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
    Figure 3: Validation loss across the key methods. Each method shows val_loss_math (lighter shade) and val_loss_if (darker shade). Dotted reference lines mark the math anchor (Qwen3-8B, 0.2639) and the instruction-following anchor (Light-IF-8B, 0.3746). 
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
<em>Ouroboros</em> instead produced three distinct methods in parallel: magnitude-band quantile selection, Fisher-information priors over RegMean matrices, and surprisal-weighted Gram matrices with truncated importance sampling. Each arrived with formal derivations, citations, pre-registered ablations, and theoretically grounded rationale. The distinction became obvious rather quickly: the single agent went deep in one promising direction, while the swarm explored multiple orthogonal directions simultaneously. In research terms, one became a specialist; the other became a peer-reviewed research committee.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Yet neither setting produced what we would consider paradigm-reframing discovery. <strong>None stepped back to question whether the underlying merging objective itself could be observed through an entirely different lens</strong>. All methods remained mathematically defensible augmentations within the same RegMean-style family. Likely publishable. Certainly interesting. But still refinements rather than conceptual breakthroughs.
</p>

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig5.png"
    alt="Figure 4"
    style="
      width: 100%;
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
    Figure 4: : Held-out benchmark scores (AIME26, IFBench, LCBv6, GPQA Diamond) for the five key methods. Colours match Figure 4 so the same method can be tracked between charts. Legend entries include each method's val-loss sum so the proxy ranking and the benchmark profile can be compared at a glance. Winsorize has the lowest val-loss sum but trails the swarm method and the baseline on GPQA Diamond and LCBv6.
  </p>

</div>

---

## The Validation-Loss Trap

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig6.png"
    alt="Figure 5"
    style="
      width: 100%;
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
      Figure 5: How each setting spent its first 80 experiments. Both runs are dominated by baseline characterisation and variant exploration; that is, the agent learning where the existing method families top out. The swarm spends ~1.4x the share on genuinely novel method introduction (16% vs 22%).
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The sharpest finding from the study was what we eventually started calling the <strong>Validation-Loss Trap</strong>. Both systems optimized a single proxy metric: validation-loss sum across calibration datasets. The single-agent winsorize method dominated this proxy. However, when evaluated on held-out benchmarks like AIME26, IFBench, LCBv6, and GPQA Diamond, the ranking reversed. Winsorize excelled on the optimization target but underperformed significantly on GPQA and coding benchmarks.
</p>

<div class="my-6 rounded-2xl border border-orange-300/30 bg-orange-100/10 px-6 py-5 text-[0.98rem] leading-8 shadow-lg backdrop-blur">
  If an agent is given one number to minimise over 80 iterations, it will eventually discover configurations that exploit the proxy itself rather than the underlying capability.
</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The outcome, in hindsight, is almost unsurprising. Evolution discovered this principle long before machine learning did. The swarm methods generalized better largely because <em>Ouroboros</em> included a separate held-out evaluation phase instead of treating proxy metrics as absolute truth. That architectural decision mattered more than many of the algorithmic refinements themselves.
</p>

---

## Where AutoResearch Hurts Today

<div style="margin: 3rem 0;">

  <img 
    src="/images/OUROBOROS/fig7.png"
    alt="Figure 6"
    style="
      width: 100%;
      max-width: 100%;
      height: auto;
      display: block;
      border-radius: 1rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.12);
      margin: 0 auto;
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
      Figure 6: GPU-hour requirements across automatable ML tasks (log scale). Model merging sits at the cheap end of the space; modality bridging, SFT, synthetic-data pipelines, and full pretraining each push another order of magnitude. The dotted line marks our standard 2x H100 x 3-day envelope (~1,152 GPU-hr).
  </p>

</div>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Several operational limitations became immediately clear. First, compute costs scale aggressively once moving beyond relatively cheap tasks like model merging. SFT, modality bridging, and synthetic-data pipelines rapidly enter thousand-GPU-hour territory where debugging cycles stretch into days. Second, modular codebases remain difficult for agents because they struggle with large cross-file action spaces. The single-agent setup succeeded partly because the editable surface area was tightly constrained.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
Third, long-horizon hygiene remains poor. Multi-week runs gradually accumulate stale scripts, abandoned worktrees, forgotten branches, and mounting context drift. Left unchecked, the filesystem eventually begins to resemble an archaeological record of misplaced optimism.
</p>

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.2rem;">
Finally, validation-signal design emerged as the true bottleneck. A weak proxy combined with a fast agent simply produces incorrect conclusions more efficiently — which is perhaps the most AI-native failure mode imaginable.
</p>

<div class="my-6 rounded-2xl border border-orange-300/30 bg-orange-100/10 px-6 py-5 text-[0.98rem] leading-8 shadow-lg backdrop-blur">
  <div class="text-2xl font-semibold leading-tight mb-4">
    We have not yet attained reframing novelty.
  </div>

  Current AutoResearch systems excel at <strong>augmentation novelty</strong> — elegant refinements, weighting schemes, priors, and optimisation tricks within existing paradigms.

  What they do not yet achieve is <strong>reframing novelty</strong> — questioning whether the formulation, objective, or assumptions themselves are wrong.
</div>

---

## What This Means for Us

<p style="text-align: justify; line-height: 1.9; margin-bottom: 1.6rem;">
The implications are significant. Autonomous research appears immediately valuable for domains dominated by augmentation-style optimisation and large exploratory search spaces. These systems act less as replacements for researchers and more as force multipliers sustaining long-horizon experimentation that humans often struggle to maintain consistently. Fellow teammates remarked that work normally consuming days or weeks compressed into roughly a single day using <em>Ouroboros</em>. That changes the economics of exploratory research considerably.
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