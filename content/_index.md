---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-05-16
type: landing

sections:
  - block: resume-biography-3
    content:
      # Profile to display — references data/authors/me.yaml
      username: me
      text: ''
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: lg
      avatar:
        size: large
        shape: rounded

  - block: markdown
    id: about
    content:
      title: About
      subtitle: ''
      text: |-
        I work at the intersection of AI research and technical leadership — which is a fancy way of saying I spend an unhealthy amount of time on optimisation problems, research strategy, and figuring out the next operationally impactful AI capability.

        Over the past 15+ years, I've wandered through signal processing, embedded systems, large-scale video analytics, computer vision, multimodal AI, foundation models, and autonomous research systems — eventually landing in the wonderfully chaotic world of AI and machine learning.

        I'm particularly interested in moving AI systems beyond *"next-token statistical predictors"* toward systems that are **adaptive, collaborative, grounded, and operationally useful in complex environments**.
    design:
      columns: '1'
      spacing:
        padding: ['3rem', 0, '2rem', 0]

  - block: markdown
    id: research
    content:
      title: Current Research Threads
      subtitle: ''
      text: |-
        **Foundation Models** — Building sovereign multimodal and language foundation models for defence-centric applications.

        **Agentic AI** — Exploring collaborative autonomous research systems and long-horizon AI workflows.

        **Autonomous Research** — Systems capable of planning, experimentation, evaluation, and iterative self-improvement.

        **World Models** — Representations of dynamics, causality, memory, and reasoning in complex environments.

        **Multimodal Understanding** — Bridging language, vision, video, structured knowledge, and reasoning systems.
    design:
      columns: '1'
      spacing:
        padding: ['2rem', 0, '2rem', 0]

  - block: markdown
    id: publications
    content:
      title: Selected Publications
      subtitle: ''
      text: |-
        **Soft Unification with Knowledge Graph Embeddings** — *ICML 2025.* Improving symbolic-neural reasoning through knowledge graph embedding methods.

        **Dynamic Scene Graph Generation** — *2025.* What off-the-shelf multimodal models can achieve for scene graph understanding.

        **Pro-Cap** — *ACM MM 2023.* Leveraging frozen vision-language models for hateful meme detection.

        **TotalDefMeme** — *2023.* A multimodal meme dataset for Total Defence and Singapore-context misinformation analysis.

        ---

        Full publication list on [Google Scholar →](https://scholar.google.com/citations?user=JBB2mf8AAAAJ&hl=en)
    design:
      columns: '1'
      spacing:
        padding: ['2rem', 0, '2rem', 0]

  - block: markdown
    id: mentorship
    content:
      title: Mentorship & Research Guidance
      subtitle: ''
      text: |-
        I've had the privilege of mentoring students on AI research projects that secured recognition at **SSEF** and **ISEF** — a constant reminder that curiosity scales faster than compute budgets.

        Beyond student mentorship, I work closely with pre-university interns, undergraduate researchers, graduate students, and PhD attachments. Most brainstorming sessions eventually drift into research ideation, hypothetical AI systems, and questionable *"what if we just try this?"* moments.
    design:
      columns: '1'
      spacing:
        padding: ['2rem', 0, '3rem', 0]
---
