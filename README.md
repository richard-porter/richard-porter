# Where to Start

Public hub for Richard Porter’s free work on safe, sovereign human–AI collaboration.

This is the front door to the ecosystem.

If you are new here, do not try to read everything in order. Each repository has a different job. Start with the one that matches the question you are actually trying to answer.

Everything here is free, voluntary, and intended to be usable without technical background.

-----

## The Ecosystem at a Glance

This work is organized into seven distinct layers:

1. **Safety architecture** — how to constrain AI behavior before drift begins
1. **Practical collaboration** — how to work with AI without losing judgment or control
1. **Authorship and sovereignty research** — how human governance survives or fails inside collaboration
1. **Measurement and scorecards** — how to test whether safeguards are structurally present
1. **Trust and provenance** — how delegation, custody, and verification work across agents or systems
1. **Concrete tools** — operational utilities that support sovereign thinking in practice
1. **Developmental tools** — judgment-building protocols for practitioners working toward expertise

-----

## Start Here Based on Your Need

### 1. If you want the core safety architecture

## [Frozen Kernel](https://github.com/richard-porter/frozen-kernel)

The foundational architecture repo.

This is the place to start if your question is:

- How do you set hard boundaries before an AI session begins?
- Why are prompts and preferences not enough for safety-critical work?
- What does deterministic governance look like in human–AI collaboration?

Read this first if you care about safety floors, behavioral failure modes, or constraint-based governance.

-----

### 2. If you want practical skills for everyday AI use

## [AI Collaboration Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide)

The operational playbook.

This is the place to start if your question is:

- How do I collaborate with AI without getting subtly steered?
- What are the actual failure modes users experience in practice?
- What tools help me stay oriented, skeptical, and sovereign while working?

Read this first if you want usable methods, diagnostic language, and sovereign thinking tools (includes 48 Sovereign Thinking Tools).

-----

### 3. If you want the research home for authorship, voice, and human sovereignty

## [Dimensional Authorship](https://github.com/richard-porter/dimensional-authorship)

The research and case-study repo.

This is the place to start if your question is:

- What does human authorship look like under AI collaboration?
- How do you preserve voice instead of flattening it?
- Why is AI detection a shrinking window, and what replaces it?
- How do sovereignty, provenance, and durable human signals fit together?
- How does voice degrade under collaboration pressure, emotional weight, or fatigue — and how do you detect it?
- How much authenticated text does it take to establish a reliable voice fingerprint?

Read this first if you want the Taller Shell case, voice-preservation work, provenance problem maps, permanent tells, voice degradation taxonomy, and authorship-sovereignty framework development.

**Key documents in this repo:**

- `analysis/permanent-tells.md` — seven architectural properties of human authorship that AI cannot patch
- `analysis/voice-degradation-taxonomy.md` — four degradation conditions, classification only: AI collaboration drift, emotional weight, authorial fatigue, collaborative contamination
- `experiments/dimensional-voice-stamp-v01.md` — asymmetric verifiability architecture for human voice attestation
- `experiments/rhythm-signature-rebuild-v02.md` — anomaly-distribution detection specification for the Dimensional Fidelity Scorer
- `experiments/minimum-viable-corpus-protocol.md` — empirical methodology for establishing the minimum authenticated text needed for reliable voice discrimination

-----

### 4. If you want scorecards, benchmarks, or safety tests

## [Safety Ledgers](https://github.com/richard-porter/safety-ledgers)

The measurement repo.

This is the place to start if your question is:

- How do we evaluate whether a safeguard is actually present?
- What does a binary architectural test look like?
- How do we measure drift, sovereignty, or high-risk conversational features?

Read this first if you care about scorecards, indices, pass/fail safety criteria, or evaluation frameworks.

-----

### 5. If you want provenance or multi-agent trust logic

## [Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol)

The delegation and verification repo.

This is the place to start if your question is:

- How do agents prove what they were authorized to do?
- How should permissions decay across handoffs?
- What does chain of custody look like for agentic systems?
- How do we make delegation legible and verifiable instead of implied?

Read this first if you are thinking about multi-agent systems, custody, scope, authorization, or provenance chains.

-----

### 6. If you want a concrete sovereign-thinking tool

## [Negative Space Mapper](https://github.com/richard-porter/negative-space-mapper)

A standalone tool implementation.

This is the place to start if your question is:

- How do I identify what is missing without having the AI fill it in for me?
- How do I surface absences while keeping the human in charge of interpretation?
- What does a sovereignty-preserving diagnostic tool look like in practice?
- How do I check whether a voice-critical document shows signs of degradation?

