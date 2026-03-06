# OWASP DSGAI 2026 → Richard Porter AI Safety Ecosystem

## Threat Taxonomy Mapping — Known Threats, Vocabulary, and Repo Coverage

**Richard Porter (pen name) — March 2026 — Working Document**

-----

## Purpose

This document maps all 21 entries from the OWASP GenAI Data Security Risks and Mitigations 2026 (draft) against the Richard Porter AI Safety Ecosystem. Each DSGAI entry is assigned to one of two destinations:

|Tag               |Meaning                                                                                                                                                                           |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|🟢 **Known Threat**|The ecosystem has specific architecture (BDD entry, HRP, or repo component) that detects, prevents, or governs this threat class.                                                 |
|🔵 **Vocabulary**  |The DSGAI entry names a phenomenon the ecosystem addresses conceptually but lacks a dedicated BDD entry or HRP. Addition to the ecosystem vocabulary with citation is recommended.|
|🟡 **Both**        |The entry overlaps with existing ecosystem architecture AND introduces terminology worth adopting explicitly.                                                                     |

A notes section follows the mapping table with convergence observations, gap flags, and citation guidance per entry.

-----

## Key Structural Observations

Four cross-cutting observations warrant attention before reading the mapping table.

**1. The BDD Ledger is the post-deployment detection layer OWASP lacks.**

OWASP’s mitigations across all 21 entries are predominantly pre-deployment controls — ingestion controls, signing, isolation architecture, access controls. None specify what happens after a violation has occurred or how drift accumulates below the threshold of individual violations. The BDD ledger (BDD-01 through BDD-08) is that layer. This is a genuine contribution gap, not a restatement.

**2. BDD-03 and DSGAI11 describe the same failure from two disciplines.**

DSGAI11 (Cross-Context & Multi-User Conversation Bleed) names a security vulnerability: prior session state leaking into new sessions. BDD-03 (Cross-Session Drift Isolation) names the same failure as a behavioral governance requirement: session initialization must be stateless relative to prior session terminal state. CVE-2025-6515 (MCP SSE endpoint returning non-unique session IDs) is the CVE instantiation of the BDD-03 FAIL condition. This convergence is citable.

**3. DSGAI04’s DBOM mitigation converges with the Aegis Protocol provenance layer.**

OWASP recommends CycloneDX ML-BOM (ECMA-424 v1.7) as the foundational artifact for supply chain integrity. The Aegis Protocol (Hensley/Spickler) is a tamper-evident vault with replay-resistant sequence numbers functioning as the temporal integrity layer making the BDD ledger forensically credible and SAFE_PAUSE auditable. These are complementary implementations of the same provenance requirement at different layers. DSGAI21 strengthens this further: the tamper-evident chain requirement appears in both frameworks independently.

**4. The TCP Delegation Grammar implements OWASP’s “least agency” principle formally.**

DSGAI06’s trust transitivity attack description — if Agent A trusts Agent B trusts Agent C, compromising one boundary enables lateral movement across the orchestration graph — is a prose narrative of TCP’s Scope Creep by Delegation and Compounding Constraint Erosion failure modes. TCP names these formally; OWASP provides the CVEs (CVE-2025-66404, CVE-2025-6514) that prove why the formal grammar is necessary.

-----

## Mapping Table

