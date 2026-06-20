# White Paper — FUNDAMENTUM (Substrate / Custody Manager)

## Use case
A forward team queries an AI assistant during a comms blackout. The model answers confidently from cached context that is hours stale. The operator, unable to tell stale from live, acts on it. In a high-stakes setting, that is a casualty, not a typo.

## The problem (evidenced)
- **LLM agents are temporally blind.** They do not account for real-world time elapsed between messages and actions, leading to action on stale information and confident-wrong outputs ([Temporally Blind, arXiv:2510.23853](https://arxiv.org/html/2510.23853v2)).
- **Miscalibrated confidence is hard for users to detect** and measurably degrades AI-assisted decision efficacy ([Miscalibrated AI Confidence, arXiv:2402.07632](https://arxiv.org/html/2402.07632v4)).
- **Under packet loss/bandwidth collapse, internal state goes stale** and cooperative performance breaks down ([AgentComm-Bench, arXiv:2603.20285](https://arxiv.org/pdf/2603.20285)).

## How SKIPJACK solves it
FUNDAMENTUM is an above-L7 mission-state **custody** layer with a **coherence contract**: it serves locally when the link is down, reconciles on reconnect, and **never lets a consumer mistake stale data for current.** It runs the model at its current level of understanding, knows its ceiling, and exposes degraded-mode (R0-R5) explicitly so the model operates *knowingly*. This is confident-misalignment prevention at the data layer — the unique core every other product inherits.