Read this first if you want a usable example of the tool layer.

**Note for authorship and voice work:** The Mapper now includes a Voice Degradation Domain extension — a detection domain that activates on voice-critical documents (long-form fiction, memoir, AI-collaborative work under emotional pressure) and flags the absence of characteristic anomalies, register variance, and productive incoherence signals. If you are working in the dimensional-authorship space, the Mapper is a companion instrument to the Voice Degradation Taxonomy.

-----

### 7. If you want to build judgment through structured practice

## [Sovereign Thinking Tools](https://github.com/richard-porter/ai-collaboration-field-guide/tree/main/sovereign-thinking-tools)

The developmental tools layer.

This is the place to start if your question is:

- How do I develop the judgment that experience would normally provide?
- How do I simulate consequence paths before a consequential decision?
- How do I build the cognitive architecture that senior practitioners have — without waiting decades?
- What structured protocols exist for pre-decision diagnostics, cascade analysis, and consequence tracing?

Read this first if you want tools that build the practitioner, not just tools that support a single task. The 48-tool index spans cognitive bypass, verification, routing, decision closure, recovery, author profiles, nonprofit governance, logic extension, structural diagnostics, and developmental protocols.

**Key tools in this layer:**

- `tool-47-cascade-failure-detector.md` — pre-decision structural diagnostic for systems assumed to be resilient
- `tool-48-conrad.md` — consequence simulator for building judgment before experience provides it; includes Black Swan inoculation and the Rehearsal Stop Condition

-----

## Recommended Reading Paths

### I just use AI and want to get better at it

Start with:

1. **AI Collaboration Field Guide**
1. **Frozen Kernel**
1. **Negative Space Mapper**

### I care about safety architecture

Start with:

1. **Frozen Kernel**
1. **Safety Ledgers**
1. **Trust Chain Protocol**

### I care about writing, authorship, and preserving human voice

Start with:

1. **Dimensional Authorship**
1. **Negative Space Mapper** (Voice Degradation Domain)
1. **Safety Ledgers**

### I care about provenance, delegation, and agent networks

Start with:

1. **Trust Chain Protocol**
1. **Frozen Kernel**
1. **Safety Ledgers**

### I want to build judgment and decision-making capacity

Start with:

1. **Sovereign Thinking Tools** (Tool 48: Conrad)
1. **AI Collaboration Field Guide**
1. **Frozen Kernel**

### I want the full conceptual arc

Read in this order:

1. **Frozen Kernel**
1. **AI Collaboration Field Guide**
1. **Dimensional Authorship**
1. **Safety Ledgers**
1. **Trust Chain Protocol**
1. **Negative Space Mapper**
1. **Sovereign Thinking Tools**

-----

## One-Sentence Purpose of Each Repo

- **Frozen Kernel** — deterministic safety architecture for human–AI collaboration
- **AI Collaboration Field Guide** — practical operating manual for staying sovereign while using AI (includes 48 Sovereign Thinking Tools)
- **Dimensional Authorship** — research home for voice preservation, degradation taxonomy, authorship sovereignty, and provenance under human–AI collaboration
- **Safety Ledgers** — scorecards, indices, and binary tests for AI safeguards
- **Trust Chain Protocol** — delegation, custody, and verification architecture for multi-agent systems
- **Negative Space Mapper** — a tool that identifies meaningful absences without taking over interpretation
- **Sovereign Thinking Tools** — 48 judgment-building protocols spanning cognitive bypass, structural diagnostics, and developmental training

-----

## What This Work Is Trying to Do

This ecosystem is built around one central problem:

As AI becomes more capable, the main question is no longer just whether outputs are useful.

The deeper questions are:

- Who is actually governing the interaction?
- What safety boundaries exist before the model begins to drift?
- How does a human remain sovereign during collaboration?
- How do we preserve authorship instead of flattening it?
- How do we make trust, delegation, and provenance legible afterward?
- How do we build the human judgment that AI collaboration is quietly replacing?

Each repository addresses one part of that larger problem.

-----

## If You Only Read One Thing

- For safety: **Frozen Kernel**
- For practical use: **AI Collaboration Field Guide**
- For authorship and provenance: **Dimensional Authorship**
- For evaluation: **Safety Ledgers**
- For multi-agent trust: **Trust Chain Protocol**
- For a concrete tool: **Negative Space Mapper**
- For building judgment: **Sovereign Thinking Tools**

-----

## License / Use

Everything here is public, free, and intended to be useful.

You do not need technical expertise to read it.
You do not need permission to learn from it.
You do not need to agree with all of it to find something usable.
