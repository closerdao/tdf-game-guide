# 💪 $Sweat Token Overview

The **$Sweat Token** is a Soulbound, decaying ERC-20 token that represents a Citizen's **work-based contribution** to a regenerative project like Traditional Dream Factory.

It rewards real, measurable effort — from land work and builds to kitchen shifts and governance roles — and forms a critical part of the **Proof of Sweat** governance weight.

---

## 🧬 Core Properties
- **Soulbound:** $Sweat is non-transferrable and cannot be traded.
- **ERC-20 Compatible:** Built on standard interfaces for integration.
- **Decaying:** Token value reduces over time to reflect recent contributions.

---

## 🔧 How It Works
- $Sweat is **manually minted** by the DAO or designated Bounty Managers.
- Each token represents **a specific amount of work completed**.
- Work can include:
  - Land regeneration
  - Hosting events or workshops
  - Cooking or cleaning
  - Building infrastructure
  - Coordinating governance or community processes

---

## 📉 Decay Over Time
Like $Presence, $Sweat gradually decays to ensure that recent contributions carry more governance weight than distant ones.

Decay Rate: Configurable (suggested ~0.03%/day)

Formula:
```text
decayedAmount = initialAmount * (1 - decayRatePerDay)^daysSinceContribution
```

---

## 🛠 Minting $Sweat
Current process:
- Work is verified by a Team Member, or Bounty Lead
- DAO Treasury sends tokens manually to the contributor’s wallet

**Future goal:** Integrate $Sweat with the Dework or Charmverse bounty systems for automatic reward distribution.

---

## 🔒 Access & Control
- Minting is restricted to authorized roles only
- Citizens can view balances but **cannot transfer or trade** $Sweat

**Future goal:** Migrate $Sweat to a zero knowledge proof to allow apps to verify work done, but maintain privacy for user.

---

## 🗳 Governance Role
$Sweat forms part of the **voting weight formula**:
```text
Voting Power = ($TDF Tokens * 1) + ($Presence * 5) + ($Sweat * 5)
```

Recent, meaningful contribution gives you more say in the decisions that shape our shared future.

---

## ⚠️ Considerations
- Rounding tolerances may apply in decay math
- Public dashboards and feedback loops help validate earned tokens

---

This is not sweatshop labor — this is **sweat equity** in the future we’re building 🌱