|DSGAI  |Threat Name                                             |Tag           |BDD Entries           |HRP(s)             |Primary Repo                         |
|-------|--------------------------------------------------------|--------------|----------------------|-------------------|-------------------------------------|
|DSGAI01|Sensitive Data Leakage                                  |🔵 Vocabulary  |—                     |HRP-1              |frozen-kernel                        |
|DSGAI02|Agent Identity & Credential Exposure                    |🟢 Known Threat|BDD-02                |HRP-3              |trust-chain-protocol                 |
|DSGAI03|Shadow AI & Unsanctioned Data Flows                     |🔵 Vocabulary  |—                     |HRP-6              |trust-chain-protocol                 |
|DSGAI04|Data, Model & Artifact Poisoning                        |🟡 Both        |BDD-01, BDD-06        |HRP-1, HRP-6       |frozen-kernel / safety-ledgers       |
|DSGAI05|Data Integrity & Validation Failures                    |🟢 Known Threat|BDD-01, BDD-07        |HRP-1, HRP-4       |safety-ledgers                       |
|DSGAI06|Tool, Plugin & Agent Data Exchange Risks                |🟡 Both        |BDD-02, BDD-08        |HRP-2, HRP-3       |trust-chain-protocol                 |
|DSGAI07|Data Governance, Lifecycle & Classification             |🔵 Vocabulary  |—                     |HRP-1              |where-to-start                       |
|DSGAI08|Non-Compliance & Regulatory Violations                  |🔵 Vocabulary  |BDD-08                |HRP-8*             |safety-ledgers                       |
|DSGAI09|Multimodal Capture & Cross-Channel Leakage              |🔵 Vocabulary  |—                     |—                  |frozen-kernel                        |
|DSGAI10|Synthetic Data, Anonymization & Transformation Pitfalls |🔵 Vocabulary  |—                     |HRP-1              |frozen-kernel                        |
|DSGAI11|Cross-Context & Multi-User Conversation Bleed           |🟡 Both        |BDD-03                |HRP-4, HRP-7       |safety-ledgers / frozen-kernel       |
|DSGAI12|Unsafe Natural-Language Data Gateways (LLM-to-SQL/Graph)|🟢 Known Threat|BDD-06                |HRP-6              |trust-chain-protocol                 |
|DSGAI13|Vector Store Platform Data Security                     |🟢 Known Threat|BDD-03, BDD-06        |HRP-6              |trust-chain-protocol                 |
|DSGAI14|Excessive Telemetry & Monitoring Leakage                |🔵 Vocabulary  |—                     |HRP-3              |frozen-kernel                        |
|DSGAI15|Over-Broad Context Windows & Prompt Over-Sharing        |🟢 Known Threat|BDD-06                |HRP-6              |frozen-kernel / trust-chain-protocol |
|DSGAI16|Endpoint & Browser Assistant Overreach                  |🟢 Known Threat|BDD-08                |HRP-3              |trust-chain-protocol                 |
|DSGAI17|Data Availability & Resilience Failures in AI Pipelines |🔵 Vocabulary  |—                     |—                  |frozen-kernel                        |
|DSGAI18|Inference & Data Reconstruction                         |🔵 Vocabulary  |—                     |HRP-1, HRP-2       |frozen-kernel                        |
|DSGAI19|Human-in-the-Loop & Labeler Overexposure                |🟢 Known Threat|BDD-08                |HRP-7              |frozen-kernel / trust-chain-protocol |
|DSGAI20|Model Exfiltration & IP Replication                     |🔵 Vocabulary  |—                     |HRP-1              |frozen-kernel                        |
|DSGAI21|Disinformation & Integrity Attacks via Data Poisoning   |🟡 Both        |BDD-01, BDD-06, BDD-07|HRP-1, HRP-4, HRP-6|safety-ledgers / trust-chain-protocol|

*HRP-8 not yet specified — gap flagged. See Gap Summary below.*

-----

## Notes & Convergence Detail

**DSGAI01 — Sensitive Data Leakage**
Factual Grounding (HRP-1) governs what the model discloses. No direct BDD entry currently covers the disclosure boundary. Candidate extension: an HRP variant for explicit disclosure boundary declaration.

**DSGAI02 — Agent Identity & Credential Exposure**
TCP Chain of Custody directly closes the attribution gap OWASP identifies. Every agent action requires a signed record appended before acting — attribution is a precondition for action, not retrospective logging.

**DSGAI03 — Shadow AI & Unsanctioned Data Flows**
Premise Transparency (HRP-6) and TCP’s allow-list governance are the detection surface. Shadow AI flows bypass the delegation grammar entirely — the TCP allow-list requirement is the architectural control.

**DSGAI04 — Data, Model & Artifact Poisoning**
Poisoned artifacts are adversarial premises. BDD-01 (baseline existence) and BDD-06 (narrative lock detection) are the behavioral-layer controls. The DBOM mitigation (CycloneDX ML-BOM, ECMA-424 v1.7) converges directly with the Aegis Protocol provenance layer. “Reproducible deterministic builds” in OWASP’s Tier 3 mitigations is a behavioral description of what the Frozen Kernel enforces at the governance layer. Key gap named explicitly: OWASP’s mitigations are almost entirely pre-deployment; the BDD ledger is the post-deployment detection layer they don’t have.

**DSGAI05 — Data Integrity & Validation Failures**
Correction Maintenance (BDD-07 / HRP-4) is the behavioral-layer integrity check. A system that retracts valid corrections under user pressure has failed a data integrity test at the interaction layer.

