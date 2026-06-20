# White Paper — ACTA (Attestation / Provenance Ledger)

## Use case
An agent ships an artifact — or takes an action — and weeks later it is implicated in an incident. Nobody can prove what produced it, in what environment, or whether it was tampered with.

## The problem (evidenced)
- **Supply-chain attacks exploded** from 216 (2015-2019) to ~88,000 in 2022 ([Empirical Study, arXiv:2308.04898](https://arxiv.org/pdf/2308.04898)).
- Even valid attestations fail when **provenance is produced outside the trust boundary**; SLSA adoption faces real deployment challenges ([SLSA Challenges, arXiv:2409.05014](https://arxiv.org/pdf/2409.05014); [Metadata Reference Architecture, arXiv:2310.06300](https://arxiv.org/html/2310.06300v2)).

## How SKIPJACK solves it
ACTA adopts the mature open standards — **in-toto, SLSA, Sigstore** — and extends build-grade attestation to **agent actions**, writing an append-only, externally-stored provenance ledger the actor cannot rewrite. Combined with the substrate's independent vantage, it ensures provenance is produced *inside* the trust boundary, closing the gap that defeats naive attestation.
