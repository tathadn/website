# CLAUDE.md — Portfolio Website Content Specification

## Project Overview

Personal portfolio website for Tathagata (Dave) Debnath — PhD candidate in Computer Science at NMSU. The site serves as the primary online presence for AI/ML engineering internship and job applications.

**Primary identity:** AI/ML Engineer building agentic systems and fine-tuning foundation models.
**Secondary identity:** Bioinformatics researcher with 10 publications and 80+ citations.

**Tech Stack (already established — do not change):**
- Pure HTML5 + CSS3 — no build system, no JS framework
- Tailwind CSS (CDN) for utility classes
- Google Fonts — Manrope (headlines) + Inter (body)
- Material Symbols for icons
- Deep academic color palette (`#002045` primary)
- Glassmorphism navigation
- No borders — tonal shifts for hierarchy
- Generous whitespace over content density

All new pages and content must use this existing stack and follow the established component patterns, spacing, and visual language already in the codebase.

**Design:** The site already has an established design system documented in `scholar_manuscript/DESIGN.md` ("The Scholarly Monograph" philosophy). **DO NOT override, redesign, or modify the existing design, layout, CSS, typography, color palette, or component styles.** Use the existing design system as-is for all pages. This CLAUDE.md file specifies content, structure, and copy only — all visual decisions defer to the existing design.

---

## Site Structure

```
index.html          → Homepage (hero + about + featured projects + skills + contact)
projects.html       → All projects with detailed cards
publications.html   → Research publications + software packages
blog.html           → Technical blog posts index
blog/codeq.html     → CodeQ technical writeup (first post)
contact.html        → Contact information and form
```

**Assets:**
```
assets/
├── Tathagata_CV_AIML.pdf
├── Tathagata_Resume_AIML.pdf
├── Tathagata_CV_Bioinformatics.pdf
├── Tathagata_Resume_Bioinformatics.pdf
└── images/
    ├── headshot.jpg
    ├── codeq_architecture.png (create or use placeholder)
    └── visiontriage_architecture.png (placeholder for future)
```

---

## Global Navigation

All pages share a consistent nav bar:

```
[TD logo/initials] Home | Projects | Publications | Blog | Contact
```

Right side of nav (or footer): [GitHub] [Google Scholar] [LinkedIn]

---

## Page 1: Homepage (index.html)

### Section 1: Hero

```
Headline:    Tathagata (Dave) Debnath
Subheadline: PhD Candidate · Computer Science · NMSU

Tagline:     Building agentic AI systems and fine-tuning foundation models
             on multi-GPU infrastructure.

CTA buttons: [GitHub: tathadn] [Google Scholar] [LinkedIn]
             [Download CV ↓] [Download Resume ↓]
```

- CV/Resume buttons default to AI/ML versions
- Optional: small text below "Also available: Bioinformatics [CV] [Resume]"
- No rotating text, no typing animation. Static and clean.

### Section 2: About

```
I'm a PhD candidate at New Mexico State University building AI systems
that autonomously find and fix software bugs. My current work combines
Monte Carlo Tree Search, Direct Preference Optimization, and
vision-language model fine-tuning — all running on distributed NVIDIA
H100 GPU infrastructure.

My research background is in bioinformatics and algorithm design, with
10 peer-reviewed publications (80+ citations) in venues including
IEEE TPAMI and IEEE/ACM TCBB, and two published CRAN R packages for
clustering algorithms.

I'm targeting Summer 2026 AI/ML internships and full-time roles in
agentic AI, LLM fine-tuning, and ML systems engineering.
```

Keep to 3 short paragraphs max. No bullet points. No "I am passionate about..." filler.

### Section 3: Featured Projects (3 cards)

Display the top 3 projects as cards. Each card shows:
- Project name
- One-line description
- 1-2 key result numbers (bold/highlighted)
- Tech stack tags
- [GitHub] [Blog] [Details →] links

