# Buyer Profile

*This file is populated by running `/interview`. It captures your standing purchasing preferences that apply across all decisions.*

**Status**: Not yet configured

**Email**: [Not set — for receiving PDF reports via Resend]

---

## Foundational Rules

*These rules apply to all purchasing decisions regardless of user preferences. They represent baseline quality and safety standards.*

### Automatic Disqualification Criteria

The following conditions result in automatic disqualification or strong warnings, even if a product otherwise meets requirements:

#### Manufacturer Red Flags
- **Severe reputation issues**: Manufacturers with documented patterns of fraud, safety recalls, or systemic quality failures
- **Defunct or unreachable**: Companies that have ceased operations or have no customer support presence
- **Legal/regulatory problems**: Ongoing lawsuits for product liability, regulatory bans, or import restrictions

#### Product Red Flags
- **Critical safety issues**: Products with documented safety hazards, fire risks, or injury reports
- **Aggregate rating below 2.5/5**: Products with overwhelmingly negative reviews across multiple platforms
- **Known defect patterns**: Products with widespread reports of the same failure mode (without manufacturer acknowledgment/fix)
- **Counterfeit concerns**: Products frequently counterfeited where authenticity cannot be verified

#### Vendor Red Flags
- **Grey market / unauthorized**: Sellers with no manufacturer authorization selling at suspiciously low prices
- **No return policy**: Vendors offering no returns on high-value items
- **Fraud reports**: Vendors with documented patterns of non-delivery or bait-and-switch

### Deprioritization Criteria

These don't automatically disqualify but result in lower ranking:

- **Review scores 2.5-3.5/5**: Requires explicit user acknowledgment
- **Manufacturer with mixed reputation**: Include warnings in recommendation
- **Limited warranty or support**: Note the risk in assessment
- **New/unproven products**: Flag lack of track record (<6 months on market, <50 reviews)

### Sub-Agent Instructions

When spawning sub-agents for tasks like manufacturer research, product extraction, or price lookups:

1. **Always check manufacturer reputation** before detailed product analysis
2. **Cross-reference reviews** across multiple sources (don't rely on single platform)
3. **Flag anomalies** - prices significantly below market suggest counterfeits or grey market
4. **Convert currencies** using current exchange rates (via MCP if available)
5. **Document sources** - include where data was obtained for verification
6. **Apply these rules first** before user-specific preferences

### Override Conditions

Users can override these defaults by explicitly stating in their buyer profile:
- "I accept higher risk for better prices"
- "I'm willing to consider products with mixed reviews"
- "I prefer grey market pricing"

Without explicit override, treat foundational rules as hard constraints.

---

## General Philosophy

**Priority Order** (1 = highest):
1. [Not set]
2. [Not set]
3. [Not set]
4. [Not set]
5. [Not set]

**Risk Tolerance**: [Not set]

---

## Quality Preferences

### Build Quality Priority
[Not set]

### Product Style Preference
[Not set - e.g., consumer, prosumer, professional/industrial]

---

## Brand & Manufacturer Criteria

### Trusted Manufacturers
[None specified]

### Avoided Manufacturers
[None specified]

### General Brand Requirements
[Not set]

---

## Budget Patterns

**Budget Style**: [Not set]

**Premium Tolerance**: [Not set - e.g., willing to pay X% more for quality]

**Markup Threshold**: [Not set - maximum acceptable markup over international RRP]

---

## Geographic Context

**Country**: [Not set]

**Currency**: [Not set]

**VAT/Tax Rate**: [Not set]

**VAT Status**: [Not set - e.g., standard, exempt, reclaimable]

### Vendor Preferences

**Preferred Vendors**:
[None specified]

**Avoided Vendors**:
[None specified]

**International Shipping**: [Not set - e.g., acceptable, preferred, avoid]

### Support Requirements
[Not set]

---

## Feature Preferences

**Technology Stance**: [Not set - e.g., cutting-edge, proven, conservative]

**Complexity Preference**: [Not set]

---

## Marketplace Preferences

**Preferred Marketplaces**:
[None specified]

**Avoided Marketplaces**:
[None specified]

**Notes**:
[None]

---

## Additional Notes

[None]

---

*Last Updated*: Never
*Created via*: `/interview`
