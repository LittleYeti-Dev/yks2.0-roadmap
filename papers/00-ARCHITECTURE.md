# White Paper — SKIPJACK Architecture: The Substrate as Core

## Use case
A coalition operates AI agents across a tactical edge, an enterprise SOC, and a degraded WAN. Connectivity is intermittent; agents must keep acting; every action must be attributable and reversible. No single vendor's point tool spans identity, memory, assurance, privilege, and custody — so teams bolt together a dozen connected-assumption products that fail the moment the link drops.

## The problem (evidenced)
- **Disconnection is the baseline, not the exception.** Benchmarks now stress agents under latency, packet loss, and bandwidth collapse and find degraded performance and stale internal state are pervasive ([AgentComm-Bench, arXiv:2603.20285](https://arxiv.org/pdf/2603.20285)).
- **Contamination crosses boundaries.** In multi-agent/shared-state systems, a single error seed cascades across sessions, roles, and users ([From Spark to Fire, arXiv:2603.04474](https://arxiv.org/abs/2603.04474v1); [Security Considerations for Multi-agent Systems, arXiv:2603.09002](https://arxiv.org/pdf/2603.09002)).
- **Governance frameworks are static; agents are dynamic.** NIST AI RMF and the EU AI Act articulate principles but were built for bounded, human-in-the-loop systems and exhibit an "agentic fitness gap" ([AAGATE, arXiv:2510.25863](https://arxiv.org/pdf/2510.25863)).

## How SKIPJACK solves it
One **above-Layer-7 custody + freshness substrate** (FUNDAMENTUM) is the core; every product line rides it. Zero-trust, telemetry, and canon are enforced **once at the core** and inherited by every module — so identity (SYMBOLON), memory (THESAURUS), assurance (EXAMEN), privilege (OCULUS), and behavioral observability (NEMESIS) are not bolted-on point tools but coherent facets of one disconnected-capable system. The substrate runs on Proxmox + Debian + Docker, degrades gracefully across regimes R0-R5, and never ships without the observed-privilege control. The moat is the integrated, zero-trust, edge-first whole.