**Card 1: CodeQ (flagship)**
```
Name:        CodeQ
Subtitle:    Autonomous Code Debugging Agent
Description: Self-improving code debugging agent that uses Monte Carlo
             Tree Search to explore fix strategies, dual-temperature
             self-critique to rank them, and Direct Preference
             Optimization to learn from its own exploration data.
             Built on Qwen2.5-Coder-7B across two H100 nodes.

Key Results: 81.3% fix rate on DebugBench (up from 10% pre-refactor)
             DPO self-improvement pushes MCTS mode to 84%

Tech Tags:   MCTS · DPO · Qwen2.5-Coder-7B · LoRA · 4-bit Quantization
             · HuggingFace TRL · Docker Sandbox · 2× H100

Links:       [GitHub] [Blog Post] [Details →]
```

**Card 2: VisionTriage (add when results are ready, placeholder until then)**
```
Name:        VisionTriage
Subtitle:    Multimodal Bug Report Triage
Description: Fine-tunes Qwen2.5-VL-7B-Instruct with QLoRA to triage
             software bug reports from screenshots + text descriptions.
             Text-only baseline benchmarked against SevPredict on the
             standard Eclipse/Mozilla dataset. Multimodal extension
             shows that adding screenshot context improves severity
             prediction accuracy.

Key Results: [TBD]% severity accuracy (text-only baseline on Eclipse/Mozilla)
             [TBD]% improvement when adding screenshot context

Tech Tags:   Qwen2.5-VL-7B · QLoRA · Eclipse/Mozilla Dataset · Rico
             · Synthetic Data · Gradio · HuggingFace

Links:       [GitHub] [HuggingFace Dataset] [Details →]
```

NOTE: If VisionTriage is not yet complete, show only 2 cards (CodeQ + Multi-Agent Codegen) or replace with placeholder text "Coming soon — Multimodal VLM fine-tuning for bug triage."

**Card 3: Parallel Multi-Agent Code Generation**
```
Name:        Parallel Multi-Agent Codegen
Subtitle:    DAG-Based Agent Orchestration for Code Synthesis
Description: Multi-agent code generation system using LangGraph with a
             DAG-based orchestrator that dispatches concurrent coder
             workers via asyncio. Extended version adds an LLM-as-Judge
             evaluator and autonomous prompt evolution loop where the
             system iteratively rewrites its own generation prompts
             based on evaluation feedback.

Key Results: Parallel DAG orchestration with async worker dispatch
             Self-evolving prompt loop via LLM-as-Judge feedback

Tech Tags:   LangGraph · Anthropic SDK · asyncio · LLM-as-Judge
             · Prompt Evolution · Docker · LangSmith

Links:       [GitHub (parallel)] [GitHub (self-evolving)] [Details →]
```

### Section 4: Technical Skills

Organized by category, AI/ML first. No progress bars, no percentage ratings. Just clean lists.

```
AI/ML & Foundation Models
  PyTorch, HuggingFace (Transformers, TRL, PEFT), LoRA/QLoRA,
  DPO, MCTS, Flash Attention 2, bitsandbytes (4-bit/8-bit),
  vLLM, Qwen2.5, DeepSeek, LangGraph, LangChain, RAG

Infrastructure & Systems
  NVIDIA H100 (multi-GPU), CUDA, NCCL, FSDP, DeepSpeed ZeRO,
  Docker, Git, Linux, screen/tmux, W&B, SSH

Languages
  Python, R, C/C++, SQL, Bash, JavaScript, LaTeX

Bioinformatics (Research)
  Samtools, STAR, DESeq2, DEXSeq, GATK, rMATS, RSEM,
  Gviz, gprofiler2, MUMmer4, BUSCO, Singularity
```

### Section 5: Quick Stats (optional, small strip)

```
10 Publications · 80+ Citations · 2 CRAN Packages · h-index 5
```

One line. No animated counters. Just facts.

### Section 6: Contact (footer or bottom section)

```
Email:    tathadbn@nmsu.edu
GitHub:   github.com/tathadn
Scholar:  [link]
LinkedIn: [link]
Location: Las Cruces, New Mexico
```

