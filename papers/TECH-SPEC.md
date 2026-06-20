# SKIPJACK 2.0 — Roadmap Technical Specification v0.1
*Engineering companion to the program roadmap. Explains what is built, in what order, and why.*

## 1. Purpose & scope
This spec explains the SKIPJACK 2.0 roadmap in engineering terms: the architecture the roadmap builds toward, the build-wave sequencing and its dependency rationale, the interfaces between product lines, and the standards each must meet. It is the bridge between the roadmap (what/when) and the per-product white-paper series (why/how).

## 2. System architecture
**Substrate-as-core.** SKIPJACK is one above-Layer-7 custody + freshness substrate (FUNDAMENTUM); all ten product lines are modules that ride it. Zero-trust, telemetry, and canon are enforced **once at the substrate** and inherited by every module — they are not re-implemented per product. A module cannot be deployed in a way that bypasses the substrate without voiding the custody/freshness/zero-trust guarantees.

**Platform-OS.** Uniform across every deployment: Proxmox (hypervisor) + Debian (bookworm-slim guests) + Docker (service containers). Same artifact for every customer; the commercial/federal distinction is a compliance wrapper at sale, not a build fork (see ARCHITECTURE-01).

**Capability layers.** Forty-eight capabilities are organized into ten architecture layers — custody-bus, governance, identity, memory, telemetry, qa-eval, product-app, modeling, publishing, substrate-spine. Capabilities are non-exclusive: each has one primary line and may be shared into others, so the shared core (custody, freshness, telemetry, identity, policy, behavioral tuning) fans out across most lines.

## 3. Core interfaces & data contracts (built in W0)
- **Custody envelope (C-1..C-11):** custody-aware transport, causal ordering, freshness markers, priority fragmentation, atomic resume, bidirectional convergence, adaptive bandwidth shaping, operator-bounded autonomy, cross-link diagnostics, replay-ability, redundant out-of-band channel.
- **Freshness Quotient:** every field carries machine-readable {date-stamp, staleness class (live/aging/stale/isolated), provenance}. The substrate never presents stale state as live (two-sided safety invariant; the second invariant: never present unverified inbound as authentic).
- **Policy decision point (PDP):** one decision surface — risk / approval / allow-deny / escalation / audit — with the cyber overlay that decisions are NOT cached over contexts containing untrusted spans.
- **Identity card (AICP):** per-agent, phase-gated, least-privilege, offline-verifiable; card multiplexing across classification domains.
- **Telemetry/attestation (ACTA):** every action emits a durable, externally-stored event (in-toto/SLSA/SCITT-aligned); the actor cannot rewrite its own audit.
- **Observed-privilege (OCULUS):** JIT elevation bound to live SysOps visibility; fail-closed on loss of visibility; field-level granularity.

## 4. Build-wave sequencing (the critical path)
**W0 — Foundation (Q1-Q3).** Platform-OS, FUNDAMENTUM custody/freshness core (incl. degraded modes R0-R5), the substrate behavioral-observation hook, NOMOS spine (PDP + zero-trust gates), SYMBOLON identity baseline, ACTA telemetry, and OCULUS (the substrate never ships without the observed-privilege SysOps board). Exit criteria: a node serves locally under a simulated blackout, presents per-field freshness, attests every action, and enforces observed-privilege fail-closed.
**W1 — Lead (Q3-Q5).** NEMESIS rides the substrate vantage to observe agents from beneath and tune in-flight; GA with OCULUS as the differentiated spearpoint.
**W2 — Integrate (Q4-Q6).** Adopt proven components: THESAURUS (Nous memory), EXAMEN (o-qa cross-model QA), ARX console, PROVIDENTIA, FABRICA, VOX, ARBITER (feature; LiteLLM-based).
**W3 — Horizon (Q6-Q8).** TEMPESTAS, MENTOR (OT), MIMESIS, IRIS (DTN/space), CUSTOS (cross-domain) — accreditation- and integration-gated.

## 5. Dependency rationale (why this order)
- **FUNDAMENTUM gates everything** — it is the keel; modules cannot exist without the custody/freshness/vantage it provides. Longest single pole; protect it.
- **The substrate vantage gates NEMESIS** — beneath-the-agent observation is ground truth (the anti-self-attestation property); it cannot be retrofitted onto a connected-assumption agent layer.
- **The Ologos IP grant gates W2** — THESAURUS/EXAMEN/ARX productize Ologos components; the license must close (target Q2) before they ship.
- **ATO is a parallel long-lead track** — RMF (categorize->select->implement->assess->authorize) takes ~12-18 months; if federal revenue is targeted it must start in Q1, not Q5. CUSTOS cross-domain (NCDSMO-grade) is the longest pole; engage by Q7.

## 6. Standards & conformance
Zero-trust: NIST SP 800-207, OMB M-22-09 (five pillars). Agent governance: OAgents conformance levels (adopted), NIST AI RMF + the agentic-fitness-gap extensions. Identity: FIDO Agentic Auth, W3C DID/VC, A2A Agent Cards, SPIFFE/SPIRE, OAuth 2.0 — SYMBOLON conforms rather than competes. Supply chain: in-toto, SLSA v1.1+, Sigstore (Cosign/Fulcio/Rekor), SBOM (CycloneDX/SPDX). Federal: RMF/ATO, CMMC, FedRAMP, CNSSI/ICD-503, DISA STIGs (per SKU).

## 7. Risks & long-lead items
FUNDAMENTUM schedule slip (mitigate: focus, no parallel sprawl); Ologos IP grant delay (mitigate: close by Q2); accreditation lead time (mitigate: start RMF Q1); incumbent + standards-body motion in identity/security (mitigate: conform to standards, lead on the novel controls — OCULUS, NEMESIS, the substrate).

## 8. References
Per-product white-paper series (use case -> peer-reviewed problem -> solution): FUNDAMENTUM, KAIROS, OCULUS (+OCULUS-01), NOMOS, ACTA, SYMBOLON, NEMESIS, ARCHITECTURE (+ARCHITECTURE-01), and the CAPSTONE zero-trust synthesis.
