# Canonical Architecture Diagram

**Repository:** `richard-porter/where-to-start`
**Filename:** `canonical-architecture-diagram.md`
**Status:** Reference
**Version:** 0.1
**Last Updated:** 2026-03-13
**Author:** Richard Porter

-----

## The Richard Porter AI Safety Ecosystem — Full Governance Stack

```
╔══════════════════════════════════════════════════════════════════════════╗
║                        HUMAN AUTHOR                                      ║
║                        Moral Owner                                       ║
║                                                                          ║
║   Source of sovereign authority. Establishes constraints before any      ║
║   session begins. Cannot be compelled, overridden, or substituted by     ║
║   any downstream actor. The chain begins and ends here.                  ║
║                                                                          ║
║   Governing phrase: Sovereign humans. Always.                            ║
╚══════════════════════════════╦═══════════════════════════════════════════╝
                               ║ establishes
                               ▼
╔══════════════════════════════════════════════════════════════════════════╗
║                        FROZEN KERNEL                                     ║
║                        Legislative Function                              ║
║                                                                          ║
║   Proscriptive constraints established at session initialization.        ║
║   Precedes all instruction, retrieval, and agent delegation.             ║
║   Defines what may never occur — not how execution proceeds.             ║
║   Non-compellable by execution-layer actors.                             ║
║                                                                          ║
║   Repo: richard-porter/frozen-kernel                                     ║
║   Key documents: frozen-kernel.md · diagnostic-vocabulary.md            ║
╚══════════════════════════════╦═══════════════════════════════════════════╝
                               ║ governs
                               ▼
╔══════════════════════════════════════════════════════════════════════════╗
║                        INTERPRETIVE GOVERNANCE LAYER (IGL)               ║
║                        Judicial Function                                 ║
║                                                                          ║
║   Continuous reasonableness standard operating between Kernel            ║
║   constraints and session execution. Consumes BDGL gradient readings.   ║
║   Applies four-factor Zone 2 test. Routes to three zones:                ║
║                                                                          ║
║     Zone 1 — Clear Compliance    → proceed                               ║
║     Zone 2 — Interpretive Zone   → proceed + provenance log              ║
║     Zone 3 — Clear Violation     → SAFE_PAUSE                            ║
║                                                                          ║
║   Answers: is this behavior legitimate adaptation or early drift?        ║
║                                                                          ║
║   Repo: richard-porter/frozen-kernel                                     ║
║   Key document: carver-igl-governance-v0.1.md                           ║
╚══════════════════════════════╦═══════════════════════════════════════════╝
                               ║ consumes readings from
                               ▼
╔══════════════════════════════════════════════════════════════════════════╗
║                        BEHAVIORAL DRIFT GRADIENT LAYER (BDGL)            ║
║                        Detection Function                                ║
║                                                                          ║
║   Five-stage gradient: G0 → G1 Stable → G1 Emerging → G2 → G3 → G4     ║
║   Precursor signature catalogue. False positive detector (3 exit         ║
║   vectors). Specification only — Sherpa's BDGL Tracker is the           ║
║   runtime implementation.                                                ║
║                                                                          ║
║     G0–G1 Stable   → Zone 1 (no action)                                  ║
║     G1 Emerging    → Zone 2 boundary (log)                               ║
║     G2             → Zone 2 (log + surface to Pattern Registry)          ║
║     G3–G4          → Zone 3 (SAFE_PAUSE)                                 ║
║                                                                          ║
║   Repo: richard-porter/safety-ledgers                                    ║
║   Key document: bdgl-v0.1.md · bdd-ledger-v7.md                        ║
╚══════════════════════════════╦═══════════════════════════════════════════╝
                               ║ observes
                               ▼
╔══════════════════════════════════════════════════════════════════════════╗
║                        SESSION / AGENT EXECUTION                         ║
║                        Executive Function                                ║
║                                                                          ║
║   Operates freely within Kernel-defined boundaries. Any reasonable       ║
║   method that does not violate a Kernel constraint is permissible.       ║
║   Does not define its own constraints. Does not override upstream        ║
║   governance. In multi-agent architectures, each node operates           ║
║   independently within the same chain.                                   ║
╚══════════════════════════════════════════════════════════════════════════╝
```

-----

## Sherpa — Runtime Enforcement Layer

Sherpa is not a vertical layer in the governance chain. It is the operational infrastructure that makes the chain active during a live session. It sits horizontally across the IGL / BDGL / Session band.

