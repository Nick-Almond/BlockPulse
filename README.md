# Lemu
<img width="942" height="403" alt="image" src="https://github.com/user-attachments/assets/69660c99-f080-4273-9b32-8949aff24bf6" />

**Liquid Engagement Multiplier Utility**

> Turn your JitoSOL into amplified, coordinated voting power on Solana network governance — with a transparent quorum trigger, preference-based signaling, and a light learning layer.

Lemu is an open-source governance helper that implements the exact **quorum-trigger** pattern publicly discussed by Jito’s Head of Governance. It lets JitoSOL holders signal once, then amplifies that signal across the entire stake pool only when a clear legitimacy threshold (≥10% of JitoSOL TVL) is reached. The result: one of the most influential coordinated votes on Solana, without forcing everyone to stay glued to every proposal.

Built as a public good for the Jito ecosystem.

---

## Why Lemu?

Solana now has network-level governance where staked SOL votes on protocol decisions.  
JitoSOL holders should not be sidelined.  

Lemu solves three problems at once:

1. **Coordination failure** – Most holders never vote because the UX is fragmented and the impact feels diluted.
2. **Legitimacy** – A stake pool should only move when a meaningful portion of its holders actually signal.
3. **Signal quality** – Raw votes are noisy. Historical correlation with tip revenue, client diversity outcomes, and fee-switch results can surface useful patterns.

When the quorum trigger fires, the entire Jito stake pool (currently ~10M SOL) votes as one — giving JitoSOL holders up to ~10× the influence of a normal SOL staker.

---

## Key Features

- **One-time preference setting**  
  Users configure once:
  - Follow a specific set of delegates
  - Auto-vote “Yes / No / Abstain” on categories (fee switches, client diversity, parameter changes, etc.)
  - Custom rules via simple YAML or on-chain config

- **Quorum Trigger (exactly as described)**  
  The stake-pool vote is submitted **only** when ≥10% of current JitoSOL TVL has signaled the same direction during the review period. Below threshold → no pool-level action. Transparent and non-custodial.

- **Off-chain signal aggregation → on-chain execution**  
  Signals collected via lightweight signed messages or dedicated program accounts. When quorum is hit, Lemu constructs and submits the stake-pool vote atomically.

- **Transparent attestation + public dashboard**  
  Every trigger produces a verifiable attestation (what signals were counted, exact TVL snapshot, final vote). Live dashboard shows current participation, projected influence, and historical outcomes.

- **Mild learning component**  
  Surfaces simple, auditable correlations:  
  “Proposals of type X historically correlated with +Y% tip revenue over the following Z epochs.”  
  Purely informational — never auto-executes based on the model. Designed to be replaced or improved by the community.

- **Non-custodial & progressive**  
  Users keep full control of their JitoSOL. Lemu never holds keys. Preference updates and signal revocation are instant.

---

## How the Quorum Trigger Works
