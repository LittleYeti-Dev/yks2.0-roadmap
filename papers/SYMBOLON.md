# White Paper — SYMBOLON (Agentic ICAM / Identity-Card Service)

## Use case
A chain of agents delegates work and spends money. One step misbehaves. Investigators cannot determine *which* agent did *what* — the agents shared a human's token or a broad static key.

## The problem (evidenced)
- Supporting agents by **replaying the user's token or using broad static keys destroys accountability**; delegation chains undermine audit trails and **non-repudiation** ([AI Identity: Standards & Gaps, arXiv:2604.23280](https://arxiv.org/pdf/2604.23280)).
- MCP/A2A define how agents communicate **but not who they are**; verifiable delegation across them is an open problem ([AIP, arXiv:2603.24775](https://arxiv.org/pdf/2603.24775)).
- Zero-trust, decentralized agent identity with fine-grained access is an active research direction ([Zero-Trust Identity for Agentic AI, arXiv:2505.19301](https://arxiv.org/html/2505.19301v1)).

## How SKIPJACK solves it
SYMBOLON productizes the AICP identity-card protocol: per-agent, phase-gated, least-privilege, **offline-verifiable** identity with card multiplexing across classification domains. It conforms to the forming standards (NIST agent identity, FIDO, W3C DID/VC, A2A Agent Cards) rather than fighting them, and adds the DDIL/air-gap verifiability incumbents lack.
