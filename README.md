[![Claude Code Repos Index](https://img.shields.io/badge/Claude%20Code%20Repos-Index-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Code-Repos-Index)

# Claude Purchasing Assistant

![Claude Space](https://img.shields.io/badge/Claude-Space-purple?style=flat-square)
![Template](https://img.shields.io/badge/Template-green?style=flat-square)

A Claude Code workspace template for structured purchasing decisions. Get specific product recommendations optimized for value-for-money, with full customization for your location, preferences, and priorities.

## Use Case

This workspace helps with purchasing decisions by:

- Capturing your buying preferences once, then applying them consistently
- Evaluating products against your defined criteria
- Comparing local pricing against international RRP
- Researching manufacturer reputation and product reliability
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
- Set up your buyer profile (location, currency, preferences)
- Capture your current purchase requirements
- Create the folder structure for your decision

### 3. Provide Sources (Optional)

Drop files into `for-ai/`:
- Screenshots of products from websites
- PDFs with specifications
- Text files with links

Or let the assistant search for options.

### 4. Get Your Recommendation

```
/research    # Evaluate all candidates
/recommend   # Get the final recommendation
```

Results appear in `from-ai/`.

## Repository Structure

```
├── CLAUDE.md                      # Agent instructions
├── buyer-profile.md               # Your preferences (populated via /interview)
├── context/
│   └── interview-questions.md     # Question bank for onboarding
├── for-ai/                        # INPUT: Drop files here for evaluation
├── from-ai/                       # OUTPUT: Research & recommendations appear here
├── purchases/
│   ├── active/                    # Current purchase decisions
│   └── completed/                 # Archived decisions
└── .claude/commands/              # Slash commands
```

## Slash Commands

| Command | Purpose |
|---------|---------|
| `/interview` | Onboard and set up buyer profile + purchase requirements |
| `/research` | Evaluate all candidate products |
| `/recommend` | Generate final recommendation |
| `/compare` | Side-by-side comparison of specific products |

## Buyer Profile

The `/interview` command populates `buyer-profile.md` with:

- **Geographic context** - Country, currency, VAT status
- **Priority ranking** - What matters most (durability, price, features, etc.)
- **Quality preferences** - Consumer vs. professional, build quality importance
- **Brand attitudes** - Trusted/avoided manufacturers
- **Budget patterns** - Flexibility, premium tolerance, markup thresholds
- **Marketplace preferences** - Preferred/avoided vendors, international shipping stance

This profile is referenced for every purchase, ensuring consistent criteria.

## How It Works

### Interview Phase

The agent uses `context/interview-questions.md` as a reference for what to ask. Questions cover:
- Where you are and how local pricing compares to international
- What you prioritize in purchases
- Brands and vendors you trust or avoid
- Your budget flexibility

### Research Phase

Each product is evaluated on:
1. **Manufacturer reputation** - History, support quality, warranty track record
2. **Product quality** - Build quality, materials, durability
3. **Reviews** - Aggregated scores, common issues, longevity reports
4. **Value** - Local price vs. international RRP, markup calculation

### Disqualification

Products are filtered based on your profile thresholds:
- Poor manufacturer reputation
- Reviews below your threshold
- Markup exceeding your limit
- Known reliability issues
- No viable support in your region

### Output

You receive:
- A single, specific product recommendation
- Clear reasoning tied to your stated preferences
- Why alternatives were not chosen
- Purchase details and caveats

## Customization

### For Different Markets

The template adapts to any location. During `/interview`, you specify:
- Your country and currency
- Local VAT/tax rate
- Whether you're VAT exempt
- Acceptable markup over international pricing
- Vendor preferences

### For Different Priorities

The buyer profile supports any purchasing philosophy:
- Quality-first vs. budget-first
- Cutting-edge vs. proven technology
- Brand loyalty vs. best value
- Local support vs. price optimization
- Consumer vs. professional/industrial equipment

## Workflow Example

```
1. Fork template
2. /interview
   → "I'm in Germany, EUR, 19% VAT"
   → "I prioritize durability over features"
   → "I trust Bosch, avoid cheap brands"
   → "Budget flexible for quality"
   → "Looking for a cordless drill"
3. Drop screenshots into for-ai/cordless-drill/
4. /research
   → Agent evaluates all options
5. /recommend
   → "My recommendation is the Bosch GSR 18V-60..."
```

---

For more Claude Code projects, visit my [Claude Code Repos Index](https://github.com/danielrosehill/Claude-Code-Repos-Index).