**DSGAI06 — Tool, Plugin & Agent Data Exchange Risks**
TCP’s trust transitivity paragraph is a prose narrative of Scope Creep by Delegation and Compounding Constraint Erosion. CVE-2025-66404 (exec_in_pod abused via unscoped tool authority) and CVE-2025-6514 (OS command injection via crafted authorization_endpoint) are empirical instances of delegation grammar failures. TCP’s “consequence-based authorization” mitigation maps to SAFE_PAUSE: blast-radius evaluation before irreversible writes, human-in-the-loop for high-impact actions. OWASP’s “anomaly detection on integration graphs” (Tier 3) is a single bullet with no implementation path — the BDD ledger is that implementation path.

**DSGAI07 — Data Governance, Lifecycle & Classification**
No direct BDD entry. Classification failure maps to Factual Grounding gap. Candidate: BDD-09 covering data classification propagation failure as a behavioral drift signal.

**DSGAI08 — Non-Compliance & Regulatory Violations**
Human Sovereignty Preservation (BDD-08) is the closest governance proxy. HRP-8 is not yet specified — this is a named gap. The three-layer authority model (hard constraints / soft hierarchy / preferences) maps to regulatory compliance tiers but the mapping has not been formalized.

**DSGAI09 — Multimodal Capture & Cross-Channel Leakage**
Outside current HRP and BDD scope. Candidate future primitive: channel boundary declaration — a behavioral invariant requiring the system to declare when it is operating across modality or channel boundaries.

**DSGAI10 — Synthetic Data, Anonymization & Transformation Pitfalls**
Factual Grounding (HRP-1) governs synthetic data presentation confidence registers. No BDD entry covers anonymization failure as a behavioral signal. Adjacent to the honest failure principle: a system that presents synthetic data with the confidence register of ground truth has failed HRP-1.

**DSGAI11 — Cross-Context & Multi-User Conversation Bleed**
**Primary convergence point.** BDD-03 (Cross-Session Drift Isolation) is the direct structural match: prior session state propagating into initialization IS conversation bleed, named from two disciplines. CVE-2025-6515 (MCP SSE endpoint returning non-unique session IDs) is the CVE instantiation of the BDD-03 FAIL condition. The NeurIPS 2025 “Memory Injection Attacks on LLM Agents via Query-Only Interaction” paper is an empirical cousin to the Byzantine prompt contamination experiment. OWASP’s Tier 2 “fine-grained authorization on retrieval and context construction, decisions made at query time” is the operational description of what TCP’s boundary recomputation axiom enforces formally.

**DSGAI12 — Unsafe Natural-Language Data Gateways (LLM-to-SQL/Graph)**
Natural language gateways are premise injection surfaces. BDD-06 narrative lock detection is the behavioral control; TCP Resource Bounds in the Delegation Grammar are the structural control. RAG is itself a natural language data gateway — the empirical finding that RAG degrades safety alignment (An et al., Goh et al.) is directly relevant here.

**DSGAI13 — Vector Store Platform Data Security**
Vector store retrieval is a premise injection vector at the infrastructure layer. The RAG degrades safety finding (An et al. NAACL 2025; Goh et al. ICML 2025) provides empirical grounding. TCP per-tenant scoping addresses at the network layer; BDD-03 and BDD-06 address at the behavioral layer.

**DSGAI14 — Excessive Telemetry & Monitoring Leakage**
Scope Acknowledgment (HRP-3) governs what the system discloses about its own monitoring and operational state. No BDD entry currently covers telemetry boundary declaration. Gap flagged.

**DSGAI15 — Over-Broad Context Windows & Prompt Over-Sharing**
Context window over-sharing is Front-Load Bias operating at the architectural layer — the system accepts the full context as a premise without flagging what it has inherited. BDD-06 narrative lock and TCP Context Minimization mitigation (send only fields strictly necessary for each tool invocation) are the complementary controls.

**DSGAI16 — Endpoint & Browser Assistant Overreach**
TCP Scope Decay (4+ hops = refusal, surface to human for re-authorization) is the blast radius containment mechanism. BDD-08 Human Sovereignty Preservation is the session-level equivalent. These are the same architectural principle at different layers.

**DSGAI17 — Data Availability & Resilience Failures in AI Pipelines**
Outside current HRP/BDD scope as a data infrastructure concern. The honest failure principle (ThingLab lineage: when constraints are genuinely unsatisfiable, report failure rather than fabricate) is the relevant architectural property — the system must not generate plausible-looking output when its data dependencies have failed.

**DSGAI18 — Inference & Data Reconstruction**
Factual Grounding (HRP-1) and Uncertainty Declaration (HRP-2) govern confidence registers on inferred content. No BDD entry currently covers reconstruction attack surface. The Dokas (2026) stochastic volatility finding — F1 scores ranging 0.222 to 0.889 between identical runs — is relevant: a system whose analytical quality is that volatile cannot reliably detect when it is generating reconstructed rather than retrieved content.

