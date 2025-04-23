# ⏳ Token Decay & Voting Weight Formula

> **Status:** Draft  

The **decay function** is a core mechanic in the $Presence and $Sweat token systems. It gradually reduces a holder’s balance over time, ensuring that **recent contributions carry more governance weight** than past ones.

This mechanic helps align participation with recency, reinforcing TDF’s regenerative values.

> **Note:** As of now, TDF governance decisions are based **only on $TDF token holdings**. The $Presence and $Sweat contracts have been deployed, but are **not yet used** in Snapshot or DAO calculations. This formula represents the intended future model.

---

## 🗳 Voting Weight Formula
In the future TDF governance model, **voting power** is calculated using three components:
```text
Voting Power = 1 × $TDF + 1 × $Presence + 5 × $Sweat
```

Each element contributes to the total weight based on:
- **$TDF** → Token holdings (1 token = 1 vote)
- **$Presence** → Physical presence on-site (1 token = 1 vote, decaying daily)
- **$Sweat** → Verified labor/contribution (1 token = **5 votes**, also decaying)

---

## 📊 Why Use a Composite Formula?
This system ensures:
- Recent presence matters more than historical staking
- Voting power is earned through **staying**, **showing up**, and **contributing**
- A more regenerative and participatory governance process

---

## ⏳ Decay Dynamics
Both $Presence and $Sweat use a **0.03% daily decay rate**, which means:
- 10% decay per year (approx.)
- Recent tokens carry more weight than old ones

### Example:
If you receive 1 $Presence today:
- After 1 year: ~0.90 remains
- After 5 years: ~0.74 remains

If you earn 1 $Presence per year over 80 years:
- Your final voting weight from that would be **~9.64** (not 80)

---

## 🧮 Key Decay Components
### 📉 Decay Rate
- Defined as a **percentage of balance removed** over time.
- Example: A **0.03% daily decay rate** leads to ~10% annual reduction.

### ⏲ Decay Interval
- Applied **continuously**, calculated at every interaction or balance query.

### 🔁 Trigger Mechanism
- Decay is applied **dynamically** when:
  - Minting new tokens
  - Burning tokens
  - Querying balance (e.g. `balanceOf()`)

### 🔒 Exemptions
- Certain contracts (e.g., treasury, burn address) can be excluded from decay
- Controlled via role-based access permissions

---

## 🛠 Sample Solidity Implementation
```solidity
function applyDecay() external {
    uint256 decayRate = 1; // Example: 1% decay
    uint256 totalSupply = totalSupply();
    for (uint256 i = 0; i < holders.length; i++) {
        address holder = holders[i];
        uint256 balance = balanceOf(holder);
        uint256 decayAmount = balance.mul(decayRate).div(100);
        _burn(holder, decayAmount);
    }
    emit DecayApplied(totalSupply, decayRate);
}
```

---

## 📉 Impact of Presence & Sweat Decay
- Encourages ongoing contribution
- Prevents “stacking” of influence by inactive participants
- Allows new players to gain meaningful power quickly through action

---

## 📈 Benefits
- Time-weighted governance
- Discourages token hoarding
- Encourages continuous participation
- Aligns voting power with active engagement

---

## 📦 Applied To:
- **$Presence** — representing physical time on land
- **$Sweat** — representing verified work contribution

These decay mechanisms reinforce the values of **action, presence, and care** over time 🌀

---

## 🧠 What’s Coming Next?
- Integration of $Presence and $Sweat into **Snapshot**
- DAO vote to formally activate this formula
- Development of public dashboards and audit tools

---

## 📚 Learn More
- [$Presence Token](presence_token.md)
- [$Sweat Token](sweat_token.md)
- [$TDF Token Basics](token_basics.md)