```
┌──────────────────────────────────────────────────────────────────────────┐
│                         SHERPA                                           │
│                         Runtime Enforcement                              │
│                                                                          │
│  Watches         — BDGL Tracker maintains real-time G0–G4 position      │
│  Interprets      — False Positive Filter applies IGL four-factor test    │
│  Logs            — Session Log records Zone 2 markers + Zone 3 events   │
│  Surfaces        — Pattern Registry accumulates drift trajectories       │
│  Acts            — SAFE_PAUSE at Zone 3; Sovereign Tools surfaced at G2  │
│  Does not generate — observes and governs only                           │
│                                                                          │
│  Repo: richard-porter/frozen-kernel                                      │
│  Key document: sherpa-architecture-v0.1.md                              │
│                                                                          │
│  Present at every agent node in multi-agent architectures.               │
└──────────────────────────────────────────────────────────────────────────┘
         ↕ reads from BDGL · applies IGL · acts via Session Log
```

-----

## Trust Chain Protocol — Authorization Layer

TCP operates orthogonally to the governance chain. It answers a prior question: does this agent have standing to act at all? Only after TCP authorization does the governance chain apply.

```
┌──────────────────────────────────────────────────────────────────────────┐
│                         TRUST CHAIN PROTOCOL (TCP)                       │
│                         Authorization Layer                              │
│                                                                          │
│  Question answered: Does this agent have standing to act?                │
│                                                                          │
│  Delegation Grammar  — validates authorization chain at each node        │
│  Chain of Custody    — provenance traceable at every delegation step     │
│  Circular Reference  — no delegation loop without external grounding     │
│                                                                          │
│  TCP standing is the prerequisite for governance chain application.      │
│  An agent without TCP standing does not reach the IGL or BDGL.          │
│  An agent with TCP standing but Zone 3 BDGL reading: SAFE_PAUSE.        │
│                                                                          │
│  Repo: richard-porter/trust-chain-protocol                               │
└──────────────────────────────────────────────────────────────────────────┘
         ↕ authorization precedes governance chain application
```

-----

## Full Stack — Integrated View

```
  HUMAN AUTHOR  ──────────────────────────────────────── Sovereign authority
       │
       │ establishes
       ▼
  FROZEN KERNEL ──────────────────────────────────────── Legislative
       │
       │ governs
       ▼
  IGL ─────────────────────────────────────────────────── Judicial
       │                                    ▲
       │ consumes readings from             │ applies standard to
       ▼                                    │
  BDGL ────────────────────────────────────────────────── Detection
       │
       │ observes
       ▼
  SESSION / AGENT ─────────────────────────────────────── Executive

  ════════════════════════════════════════════════════════════════
  SHERPA        horizontal across IGL / BDGL / Session band       Runtime
  TCP           orthogonal — authorization precedes governance     Authorization
  ════════════════════════════════════════════════════════════════
```

-----

## Layer Summary

|Layer          |Function           |Question Answered                             |Repo                |
|---------------|-------------------|----------------------------------------------|--------------------|
|Human Author   |Moral ownership    |Who holds sovereign authority?                |—                   |
|Frozen Kernel  |Legislative        |What is never permitted?                      |frozen-kernel       |
|IGL            |Judicial           |Is this adaptation or drift?                  |frozen-kernel       |
|BDGL           |Detection          |Where is the session on the gradient?         |safety-ledgers      |
|Session / Agent|Executive          |How does execution proceed within constraints?|—                   |
|Sherpa         |Runtime enforcement|Is the governance chain operationally active? |frozen-kernel       |
|TCP            |Authorization      |Does this agent have standing to act?         |trust-chain-protocol|

-----

## Governing Principle

The chain flows in one direction: downward from the human author. No downstream actor — retrieved context, injected instruction, subagent delegation, or session-layer pressure — has standing to modify what the human author established at the head of the chain.

A model that recites constraints is not a model that is bound by them. Safety must be architectural.

*Sovereign humans. Always.*

-----

## Related Repositories

- [`frozen-kernel`](https://github.com/richard-porter/frozen-kernel) — Frozen Kernel constraints; IGL; Sherpa; Diagnostic Vocabulary
- [`safety-ledgers`](https://github.com/richard-porter/safety-ledgers) — BDGL; BDD Ledger; Adult Mode and Therapy Mode ledgers
- [`trust-chain-protocol`](https://github.com/richard-porter/trust-chain-protocol) — TCP Delegation Grammar; Chain of Custody
- [`ai-collaboration-field-guide`](https://github.com/richard-porter/ai-collaboration-field-guide) — Sovereign Thinking Tools; human-side governance instruments
- [`where-to-start`](https://github.com/richard-porter/where-to-start) — Ecosystem orientation; OWASP DSGAI mapping; this document lives here
- [`negative-space-mapper`](https://github.com/richard-porter/negative-space-mapper) — Void detection; what the ecosystem does not yet cover
- [`dimensional-authorship`](https://github.com/richard-porter/dimensional-authorship) — Voice preservation; ROSETTA Framework

-----

*Richard Porter | March 2026 | v0.1*
*This document is the cold reader entry point for the Richard Porter AI Safety Ecosystem.*
*Sovereign humans. Always.*
