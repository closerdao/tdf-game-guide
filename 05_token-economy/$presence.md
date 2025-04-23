# 🕒 $PRESENCE TOKEN

**ATTENDANCE RECORD** The $Presence token is your digital record in the TDF community—tracking your physical time spent on the land.

> *"Your presence matters. Every day on the land contributes to your community standing."*

## 🧙‍♂️ TOKEN PROPERTIES

$Presence is a special token with unique characteristics:

- **Non-transferable** - Cannot be transferred or traded to other members
- **Time-Weighted** - Recent presence carries more weight than distant past
- **Decaying** - Gradually decreases over time, encouraging continued engagement
- **Verifiable** - Cryptographically secured proof of your physical presence

## ⚙️ TECHNICAL DETAILS

$Presence is an ERC-20 token with custom modifications:

```solidity
contract PresenceToken is ERC20Upgradeable, Ownable2StepUpgradeable {
    // Core functionality and state variables
}
```

### 🧮 DECAY FORMULA

Your presence decreases through exponential decay:

```
decayedAmount = initialAmount * (1 - decayRatePerDay)^numberOfDays
```

| Time Elapsed | Remaining Value (0.03% daily decay) |
|--------------|-------------------------------------|
| 30 days      | ~99% of original value              |
| 180 days     | ~95% of original value              |
| 365 days     | ~90% of original value              |

## 🔄 HOW IT WORKS

### Earning $Presence
- **Physical Stay** - Automatically created for each day on-site
- **Retroactive Recording** - Can be awarded for past stays (with verification)

### Using $Presence
- **Governance Weight** - Contributes to your voting power (1× multiplier)
- **Community Recognition** - Visible indicator of your time investment
- **Participation Requirements** - Some activities require minimum $Presence

## 🛡️ ACCESS CONTROL

Only specific roles can create or remove $Presence:
- `BOOKING_PLATFORM_ROLE` - Automated systems tracking stays
- `BOOKING_MANAGER_ROLE` - Human verification of special cases
- `CONTRACT_OWNER` - Ultimate oversight (DAO multisig)

## 🔮 FUTURE DEVELOPMENT

- **Enhanced Privacy** - Better privacy while maintaining verifiability
- **Cross-Project Recognition** - Interoperability with other regenerative communities
- **Enhanced Visualization** - Better ways to see your presence impact

---

*"Your presence isn't just counted—it's felt throughout the community."*
