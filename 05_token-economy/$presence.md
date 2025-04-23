# 🕒 $Presence Token Overview

The **$Presence Token** is a custom ERC-20 utility token designed to reflect **time-weighted physical presence** at a regenerative land-based project. It introduces continuous decay to reward recent participation while maintaining a cryptographic memory of contribution.

This document outlines its function, implementation, and role in governance at Traditional Dream Factory.

---

## 🌿 Core Features
- **Non-transferrable**: Tokens cannot be transferred or approved — only minted or burned.
- **Continuous Decay**: Token balances decay automatically over time.
- **Time-Weighted Governance**: Recent presence holds more governance weight.
- **Role-Based Access**: Only authorized roles can mint and burn tokens.

---

## ⚙️ Technical Design
The $Presence token is built using an **Upgradeable Proxy** architecture with OpenZeppelin contracts.

```solidity
contract PresenceToken is ERC20Upgradeable, Ownable2StepUpgradeable {
    // Core functionality and state variables
}
```

### 🧮 Decay Mechanism
Applies exponential decay to balances:
```text
decayedAmount = initialAmount * (1 - decayRatePerDay)^numberOfDays
```
- **decayRatePerDay**: Configurable (e.g. 0.03% ≈ 10% per year)
- **lastDecayTimestamp**: Tracks when an account’s balance was last updated
- **lastDecayedBalance**: Used to compute updated balance before mint/burn

---

## 🎟 Minting
Citizens earn $Presence when they **stay on-site**:
```solidity
function mint(address account, uint256 amount, uint256 daysAgo) external
```
- `account`: Address of the Citizen
- `amount`: Tokens to mint
- `daysAgo`: How long ago the stay occurred (if retroactive)

---

## 🔥 Burning
Adjustments (e.g. canceled stays) use:
```solidity
function burn(address account, BurnData[] calldata burnDataArray) external returns (uint256 finalBalance)
```
- Removes tokens according to age and decay



## 🧰 Access Control
Minting and burning requires specific roles:
- `BOOKING_PLATFORM_ROLE`
- `BOOKING_MANAGER_ROLE`
- Contract Owner (e.g. DAO Multisig)

**Future goal:** Migrate $Sweat to a zero knowledge proof to allow apps to verify work done, but maintain privacy for user.



## 🗳 Governance Integration
$Presence balances are used to compute voting power:
- **More recent presence = higher voting weight**
- Combines with $TDF Tokens and $Sweat in the full weight formula

Example decay timeline (0.03% daily decay):
| Time Elapsed | Remaining Balance (of 1.00) |
|--------------|-------------------------------|
| 30 days      | ~0.99                         |
| 180 days     | ~0.95                         |
| 365 days     | ~0.90                         |

---

## ⚠️ Limitations & Considerations
- Transfers and approvals are disabled
- High-precision math used to prevent rounding errors
- Small tolerance (~100,000 wei) allowed during burns

---

## 🚀 Deployment
$Presence is deployed per project using an **Upgradeable Proxy pattern**, allowing:
- Future logic updates
- Data preservation
- Governance modularity

---

$Presence isn't just a number — it's a memory of your footsteps on the land 🌀