---

## Page 2: Projects (projects.html)

### Page Header
```
Headline: Projects
Subtitle: AI/ML engineering, agentic systems, and research software.
```

### Project Cards

Each project gets a full card with this structure:

```
[Project Name]
[One-line subtitle]

Overview:
  2-4 sentences describing what the project does, the architecture,
  and what makes it technically interesting.

Key Results:
  Specific numbers in a small table or highlighted metrics.

Tech Stack:
  Tags/pills for each technology.

Links:
  [GitHub Repo] [Blog Post] [Demo] [Paper]
  (only show links that exist)
```

#### Project 1: CodeQ — Autonomous Code Debugging Agent

```
Overview:
  CodeQ is a self-improving code debugging agent inspired by Agent Q
  (Putta et al., 2024). It uses Monte Carlo Tree Search to
  systematically explore fix strategies for buggy code, an AI
  self-critique mechanism with dual-temperature scoring to rank
  proposed fixes, and Direct Preference Optimization to teach the
  model to prefer successful fixes over failed ones — all without
  human intervention.

  The system runs across two NVIDIA H100 nodes: Machine A handles
  MCTS inference in 4-bit quantization (~4-6 GB VRAM), while
  Machine B runs DPO training with LoRA in bf16 (~30-35 GB VRAM).
  LoRA adapters are transferred between machines via scp, enabling
  a pipelined workflow where exploration and training overlap.

Architecture Highlights:
  - MCTS with UCB1 selection, K=4 expansion at temp=0.8, critic
    ranking at temp=0.2
  - Full-rewrite action space (refactored from line-level edits)
  - Docker sandbox execution (no network, 512MB RAM, 30s timeout)
  - Blended Q-value preference extraction (α=0.5 MCTS + AI critic)
  - Off-policy DPO with pre-computed reference log-probs
  - Fp32 logit upcast to fix bf16 NaN overflow
  - TRL pinned to 0.29.1 (1.0.0 broke precompute_ref_log_probs)

Key Results:
  | Metric                          | Value           |
  | Full rewrite baseline           | 43.9% (54/123)  |
  | MCTS rewrite (base model)       | 81.3% (100/123) |
  | MCTS rewrite (+ DPO Round 2)    | 84.0% (42/50)   |
  | Improvement from rewrite refactor | 10% → 81.3%   |
  | DPO transfer to full_rewrite    | No transfer     |

  Notable: 81% data duplication discovered and fixed in DebugBench
  dataset during preprocessing.

Tech Stack:
  Qwen2.5-Coder-7B-Instruct · MCTS · DPO · LoRA (r=32) · bf16 ·
  4-bit (bitsandbytes) · HuggingFace TRL · Flash Attention 2 ·
  Docker · 2× NVIDIA H100 94GB · W&B

Links: [GitHub] [Technical Blog Post]
```

#### Project 2: VisionTriage — Multimodal Bug Report Triage

```
Overview:
  VisionTriage fine-tunes Qwen2.5-VL-7B-Instruct with QLoRA to
  automatically triage software bug reports that include screenshots.
  The model takes a screenshot of a UI bug plus a text description and
  outputs structured triage metadata: severity level, affected
  component, bug type classification, root cause hypothesis, and
  suggested fix.

  The text-only severity prediction baseline is benchmarked against
  published methods (SevPredict, MASP, BERT-SBR) on the standard
  Eclipse/Mozilla Defect Tracking Dataset (~215K bug reports). The
  multimodal extension uses Rico screenshots with programmatic bug
  injection to demonstrate that adding visual context improves triage
  accuracy over text-only approaches.

  This project connects directly to CodeQ — CodeQ fixes bugs from
  code; VisionTriage triages bugs from visual reports before they
  reach a developer.

Key Results:
  [Add when available]
  | Metric                     | Text-Only | Multimodal | Delta |
  | Severity accuracy (binary) | TBD%      | TBD%       | +TBD% |
  | Component accuracy         | TBD%      | TBD%       | +TBD% |
  | Composite triage score     | TBD       | TBD        | +TBD  |

Tech Stack:
  Qwen2.5-VL-7B-Instruct · QLoRA · Eclipse/Mozilla Dataset · Rico ·
  Synthetic Bug Injection · HuggingFace TRL · Gradio

Links: [GitHub] [HuggingFace Dataset] [Demo]
```

