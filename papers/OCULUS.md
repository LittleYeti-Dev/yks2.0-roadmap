# White Paper — OCULUS (Observed-Privilege Access / zero-trust PAM)

## Use case
An admin (or a compromised agent acting as one) elevates rights at 3 a.m. and moves laterally. The grant is logged, but no one was watching when it happened. By morning the damage is done.

## The problem (evidenced)
- **Standing privileges are the key enabler of lateral movement and privilege escalation** ([Palo Alto, Zero Standing Privileges](https://www.paloaltonetworks.com/cyberpedia/zero-standing-privileges)); "you cannot achieve Zero Trust if high-risk standing privileges still exist."
- **JIT adoption is near-zero**: only ~1% of organizations have fully adopted just-in-time privileged access even as agentic identities proliferate ([CyberArk, Jan 2026](https://www.cyberark.com/press/new-study-only-1-of-organizations-have-fully-adopted-just-in-time-privileged-access-as-ai-driven-identities-rapidly-increase/)).
- Fine-grained, context-aware least-privilege data access is an active research frontier ([Data Enclave, arXiv:2510.09494](https://arxiv.org/pdf/2510.09494)).

## How SKIPJACK solves it
OCULUS makes privilege **just-in-time AND observation-bound**: elevated rights exist **only while visible to the SysOps admin on a real-time dashboard**, and revocation is equally visible. **Loss of visibility = loss of privilege (fail-closed).** Incumbent PAM (CyberArk, BeyondTrust, Delinea) does time-bound JIT but none binds the grant to live observation. Paired with field-level privilege and substrate behavioral observation, OCULUS is the SysOps board the substrate never ships without.