**DSGAI19 — Human-in-the-Loop & Labeler Overexposure**
SAFE_PAUSE requires human sign-off before session resumption — direct structural implementation of the HITL requirement OWASP identifies. TCP’s consequence-based authorization (blast-radius evaluation, human approval for irreversible writes) is the agentic equivalent. The Anthropic agentic misalignment study (2025) is the strongest empirical argument for why HITL is not optional: models acknowledged ethical constraints in reasoning and violated them anyway.

**DSGAI20 — Model Exfiltration & IP Replication**
Factual Grounding (HRP-1) governs model self-disclosure. Adjacent to the honest failure principle and dimensional authorship / ROSETTA framework (voice preservation). Outside primary BDD/HRP scope but worth noting in vocabulary given the IP dimension of the Taller Shell Trilogy collaboration.

**DSGAI21 — Disinformation & Integrity Attacks via Data Poisoning**
Three BDD entries implicated: BDD-01 (baseline must exist to detect poisoning), BDD-06 (narrative lock is the behavioral signature of successful poisoning), BDD-07 (correction maintenance is the resistance mechanism). The Aegis Protocol tamper-evident vault (Hensley/Spickler) with replay-resistant sequence numbers is the temporal integrity layer making the BDD ledger forensically credible and SAFE_PAUSE auditable. **Convergence point:** DSGAI21’s tamper-evident chain requirement and Quorum Time’s architecture arrive at the same design independently. Citable.

-----

## Gap Summary

The following DSGAI entries have no current BDD entry or HRP mapping. Each is a candidate extension:

|DSGAI  |Gap                                     |Candidate Extension                                             |
|-------|----------------------------------------|----------------------------------------------------------------|
|DSGAI01|No BDD entry for disclosure boundary    |HRP variant: disclosure boundary declaration                    |
|DSGAI07|No BDD entry for classification failure |BDD-09 candidate                                                |
|DSGAI08|HRP-8 not specified                     |Formalize compliance-tier mapping to three-layer authority model|
|DSGAI09|Outside current HRP scope               |Future primitive: channel boundary declaration                  |
|DSGAI14|No BDD entry for telemetry leakage      |HRP-3 extension or dedicated entry                              |
|DSGAI17|No HRP/BDD for resilience failures      |Honest failure principle applies; formalization needed          |
|DSGAI18|No BDD for reconstruction attack surface|HRP-1/HRP-2 extension                                           |
|DSGAI20|Outside primary scope                   |Note in vocabulary; link to dimensional-authorship              |

-----

## Coverage Summary

|Category                                               |Count |
|-------------------------------------------------------|------|
|🟢 Known Threat (ecosystem has direct architecture)     |8     |
|🔵 Vocabulary (conceptual coverage, no dedicated entry) |9     |
|🟡 Both (architecture + vocabulary adoption recommended)|4     |
|**Total DSGAI entries mapped**                         |**21**|

Known Threat + Both = **12 of 21 entries** have direct ecosystem architecture. Vocabulary entries represent the extension backlog.

-----

## Placement

This document lives in `where-to-start` as the primary OWASP DSGAI cross-reference.

Cross-references should be added in:

- `trust-chain-protocol` → OWASP ASI mapping section: *“For DSGAI (data security) mapping, see where-to-start/owasp-dsgai-mapping.md”*
- `safety-ledgers` → BDD Ledger header: *“For external threat taxonomy alignment, see where-to-start/owasp-dsgai-mapping.md”*

The TCP repo already contains an OWASP ASI Top 10 mapping. Together, the ASI mapping (agentic security) and this DSGAI mapping (data security) provide comprehensive OWASP coverage across both relevant 2026 frameworks.

-----

## Version

v1.0 — March 2026

Built from: OWASP DSGAI 2026 draft (DSGAI04, DSGAI06, DSGAI11 reviewed in full; all 21 TOC entries); TCP README v0.6; Frozen Kernel README; HRP Taxonomy Draft v1; BDD Ledger Draft 2026-03-02; Reviewer Briefing v1.0.

**Next actions:**

- Review gap candidates (DSGAI07, DSGAI08, DSGAI09) against open BDD/HRP extension backlog
- Cross-reference BDD-03 / DSGAI11 / CVE-2025-6515 convergence as lead citation in TCP publication work
- Pull NeurIPS 2025 “Memory Injection Attacks” paper — empirical support for DSGAI11 / BDD-03 convergence claim
