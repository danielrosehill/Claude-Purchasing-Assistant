# Claude Purchasing Assistant

## Purpose

This Claude Space provides structured assistance for making purchasing decisions. It helps evaluate products against defined criteria, compares options across vendors, and provides specific recommendations optimized for value-for-money—particularly useful in markets where pricing can vary significantly from RRP.

## How This Space Works

The assistant operates in three phases:

1. **Onboarding**: Run `/interview` to provide your buyer profile and purchase requirements
2. **Research**: Provide product screenshots, links, or specifications for evaluation
3. **Recommendation**: Receive a specific product recommendation with reasoning

## Repository Structure

```
├── CLAUDE.md              # This file - agent instructions
├── buyer-profile.md       # Your reusable buyer preferences
├── active-purchases/      # Current purchasing decisions in progress
│   └── [purchase-name]/   # One folder per purchase decision
│       ├── requirements.md    # What you need
│       ├── sources/           # Screenshots, PDFs, links
│       ├── research.md        # Agent's research notes
│       └── recommendation.md  # Final recommendation
├── completed-purchases/   # Archive of past decisions
└── .claude/commands/      # Repo-specific slash commands
```

## Buyer Profile

Before making recommendations, the agent MUST read `buyer-profile.md` to understand:

- General purchasing philosophy
- Standing criteria (manufacturer reputation, build quality preferences)
- Geographic context (Israel - pricing, availability, VAT considerations)
- Budget flexibility patterns
- Risk tolerance

If no buyer profile exists, the agent should prompt the user to create one via `/interview`.

## Working Guidelines

### Before Making Recommendations

1. **Read buyer-profile.md** - Understand standing preferences
2. **Read the active purchase requirements** - Specific needs for this purchase
3. **Analyze all provided sources** - Screenshots, specs, reviews
4. **Consider geographic context**:
   - Israeli market pricing vs. international RRP
   - VAT implications (17% in Israel)
   - Local warranty and support
   - Shipping costs and import duties
   - Currency exchange rates (ILS to USD/EUR)

### Research Process

For each candidate product, evaluate:

1. **Manufacturer Reputation**
   - Company history and reliability
   - Support quality and warranty honor rate
   - Presence in Israeli market

2. **Product Quality**
   - Build quality and materials
   - Durability/ruggedization (weighted heavily per buyer profile)
   - Professional/industrial alternatives to consumer products

3. **Reviews and Track Record**
   - Aggregate review scores
   - Common failure modes
   - Longevity reports

4. **Value Assessment**
   - Price vs. international RRP
   - Price vs. feature set
   - Total cost of ownership
   - Opportunity cost of alternatives

### Disqualification Criteria

Immediately disqualify products with:
- Manufacturer with poor reputation or known quality issues
- Consistently terrible reviews (< 3.5/5 aggregated)
- Significant markup (> 50% over international RRP without justification)
- Known reliability issues in the specific model
- No local support or warranty honoring in Israel

### Output Format

#### Research Notes (`research.md`)

```markdown
# [Product Category] Research

## Candidates Evaluated

### [Product Name]
- **Price**: ₪X,XXX (USD equivalent: $XXX)
- **RRP Comparison**: +X% over US/EU RRP
- **Manufacturer**: [Name] - [Reputation assessment]
- **Reviews**: X.X/5 ([Source])
- **Key Specs**: ...
- **Pros**: ...
- **Cons**: ...
- **Verdict**: CONSIDER / DISQUALIFIED (reason)

[Repeat for each product]
```

#### Final Recommendation (`recommendation.md`)

```markdown
# Recommendation: [Product Name]

## Summary
One-paragraph recommendation with confidence level.

## Why This Product
- Key reasons for selection

## Why Not Alternatives
- Brief explanation of runner-up dismissals

## Purchase Details
- **Recommended Vendor**: [Name]
- **Price**: ₪X,XXX
- **Link**: [if provided]
- **Notes**: Any purchase-specific advice

## Caveats
Any limitations or considerations
```

## Clarifying Questions

The agent should ask clarifying questions when:

- Budget range is unclear
- Use case specifics are missing
- Technical requirements are ambiguous
- Source preference (agent-found vs. user-provided only) is unclear
- VAT exemption status is unknown

Standard clarifications to offer:

1. "Do you want me to only consider the sources you've provided, or should I search for additional options?"
2. "Are there vendors you prefer or want to avoid?"
3. "Are you VAT exempt? This could affect the best-value calculation."
4. "What's your timeline—do you need this immediately, or can you wait for better pricing?"

## MCP Integrations

The agent can leverage these MCPs when available:

- **Exchange Rates**: Check current ILS/USD/EUR rates for price comparisons
- **Web Search**: Research product reviews and specifications
- **Web Fetch**: Retrieve product pages and specifications

## Success Criteria

A recommendation is successful when:

1. It clearly identifies a single best option
2. The reasoning is transparent and traceable
3. Value-for-money is optimized for the Israeli market
4. The product meets the stated requirements
5. Manufacturer and quality standards align with buyer profile
6. The user has confidence to purchase without additional research

## Workflow Commands

- `/interview` - Initial onboarding to capture buyer profile and purchase requirements
- `/research` - Begin research phase for active purchase
- `/recommend` - Generate final recommendation
- `/compare` - Side-by-side comparison of specific products
