# White Paper — NEMESIS (Agent Behavioral Observability & Tuning / agent-EDR)

## Use case
One agent in a fleet is quietly poisoned by injected instructions. Within hours its outputs steer the agents downstream of it. The SIEM shows failed transactions but not which agent started the cascade.

## The problem (evidenced)
- **A single injected error seed cascades** through multi-agent systems via inter-agent messages, shared memory, and tool arguments — crossing session, role, and user boundaries ([From Spark to Fire, arXiv:2603.04474](https://arxiv.org/abs/2603.04474v1)).
- **Prompt-injection success rates exceed 85%** against state-of-the-art defenses with adaptive strategies ([TAMAS, arXiv:2511.05269](https://arxiv.org/pdf/2511.05269); [Agentic Coding Injection, arXiv:2601.17548](https://arxiv.org/html/2601.17548v1)).
- Self-reported agent state cannot be trusted; governance must observe behavior ([Multi-Agent Defense Pipeline, arXiv:2509.14285](https://arxiv.org/abs/2509.14285)).

## How SKIPJACK solves it
NEMESIS observes each agent **from beneath, at the substrate** — ground truth, not self-report — detects drift/misbehavior, and tunes or constrains the agent in-flight. Because the vantage lives in the core, no agent can fool it (the structural antidote to self-attestation). It is the runtime detection-and-correction layer the cascade literature shows is missing.
