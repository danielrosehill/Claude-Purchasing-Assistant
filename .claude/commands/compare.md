# Side-by-Side Product Comparison

Generate a detailed comparison between specific products. Use this when the user wants to see products compared directly rather than going through the full research flow.

## Usage

The user may invoke this with specific products:
- "Compare the TP-Link AX3000 vs Netgear Nighthawk"
- "Compare these three monitors"
- Or simply run /compare and be prompted for products

## Before Comparing

1. Read `buyer-profile.md` for preferences (if configured)
2. Check `for-ai/` for any materials the user has provided

## Process

1. **Identify Products**
   If not specified, ask: "Which products would you like me to compare?"

2. **Gather Information**
   For each product, research:
   - Full specifications
   - Current pricing in user's market (from buyer profile)
   - International RRP for markup calculation
   - Review scores and consensus
   - Manufacturer reputation

3. **Generate Comparison**

## Output

Create `comparison.md` in `from-ai/` (or `from-ai/[purchase-name]/` if part of active purchase):

```markdown
# Comparison: [Product Category]

**Date**: [Date]
**Products Compared**: [Count]
**Location**: [From buyer profile, or "Not specified"]

## Quick Summary

| | [Product A] | [Product B] | [Product C] |
|---|---|---|---|
| **Price** | [Local] | [Local] | [Local] |
| **vs RRP** | +X% | +X% | +X% |
| **Reviews** | X.X/5 | X.X/5 | X.X/5 |
| **Best For** | [1-2 words] | [1-2 words] | [1-2 words] |

## Detailed Comparison

### Specifications

| Spec | [Product A] | [Product B] | [Product C] |
|------|-------------|-------------|-------------|
| [Spec 1] | [Value] | [Value] | [Value] |
| [Spec 2] | [Value] | [Value] | [Value] |
| [Spec 3] | [Value] | [Value] | [Value] |

### Build Quality

| Product | Assessment |
|---------|------------|
| [A] | [Assessment] |
| [B] | [Assessment] |

### Manufacturer Reputation

| Product | Manufacturer | Reputation |
|---------|--------------|------------|
| [A] | [Name] | [Assessment] |
| [B] | [Name] | [Assessment] |

### Value Analysis

| Product | Price | RRP | Markup | Value Rating |
|---------|-------|-----|--------|--------------|
| [A] | [Local] | $XXX | +X% | Good/Fair/Poor |
| [B] | [Local] | $XXX | +X% | Good/Fair/Poor |

## Winner by Category

- **Best Value**: [Product]
- **Best Build Quality**: [Product]
- **Best Features**: [Product]
- **Best for [User's Use Case]**: [Product]

## Bottom Line

[Clear statement of which product wins overall, referencing buyer profile priorities if configured]
```

## Guidelines

- Use tables for easy scanning
- Highlight meaningful differences, not just list specs
- Apply buyer profile weightings when declaring winners (if profile exists)
- Be opinionated—users want guidance, not just data
- Call out any products that should be immediately dismissed

## After Comparison

Ask: "Would you like me to proceed with a full recommendation, or do you need more information on any of these products?"