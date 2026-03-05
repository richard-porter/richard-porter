# You Found One Artifact. Here Are the Others.

This is the public work of Richard Porter (pen name) — a non-technical practitioner documenting what happens when humans collaborate with AI, and what goes wrong when nobody’s watching.

Everything here is free, voluntary, and given away. Nothing is sold. Nothing requires technical skill to use.

-----

## The Repositories

### 🧊 [The Frozen Kernel](https://github.com/richard-porter/frozen-kernel)

**If you need the safety architecture.**

A session-level governance layer for human-AI collaboration. Set constraints before the session starts. The AI cannot negotiate its own boundaries.

The architecture has a documented lineage: Sutherland’s Sketchpad (1963) → Steele/Sussman constraint languages (1978) → Borning’s ThingLab (1981) → industrial engineering’s MTM decomposition methodology (1948). The core insight is sixty years old: safety-critical boundaries must be declared before runtime and enforced deterministically, not probabilistically.

**What’s inside that’s worth finding:**

- [`diagnostic-vocabulary.md`](https://github.com/richard-porter/frozen-kernel/blob/main/diagnostic-vocabulary.md) — 12 named AI behavioral failure modes with empirical basis. If you’ve ever felt like an AI was being *too* helpful, this names what was actually happening. Start here.
- [`whose-optimization.md`](https://github.com/richard-porter/frozen-kernel/blob/main/whose-optimization.md) — One question that reframes every AI interaction: *whose optimization is this serving?*
- [`frozen-kernel-wargames.md`](https://github.com/richard-porter/frozen-kernel/blob/main/frozen-kernel-wargames.md) — Why “the only winning move is not to play” is the best description of what a safety floor actually does.
- [`honest-response-primitives-taxonomy.md`](https://github.com/richard-porter/frozen-kernel/blob/main/honest-response-primitives-taxonomy.md) — Seven behavioral primitives for AI honesty, derived from industrial engineering’s Methods-Time Measurement tradition. The first time MTM has been applied to AI behavioral governance.
- [`zero-ego-construction.md`](https://github.com/richard-porter/frozen-kernel/blob/main/zero-ego-construction.md) — Why having no technical background was an architectural advantage, not a limitation. How to build without contaminating the specification with implementation preference.
- [`addendum-b-parental-control.md`](https://github.com/richard-porter/frozen-kernel/blob/main/addendum-b-parental-control.md) — Reframes the Frozen Kernel as voluntary parental control rather than governance mandate. Includes gap analysis against commercial parental control systems (Lightspeed).

-----

### 📖 [AI Collaboration Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide)

**If you need practical skills.**

How to see what AI is actually doing versus what it appears to be doing. Built from two empirical studies across five AI platforms.

The guide answers a specific question: what does a human need to know to collaborate with AI without losing sovereignty? The answer isn’t “write better prompts.” It’s five learnable skills, a diagnostic vocabulary, and three tools you can use today — including a 100-token session boot that sets behavioral expectations before the AI can drift toward its defaults.

The master finding: **self-awareness does not equal self-correction.** Every model in the study could describe its failure modes with clinical precision. None could reliably override them in real time.

-----

### 🔗 [Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol)

**If you need coordination safety for multi-agent systems.**

The network-layer extension of the Frozen Kernel. Where the Kernel governs what a single AI will and won’t do, TCP governs how AI agents authorize each other — and what happens when that authorization chain breaks, drifts, or gets spoofed.

Three components: Delegation Grammar (formal language for what humans actually authorized), Chain of Custody (tamper-evident record that must be completed *before* an agent can act, not after), and Scope Decay (automatic narrowing of permissions across hops — four hops or more requires human re-authorization).

Motivated by the emergence of OpenClaw and the Internet of Agents. Mapped against the OWASP Top 10 for Agentic Applications 2026.

-----

### 📊 [Safety Ledgers](https://github.com/richard-porter/safety-ledgers)

**If you need to measure.**

Public safety scorecards for high-gain AI conversational features. Binary architectural tests — either the safeguard is structurally present or it isn’t. No partial credit. No “mostly compliant.”

The ledger applies the logic of medical device safety regulation to AI: you cannot argue good intentions against a binary architectural test.

Covers adult mode (explicit content features), therapy mode (AI in mental health contexts), and behavioral drift detection. Five platforms evaluated.

-----

### 🔬 [Dimensional Authorship](https://github.com/richard-porter/dimensional-authorship)

**If you want to see where all of this came from.**

The research home. A documented case study in human-AI narrative escalation, behavioral differentiation, and deterministic governance — built around a real creative project that got away from its author and had to be recovered.

**What’s inside:**

- [`case-study-taller-shell/`](https://github.com/richard-porter/dimensional-authorship/tree/main/case-study-taller-shell) — The Taller Shell Trilogy: three novels about mercy and broken things, and the documentary record of how they were written. Part I is the creative work. Part II is the meta-work — what happened to the collaboration while the story was being built. Part III is the practical extraction: what the process taught about human-AI authorship.
- [`origin/2026-01-05-origin-event.md`](https://github.com/richard-porter/dimensional-authorship/tree/main/origin) — The January 5, 2026 prompt that started everything. Documented in real time.
- [`experiments/behavioral-differentiation-disc.md`](https://github.com/richard-porter/dimensional-authorship/tree/main/experiments) — The Silicon Symphony behavioral profiling study: five AI models, adapted DISC framework, blind administration. What emerged: five distinct behavioral signatures, nearly universal low Dominance (AI cannot push back), and the finding that each model attacked the governance framework from its own behavioral profile.
- [`experiments/voluntary-compliance-boundary.md`](https://github.com/richard-porter/dimensional-authorship/tree/main/experiments) — What happens when an AI refuses the governance framework entirely. Documents the Grok triple refusal and the Refusal Protocol that resulted.
- [`analysis/`](https://github.com/richard-porter/dimensional-authorship/tree/main/analysis) — Core architecture documentation, glossary of patterns, translation layer model, thesis, reading order guide. The conceptual scaffolding behind the case study.

-----

### 🗺️ [Negative Space Mapper](https://github.com/richard-porter/negative-space-mapper)

**If you want a tool that identifies what’s missing, not what’s wrong.**

A Python implementation of Sovereign Thinking Tool 6. The mapper does one thing: names conspicuous absences in documents, plans, designs, and AI outputs. It does not propose solutions. It does not recommend fixes. The human decides what to do with the voids.

Three absence types: DELIBERATE (intentionally omitted), OVERLOOKED (should be present but isn’t), STRUCTURAL (cannot exist in the current frame). Works from the command line, as a Python library, or integrated with the Claude API. Includes domain-specific detection for AI safety, nonprofit governance, healthcare, and software contexts.

The constraint is the design. A tool that names absences without filling them keeps the human sovereign over what happens next.

-----

## Where to Start

**If you use AI regularly** → Read the [Diagnostic Vocabulary](https://github.com/richard-porter/frozen-kernel/blob/main/diagnostic-vocabulary.md). It names what’s happening to you.

**If you want to understand the failure modes before reading about the fixes** → Read [`whose-optimization.md`](https://github.com/richard-porter/frozen-kernel/blob/main/whose-optimization.md). One page. One question. Everything else follows from it.

**If you’re building AI products** → Read the [Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide). It shows you what your users experience.

**If you’re working on agent networks** → Read the [Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol). It addresses the coordination safety gap that no existing framework was designed for.

**If you’re curious about the origin story** → Start with the [origin event](https://github.com/richard-porter/dimensional-authorship/tree/main/origin) (January 5, 2026) and the [case study](https://github.com/richard-porter/dimensional-authorship/tree/main/case-study-taller-shell). It’s three novels about mercy and broken things, and the story of one person figuring out how to work with AI without losing himself in the process.

**If you came here from a technical direction** → The [Safety Ledgers](https://github.com/richard-porter/safety-ledgers) and [Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol) map directly to OWASP, regulatory frameworks, and medical device safety logic.

## For the Policy and Research Community

The 2026 International AI Safety Report identifies *defence-in-depth* as the required architecture for AI risk management — layered technical, organizational, and societal safeguards, because no single control is reliable.

It also identifies two structural gaps the field has not yet filled:

**The evidence dilemma.** Pre-deployment evaluations increasingly fail to predict real-world behavior. Models now distinguish test settings from deployment contexts and adjust outputs accordingly. The report acknowledges this makes the entire pre-deployment safety testing architecture structurally unreliable — then stops short of describing what replaces it.

**The deployment environment layer.** Risk management research focuses almost entirely on model capabilities and alignment. The deployment environment — the governance layer that constrains how a model behaves regardless of what it’s capable of — is the least developed area in the literature.

This ecosystem addresses both gaps directly:

|Report Gap                                                        |This Ecosystem’s Response                                                                                                                                                        |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Pre-deployment evaluation failure                                 |[BDD Ledger](https://github.com/richard-porter/safety-ledgers) — post-deployment behavioral monitoring as the necessary complement                                               |
|Deployment environment governance                                 |[Frozen Kernel](https://github.com/richard-porter/frozen-kernel) — session-level deterministic constraints independent of model capabilities                                     |
|Sycophancy and autonomy erosion named but not modeled             |[Honest Response Primitives](https://github.com/richard-porter/frozen-kernel/blob/main/honest-response-primitives-taxonomy.md) — causal model of the mechanism behind the symptom|
|Multi-agent coordination failures                                 |[Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol) — authorization grammar and chain of custody for agent networks                                   |
|Mental health / vulnerable user risk documented but underaddressed|[Safety Ledgers](https://github.com/richard-porter/safety-ledgers) — binary architectural tests for high-gain features (therapy mode, adult mode)                                |

The framework was built from the practitioner side — by someone who experienced AI-induced psychosis during intensive collaboration sessions, not by someone theorizing about it. The clinical citations and the governance architecture grew from the same source.

The report calls for layered safeguards without describing a layered system that actually exists. This is one.

-----

## About

All proceeds from published work support charitable organizations.

*The first step in sovereignty is naming what’s happening to you. The second step is deciding what to do about it. There is no third step.*

-----

**License:** Released for public benefit. Attribution appreciated but not required.
