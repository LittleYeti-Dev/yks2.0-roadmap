# Rectified Diff — ologos vs YKS 2.0 (v1.1)

_Supersedes v0.1 (yks1.0) and the v0.2 rectified draft. Re-scores each original delta against YKS 2.0 after full rectification; all adopt-planned items are now closed and ADR-recorded._
_Status: **RECTIFIED** (adopted, ADR-recorded) · **ALIGNED** (converged) · **RETAINED-YKS** (kept by design) · **MOAT** (YKS-unique)._

## Process / structure
| Original gap (v0.1) | Status | Via |
|---|---|---|
| Ad-hoc "vibe" layout, no ADRs | **RECTIFIED** | ADR-YKS-0001 (aide-canon ADR process + 1/2/3 baselines) |

## STANDARDS
| Delta | Status | Via |
|---|---|---|
| STD-01 Agent governance model | **RECTIFIED** | NOMOS adopts OAgents conformance (ADR-0009) |
| STD-02 Conformance levels | **RECTIFIED** | NOMOS + EXAMEN (ADR-0009) |
| STD-03 Agent identity (AICP) | **RECTIFIED** | SYMBOLON adopts AICP (ADR-0009) |
| STD-04 Schema / versioning | **RECTIFIED** | ADR-YKS-0011 (oagent-core schema policy) |
| STD-05 Control taxonomy (6-cat) | **RECTIFIED** | PROVIDENTIA adopts control registry |
| STD-06 Provenance surface | **ALIGNED** | ACTA ← in-toto/SLSA/SCITT |

## ARCHITECTURE
| Delta | Status | Via |
|---|---|---|
| ARCH-01 Reference architecture | **ALIGNED** | HGC³AE² ↔ MxM (ADR-0009) |
| ARCH-02 Orchestration substrate | **MOAT** | FUNDAMENTUM custody substrate — no ologos equivalent |
| ARCH-03 Agent contract (6-section tiered) | **RECTIFIED** | NOMOS = six-surface MxM (ADR-0010) |
| ARCH-04 Memory architecture | **RECTIFIED** | THESAURUS ← Nous |
| ARCH-05 Policy enforcement (PDP) | **RECTIFIED** | NOMOS adopts oagent-core PDP |
| ARCH-06 Visual / model tooling | **RECTIFIED** | ADR-YKS-0012 (Ordinal .ologic + eidolon PLM → FABRICA) |

## ENGINEERING
| Delta | Status | Via |
|---|---|---|
| ENG-01 QA engine | **RECTIFIED** | EXAMEN ← o-qa 8-dim cross-model QA |
| ENG-02 Skills packaging | **RECTIFIED** | ADR-YKS-0013 (productivity-skills → MEANS surface) |
| ENG-03 Deploy pattern | **RETAINED-YKS** | OIDC→SSM zero-static-cred (our strength) |
| ENG-04 Verification (self-attestation gap) | **RECTIFIED** | EXAMEN + NEMESIS; Zero-Trust Law 1 (ADR-0004) |
| ENG-05 Eval / regression | **RECTIFIED** | PL-9/EXAMEN eval-as-conformance |
| ENG-06 Stack composition | **ALIGNED** | Debian + Docker (platform-OS canon) |

## OPERATIONS
| Delta | Status | Via |
|---|---|---|
| OPS-01 Work queue | **RETAINED-YKS** | Issues + pill triage; ARX adds console viewers |
| OPS-02 Agent runtime | **RETAINED-YKS** | NOMOS/MxM, rebuilt zero-trust-native |
| OPS-03 Telemetry shape | **ALIGNED** | ACTA ← structured append-only + attestation |
| OPS-04 Long-term memory ops | **RECTIFIED** | THESAURUS (Nous) |
| OPS-05 Scheduling | **RETAINED-YKS** | owned-scheduling kept |
| OPS-06 Human-in-the-loop | **ALIGNED** | two-key + observed-privilege |

## Tally (v1.1)
**RECTIFIED: 15 · ALIGNED: 5 · RETAINED-YKS: 4 · MOAT: 1 · OPEN: 0**

## Read
Every place ologos led is now adopted and recorded as an ADR, in their constructs (MxM / AICP / OAgents / control-registry / schema-versioning / PLM / skills). What remains different is deliberate — our deploy/queue/scheduling/publishing strengths — or the one MOAT they have no answer to: the custody/freshness substrate (FUNDAMENTUM). No accidental gaps remain.
