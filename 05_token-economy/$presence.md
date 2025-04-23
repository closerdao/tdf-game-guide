# 🕒 $PRESENCE POWER

**TRACK YOUR FOOTSTEPS!** The $Presence token is your digital footprint in the game world—a magical record of your physical journey through time and space.

> *"Your presence is power. Every moment on the land leaves a trace in the digital realm."*

## 🧙‍♂️ MAGICAL PROPERTIES

$Presence is a special token with unique enchantments:

- **Soulbound** - Cannot be transferred or traded to other players
- **Time-Weighted** - Recent presence carries more power than distant past
- **Decaying** - Gradually fades over time, encouraging continued engagement
- **Verifiable** - Cryptographically secured proof of your physical presence

## ⚙️ TECHNICAL ESSENCE

$Presence is an ERC-20 token with custom modifications:

```solidity
contract PresenceToken is ERC20Upgradeable, Ownable2StepUpgradeable {
    // Core functionality and state variables
}
```

### 🧮 DECAY FORMULA

Your presence fades through exponential decay:

```
decayedAmount = initialAmount * (1 - decayRatePerDay)^numberOfDays
```

| Time Elapsed | Remaining Power (0.03% daily decay) |
|--------------|-------------------------------------|
| 30 days      | ~99% of original strength           |
| 180 days     | ~95% of original strength           |
| 365 days     | ~90% of original strength           |

## 🎮 GAMEPLAY MECHANICS

### Earning $Presence
- **Physical Stay** - Automatically minted for each day on-site
- **Retroactive Minting** - Can be awarded for past stays (with verification)

### Using $Presence
- **Governance Weight** - Amplifies your voting power (5× multiplier)
- **Community Recognition** - Visible indicator of your time investment
- **Quest Requirements** - Some quests require minimum $Presence

## 🛡️ ACCESS CONTROL

Only specific roles can mint or burn $Presence:
- `BOOKING_PLATFORM_ROLE` - Automated systems tracking stays
- `BOOKING_MANAGER_ROLE` - Human verification of special cases
- `CONTRACT_OWNER` - Ultimate oversight (DAO multisig)

## 🔮 FUTURE EVOLUTION

- **Zero-Knowledge Proofs** - Enhanced privacy while maintaining verifiability
- **Cross-Project Recognition** - Interoperability with other regenerative communities
- **Enhanced Visualization** - Better ways to see your presence impact

---

*"Your presence isn't just counted—it's felt throughout the ecosystem."* 🌀