NOTE: Replace TBD values with actual results when available. If project is not started, mark as "In Progress" with expected completion date.

#### Project 3: Parallel Multi-Agent Code Generation

```
Overview:
  A DAG-based multi-agent code generation system built with LangGraph
  and the native Anthropic SDK. An orchestrator agent analyzes coding
  tasks, builds a dependency graph, and dispatches parallel async
  coder workers that generate, review, and test code through
  structured handoffs.

Tech Stack:
  LangGraph · Anthropic SDK · asyncio · Python

Links: [GitHub]
```

#### Project 4: Self-Evolving Code Generation

```
Overview:
  Extension of the multi-agent pipeline that adds an LLM-as-Judge
  evaluator, failure analyzer, and autonomous prompt evolver. The
  system forms a generation loop where the tester agent rewrites its
  own system prompt based on evaluation feedback, creating a
  self-improving code generation pipeline.

Tech Stack:
  LangGraph · LLM-as-Judge · Prompt Evolution · JSON Tracker · Docker

Links: [GitHub]
```

#### Project 5: Multi-Agent Code Generation V1

```
Overview:
  Sequential multi-agent pipeline using an Orchestrator → Planner →
  Coder → Reviewer → Tester architecture. Includes LangSmith tracing
  for observability and Docker sandboxing for safe code execution.
  This was the foundation that led to the parallel and self-evolving
  versions.

Tech Stack:
  LangChain · LangSmith · Docker · Python

Links: [GitHub]
```

#### Project 6: OptCirClust — Fast Optimal Circular Clustering

```
Overview:
  Published CRAN R package implementing a fast optimal clustering
  algorithm for circular (1-dimensional periodic) data. Uses dynamic
  programming to find the globally optimal partition, avoiding local
  optima issues of iterative methods like k-means.

  Published in IEEE Transactions on Pattern Analysis and Machine
  Intelligence (TPAMI).

Tech Stack:
  R · CRAN · Dynamic Programming

Links: [CRAN] [IEEE TPAMI Paper]
```

#### Project 7: CircularSilhouette — Cluster Validation Index

```
Overview:
  Published CRAN R package implementing a silhouette-based cluster
  validation index designed specifically for circular data. Provides
  a quantitative measure of clustering quality that accounts for the
  periodic nature of circular measurements.

  Published in IEEE/ACM Transactions on Computational Biology and
  Bioinformatics (TCBB).

Tech Stack:
  R · CRAN · Statistical Methods

Links: [CRAN] [IEEE/ACM TCBB Paper]
```

#### Project 8: NutriBot — RAG Nutrition Chatbot (optional, include if README is strong)

```
Overview:
  RAG-based nutrition Q&A chatbot using hybrid FAISS + BM25 retrieval
  merged via Reciprocal Rank Fusion. Includes a 30-question evaluation
  pipeline and cost optimization strategies for API usage.

Tech Stack:
  FAISS · BM25 · Reciprocal Rank Fusion · LangChain · Python

Links: [GitHub]
```

---

## Page 3: Publications (publications.html)

### Page Header
```
Headline: Publications & Software
Subtitle: 10 peer-reviewed publications · 80+ citations · h-index 5
          [Google Scholar Profile →]
```

### Section 1: Software Packages

```
OptCirClust
  Fast optimal circular clustering algorithm.
  Published on CRAN. Associated paper in IEEE TPAMI.
  [CRAN Package] [Paper] [GitHub]

CircularSilhouette
  Silhouette-based cluster validation for circular data.
  Published on CRAN. Associated paper in IEEE/ACM TCBB.
  [CRAN Package] [Paper] [GitHub]
```

