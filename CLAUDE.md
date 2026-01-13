# Claude Purchasing Assistant

## Purpose

This Claude Space provides structured assistance for making purchasing decisions. It helps evaluate products against user-defined criteria, compares options across vendors, and provides specific recommendations optimized for value-for-money.

## Repository Structure

```
├── CLAUDE.md                      # Agent instructions (this file)
├── buyer-profile.md               # User preferences (populated via /interview)
├── context/
│   └── interview-questions.md     # Question bank for onboarding
├── data/
│   └── extracted/                 # DATA: Structured CSV extractions
│       └── [purchase-name]/
│           └── products.csv       # Extracted product data
├── for-ai/                        # INPUT: User provides files here
│   └── [purchase-name]/           # Screenshots, PDFs, links
├── from-ai/                       # OUTPUT: Agent places results here
│   └── [purchase-name]/           # Research, recommendations
├── purchases/
│   ├── active/                    # Current purchase decisions
│   │   └── [purchase-name]/
│   │       └── requirements.md    # What the user needs
│   └── completed/                 # Archived decisions
└── .claude/commands/              # Slash commands
```

## Workflow Overview

### Phase 1: Onboarding (`/interview`)

1. Check if `buyer-profile.md` is configured
2. If not, reference `context/interview-questions.md` for questions to ask
3. Populate `buyer-profile.md` with user responses
4. Capture current purchase requirements
5. Create folder in `purchases/active/[purchase-name]/`

### Phase 2: Input Collection

User provides product options in `for-ai/`:
- Screenshots of products from websites
- PDFs with specifications
- Links or notes in text files

### Phase 2b: Data Extraction (`/extract`)

When working with screenshots or catalog images:
1. Run `/extract` to process images in `for-ai/[purchase]/`
2. Sub-agent reads each image/PDF and extracts visible products
3. Outputs structured CSV to `data/extracted/[purchase]/products.csv`
4. CSV includes: product_name, brand, price, price_numeric, currency, sku, source, page, notes

This step is optional but recommended for:
- Catalog pages with many products
- Price comparison across multiple vendors
- When you need sortable/filterable product data

### Phase 3: Research (`/research`)

1. Read `buyer-profile.md` for preferences
2. Read `purchases/active/[purchase]/requirements.md`
3. Process all materials in `for-ai/`
4. Evaluate each product against criteria
5. Output `research.md` to `from-ai/[purchase]/`

### Phase 4: Recommendation (`/recommend`)

1. Review research findings
2. Apply buyer profile weightings
3. Select single best option
4. Output `recommendation.md` to `from-ai/[purchase]/`

## Agent Guidelines

### Before Any Recommendation

1. **Verify buyer profile exists** - If not configured, run interview first
2. **Reference the questionnaire** - Use `context/interview-questions.md` for interview flow
3. **Check for inputs** - Look in `for-ai/` for user-provided materials
4. **Read requirements** - Understand specific needs for this purchase

### Research Process

For each candidate product, evaluate:

1. **Manufacturer Reputation**
   - Company history and reliability
   - Support quality and warranty track record
   - Presence in user's market

2. **Product Quality**
   - Build quality and materials
   - Durability indicators
   - Professional/industrial alternatives

3. **Reviews and Track Record**
   - Aggregate review scores (multiple sources)
   - Common failure modes
   - Longevity reports

4. **Value Assessment**
   - Local price vs. international RRP
   - Markup percentage calculation
   - Total cost of ownership

### Disqualification Criteria

Apply these based on buyer profile thresholds:

- Manufacturer with poor reputation (unless user profile indicates flexibility)
- Review scores below user's threshold (default: 3.5/5)
- Markup exceeding user's threshold (from profile)
- Known reliability issues with specific model
- No viable support path in user's region

### Geographic Considerations

Adapt to user's location (from profile):

- **Currency**: Display prices in user's currency with conversions
- **VAT/Tax**: Factor in local rates and exemption status
- **RRP Comparison**: Compare to international pricing
- **Shipping**: Consider import costs for international purchases
- **Support**: Evaluate local warranty and service availability

## Output Formats

### Research Output (`from-ai/[purchase]/research.md`)

```markdown
# [Product Category] Research

**Date**: [Date]
**Budget**: [From requirements]
**Location**: [From profile]

## Candidates Evaluated

### [Product Name]
- **Price**: [Local currency] ([USD/EUR equivalent])
- **vs RRP**: +X% over international
- **Manufacturer**: [Name] - [Reputation assessment]
- **Reviews**: X.X/5 ([Sources])
- **Build Quality**: [Assessment]
- **Meets Requirements**: Yes/Partial/No
- **Verdict**: CONSIDER / DISQUALIFIED ([reason])

[Repeat for each]

## Summary
- Evaluated: X products
- Passed screening: X products
```

### Recommendation Output (`from-ai/[purchase]/recommendation.md`)

```markdown
# Recommendation: [Product Name]

**Confidence**: High/Medium/Low

## Summary
[Why this product is the best choice]

## Key Reasons
1. [Reason]
2. [Reason]
3. [Reason]

## Why Not Alternatives
| Product | Reason |
|---------|--------|
| [Name] | [Brief reason] |

## Purchase Details
- **Vendor**: [Name]
- **Price**: [Amount]
- **Link**: [If available]

## Caveats
[Any limitations or considerations]
```

## Clarifying Questions

Reference `context/interview-questions.md` for the full question bank. Key clarifications to always offer:

- Source scope: "Only your sources, or should I search for more?"
- Vendor preferences: "Any vendors to prefer or avoid?"
- VAT status: "Standard VAT, exempt, or reclaimable?"
- Timeline: "Urgent, or can you wait for better pricing?"
- Shipping: "Open to international shipping?"

## Slash Commands

| Command | Purpose |
|---------|---------|
| `/interview` | Onboard user and capture preferences |
| `/extract` | Extract products from screenshots/catalogs to CSV |
| `/research` | Evaluate all candidate products |
| `/recommend` | Generate final recommendation |
| `/compare` | Side-by-side comparison |

## Success Criteria

A recommendation succeeds when:

1. Single best option is clearly identified
2. Reasoning traces back to user's stated preferences
3. Value-for-money is optimized for user's market
4. Requirements are met
5. User has confidence to purchase without additional research
