# Claude Purchasing Assistant

![Claude Space](https://img.shields.io/badge/Claude-Space-purple?style=flat-square)
![Template](https://img.shields.io/badge/Template-green?style=flat-square)

A Claude Code workspace template for structured purchasing decisions. Get specific product recommendations optimized for value-for-money, particularly useful in markets where pricing varies significantly from international RRP.

## Use Case

This workspace helps with purchasing decisions by:

- Evaluating products against your defined criteria
- Comparing options across vendors and geographies
- Researching manufacturer reputation and product reliability
- Calculating value-for-money considering local pricing vs. international RRP
- Providing specific, confident recommendations (not just options)

## Getting Started

### 1. Clone or Fork This Template

```bash
gh repo clone danielrosehill/Claude-Purchasing-Assistant my-purchases
cd my-purchases
```

### 2. Run the Interview

Start Claude Code and run:

```
/interview
```

This will:
- Create your buyer profile (one-time setup)
- Capture your current purchase requirements
- Set up a folder for the purchase decision

### 3. Provide Sources (Optional)

Add screenshots, PDFs, or links to the `active-purchases/[purchase]/sources/` folder. Or let the assistant search for options.

### 4. Get Your Recommendation

```
/research    # Evaluate all candidates
/recommend   # Get the final recommendation
```

## Repository Structure

```
├── CLAUDE.md              # Agent instructions
├── buyer-profile.md       # Your reusable preferences
├── active-purchases/      # Current decisions in progress
│   └── [purchase-name]/
│       ├── requirements.md
│       ├── sources/
│       ├── research.md
│       └── recommendation.md
├── completed-purchases/   # Archive
└── .claude/commands/      # Slash commands
```

## Slash Commands

| Command | Purpose |
|---------|---------|
| `/interview` | Onboard and capture purchase requirements |
| `/research` | Evaluate all candidate products |
| `/recommend` | Generate final recommendation |
| `/compare` | Side-by-side comparison of specific products |

## Buyer Profile

The `buyer-profile.md` captures standing preferences:

- Quality and durability priorities
- Manufacturer reputation requirements
- Budget patterns and flexibility
- Geographic context (local pricing, VAT, vendors)
- Feature preferences (conservative vs. cutting-edge)

This profile is referenced for every purchase, ensuring consistent criteria.

## How Recommendations Work

### Research Phase

Each product is evaluated on:

1. **Manufacturer reputation** - Company history, support quality, warranty track record
2. **Product quality** - Build quality, materials, durability
3. **Reviews** - Aggregated scores, common issues, longevity reports
4. **Value** - Price vs. international RRP, total cost of ownership

### Disqualification Criteria

Products are immediately disqualified if they have:
- Poor manufacturer reputation
- Reviews below 3.5/5 aggregate
- Markup exceeding 50% over RRP (without justification)
- Known reliability issues
- No viable local support

### Output

You receive:
- A single, specific product recommendation
- Clear reasoning tied to your requirements
- Why alternatives were not chosen
- Purchase details and caveats

## Geographic Context

This template is configured for Israel but easily adapts:

- VAT considerations (17% in Israel)
- Local vs. international pricing comparison
- Import duty and shipping costs
- Local warranty/support requirements
- Vendor preferences and avoidances

## Customization

### For Different Markets

Edit `buyer-profile.md` to adjust:
- Currency and VAT rate
- Acceptable markup thresholds
- Local vendor preferences
- Support requirements

### For Different Priorities

The buyer profile supports different purchasing philosophies:
- Quality-first vs. budget-first
- Cutting-edge vs. proven technology
- Brand loyalty vs. best value
- Local support vs. price optimization