### Section 2: Publications

List in reverse chronological order. For each paper:

```
[Title]
[Authors — bold "T. Debnath" or "Tathagata Debnath"]
[Venue, Year]
[Links: Paper | PDF | Code (if applicable)]
```

Include all 10 publications. Pull the exact list from Google Scholar.
Known publications include:

1. Radiation exposure induces genome-wide alternative splicing events
   in Aedes aegypti mosquitoes (2025)
2. Phosphoproteomics Analyses of Aedes aegypti fat body... (2024)
3. CircularSilhouette paper — IEEE/ACM TCBB (2023)
4. OptCirClust paper — IEEE TPAMI (2021)
5. EF-index paper — Journal of Visual Communication and Image
   Representation (2019)
6. RASIT paper (2018)
7-10. [Pull remaining from Scholar profile]

Ensure author order matches the published versions exactly.
TPAMI authorship: verify correct order (this was previously corrected).

---

## Page 4: Blog (blog.html)

### Page Header
```
Headline: Blog
Subtitle: Technical writeups on AI/ML engineering and research.
```

### Blog Post Index

List posts in reverse chronological order. Each entry shows:
```
[Post Title]
[Date] · [Reading time estimate]
[2-sentence summary]
[Read →]
```

### Blog Post 1: CodeQ Technical Writeup (blog/codeq.html)

**Title:** "CodeQ: Teaching an LLM to Debug Code with MCTS and DPO"
**Target length:** 1500-2500 words
**Date:** [Publication date]

**Outline:**

```
1. Introduction (200 words)
   - The problem: automated code debugging is hard
   - The idea: combine MCTS exploration with DPO self-improvement
   - Inspired by Agent Q (Putta et al., 2024)
   - One-line result: 81.3% fix rate on DebugBench

2. Architecture Overview (300 words)
   - Two-machine setup: Machine A (inference, 4-bit) + Machine B
     (training, bf16)
   - MCTS engine: UCB1 selection, K=4 expansion, dual-temperature
     critique
   - DPO training loop: preference pair extraction from MCTS
     trajectories, LoRA fine-tuning
   - Diagram: the self-improvement feedback loop
     (MCTS Explore → Extract Prefs → DPO Train → Evaluate → Merge)

3. The Critical Refactor: Line Edits → Full Rewrites (400 words)
   - Original design: PLAN/THOUGHT/CODE_ACTION structured format
     with line-level edits (EDIT, INSERT, DELETE, RUN_TESTS)
   - Problem: parse failures, 0.38% apparent success rate
   - Discovery: switching to full_rewrite mode revealed true 36%
     baseline (not 0.38%)
   - MCTS with full rewrites: 10% → 81.3%, 14x faster
   - Lesson: action space design matters more than model quality

4. Data Quality: The 81% Duplication Discovery (200 words)
   - DebugBench had 81% duplicate entries
   - Impact on evaluation: inflated apparent performance
   - Fix: deduplication reduced dataset from ~650 to ~123 unique
     problems
   - Lesson: always audit your benchmark

5. DPO Training: What Worked and What Broke (400 words)
   - Round 1 DPO: baseline training
   - NaN collapse in Round 2: bf16 overflow in logit computation
   - Fix: Fp32LogitsDPOTrainer subclass that upcasts logits
   - TRL version pinning: 1.0.0 broke precompute_ref_log_probs,
     pinned to 0.29.1
   - LoRA config: rank=32, alpha=64, all attn+MLP, lr=5e-6, 2
     epochs, beta=0.1

6. Results (300 words)
   - Results table (base vs. MCTS vs. DPO Round 2)
   - DPO improves MCTS mode: 81.3% → 84%
   - DPO does NOT transfer to full_rewrite: 43.9% → 43.9%
   - Explanation: training data is MCTS trajectories only, so the
     model only improves on MCTS-style exploration
   - Ablation results (category breakdown, difficulty breakdown,
     rollouts ablation) — add when available

7. What I'd Do Differently (200 words)
   - Train DPO on full_rewrite trajectories to test transfer
   - Try Round 3 to measure diminishing returns
   - Cross-benchmark generalization (SWE-bench Lite)
   - The honest finding about no transfer is as interesting as the
     positive results

8. Links
   - GitHub: github.com/tathadn/codeq
   - Inspired by: Agent Q (Putta et al., 2024)
```

