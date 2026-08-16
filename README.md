# Lemu

<img width="942" height="403" alt="image" src="https://github.com/user-attachments/assets/69660c99-f080-4273-9b32-8949aff24bf6" />

**Liquid Engagement Multiplier Utility**

> Turn your Pump.fun bags into amplified, coordinated community power — with a transparent quorum trigger, preference-based signaling, and a light learning layer.

Lemu is an open-source community helper built for Pump.fun tokens. It lets holders of any Pump.fun-launched coin signal once, then amplifies that signal across the entire holder base only when a clear legitimacy threshold (≥10% of circulating supply or holder-weighted value) is reached. The result: one of the strongest coordinated community moves on Solana meme coins, without forcing everyone to stay glued to every chart or Telegram.

Built as a public good for the Pump.fun ecosystem.

---

## Why Lemu?

Pump.fun makes launching a token easy. Coordinating the community after launch is hard.  
Most holders never act together because the UX is fragmented and individual impact feels diluted.

Lemu solves three problems at once:

1. **Coordination failure** – Most holders never signal or move together because it’s messy and the impact feels tiny.
2. **Legitimacy** – A community action (signal, hold, migrate, or social push) should only fire when a meaningful portion of holders actually agree.
3. **Signal quality** – Raw calls are noisy. Historical patterns (volume spikes, holder retention, previous successful quorums) can surface useful context.

When the quorum trigger fires, the coordinated signal from ≥10% of the supply moves as one — giving the community far more weight than scattered individual posts or buys.

---

## Key Features

- **One-time preference setting**  
  Users configure once:
  - Follow a specific set of community leads or wallets
  - Auto-signal “Bullish / Neutral / Exit” on categories (new listings, migrations, marketing pushes, etc.)
  - Custom rules via simple YAML or on-chain config

- **Quorum Trigger**  
  The community-level action is submitted **only** when ≥10% of current circulating supply (or holder-weighted value) has signaled the same direction. Below threshold → no coordinated move. Transparent and non-custodial.

- **Off-chain signal aggregation → on-chain / social execution**  
  Signals collected via lightweight signed messages or dedicated accounts. When quorum is hit, Lemu can trigger a public attestation, dashboard update, and optional coordinated social or on-chain signal.

- **Transparent attestation + public dashboard**  
  Every trigger produces a verifiable record (which wallets signaled, exact supply snapshot, final direction). Live dashboard shows current participation, projected strength, and historical outcomes.

- **Mild learning component**  
  Surfaces simple, auditable correlations:  
  “Signals of type X historically correlated with +Y% volume or holder retention over the next Z hours.”  
  Purely informational — never auto-executes based on the model. Designed to be improved by the community.

- **Non-custodial & progressive**  
  Users keep full control of their tokens. Lemu never holds keys. Preference updates and signal revocation are instant.

---

## How the Quorum Trigger Works

Signal window opens
        ↓
Holders submit signed signals
        ↓
Lemu continuously aggregates:Unique wallet balance / supply weight behind each signal
Direction (Bullish / Neutral / Exit)
        ↓

If summed weight ≥ 10% of circulating supply
        ↓
Lemu publishes the coordinated attestation + dashboard update
        ↓
Optional community action or social signal is released

If the 10% threshold is never reached, no coordinated move happens. This is intentional: legitimacy over forced pumps.

---

## Getting Started

### Prerequisites
- Node.js 20+
- A Solana wallet (example: `61XL88MLZj96yxD4bVQNL35GH9YgnSLGg7R6uN5Rp3CW`)
- Small amount of SOL for fees (signals are near-free)

Tip JarIf you find Lemu useful, feel free to send a tip:Solana Address:
61XL88MLZj96yxD4bVQNL35GH9YgnSLGg7R6uN5Rp3CW



### Quick start

```bash
git clone https://github.com/your-username/lemu.git
cd lemu
npm install
cp .env.example .env
npm run dev
lemu config set \
  --follow <wallet-or-lead> \
  --category migration:bullish \
  --category marketing:neutral

  