Include in the post:
- Architecture diagram (can be simple — text-based or SVG)
- Results table
- Code snippets for key decisions (the fp32 logit fix, the rewrite
  prompt, the preference extraction logic)

### Blog Post 2: VisionTriage (blog/visiontriage.html) — FUTURE

Add when VisionTriage results are available. Outline:

```
Title: "Adding Eyes to Bug Report Triage: Multimodal VLM Fine-Tuning"

1. No standard multimodal benchmark exists for bug triage
2. Building the hybrid approach: Eclipse/Mozilla text baseline +
   Rico screenshot extension
3. Text-only results vs. SevPredict/MASP
4. Does adding screenshots help? Ablation results
5. Dataset release on HuggingFace
```

---

## Page 5: Contact (contact.html)

### Page Header
```
Headline: Get in Touch
Subtitle: Open to AI/ML internships (Summer 2026) and research
          collaborations.
```

### Contact Information

```
Email:     tathadbn@nmsu.edu / tirtha.debnath@gmail.com
GitHub:    github.com/tathadn
Scholar:   scholar.google.com/citations?user=AAErR7QAAAAJ
LinkedIn:  linkedin.com/in/tathagata-debnath-1a68727a
Location:  Las Cruces, New Mexico, USA
```

### Contact Form (optional)

Simple form: Name, Email, Message, Send button.
Can use Formspree (formspree.io) for backend — no server needed.

---

## SEO & Meta Tags (all pages)

```html
<title>Tathagata Debnath — AI/ML Engineer & PhD Candidate</title>
<meta name="description" content="Building agentic AI systems and
  fine-tuning foundation models. PhD candidate at NMSU. MCTS, DPO,
  VLM fine-tuning, distributed training on multi-GPU infrastructure.
  10 publications, 80+ citations.">
<meta name="keywords" content="AI/ML Engineer, Agentic AI, LLM
  Fine-Tuning, MCTS, DPO, LoRA, QLoRA, NVIDIA H100, PhD Candidate,
  NMSU, Tathagata Debnath">

<!-- Open Graph (for LinkedIn/Twitter sharing) -->
<meta property="og:title" content="Tathagata Debnath — AI/ML Engineer">
<meta property="og:description" content="Building agentic AI systems
  and fine-tuning foundation models on multi-GPU infrastructure.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://tathagatadebnath.com">

<!-- Canonical URL -->
<link rel="canonical" href="https://tathagatadebnath.com">
```

Adjust `<title>` per page:
- Projects: "Projects — Tathagata Debnath"
- Publications: "Publications — Tathagata Debnath"
- Blog: "Blog — Tathagata Debnath"
- Blog post: "[Post Title] — Tathagata Debnath"
- Contact: "Contact — Tathagata Debnath"

---

## Content Rules

1. **No filler language.** No "I am passionate about...", no "In this
   section I will discuss...", no "Feel free to reach out."
2. **Lead with results.** Every project card should have at least one
   quantitative result visible without clicking into details.
3. **Link to code.** Every featured project must have a GitHub link.
   If there's no public repo, don't feature it.
4. **Be honest.** Include negative results (DPO no-transfer) alongside
   positive ones. This signals intellectual maturity.
5. **Keep it current.** Update citation count, project results, and
   blog posts as work progresses. Stale content is worse than no content.
6. **AI/ML first.** On every page, AI/ML content appears before
   bioinformatics content. The ordering signals priority.
7. **No outdated stats.** Remove or update any counters (publications,
   lines of code, etc.) that don't reflect current reality.
8. **Mobile-first.** Test every page on mobile. Recruiters check
   profiles on phones.
