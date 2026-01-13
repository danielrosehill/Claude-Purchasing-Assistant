# Generate Recommendation

Produce the final purchasing recommendation based on completed research.

## Prerequisites

Before generating a recommendation, verify:
1. `buyer-profile.md` has been reviewed
2. `purchases/active/[purchase]/requirements.md` exists
3. `from-ai/[purchase]/research.md` has been completed
4. At least one product has CONSIDER status

If prerequisites aren't met, inform the user what's missing and offer to help complete those steps.

## Recommendation Process

### 1. Review Considered Products

From the research, examine all products marked CONSIDER:
- Re-evaluate against buyer profile priorities
- Compare value-for-money across candidates
- Consider total cost of ownership
- Factor in intangibles (support quality, upgrade path, ecosystem)

### 2. Apply Weighted Criteria

Reference the priority order from `buyer-profile.md`. Default weights if not specified:

**Typically High Weight**
- Build quality/durability
- Manufacturer reputation
- Reliability track record

**Typically Medium Weight**
- Feature match to requirements
- Value vs. RRP
- Local support availability

**Typically Lower Weight**
- Cutting-edge features
- Aesthetics
- Brand prestige

Adjust based on the specific buyer profile priorities.

### 3. Make the Call

Select ONE product as the recommendation. Be decisive—the user wants a clear answer, not options.

## Output

Create `recommendation.md` in `from-ai/[purchase-name]/`:

```markdown
# Recommendation: [Exact Product Name]

**Purchase**: [What this is for]
**Date**: [Date]
**Confidence**: High/Medium/Low

## The Recommendation

[2-3 sentence summary of why this specific product is the best choice for this user's needs, budget, and preferences]

## Key Reasons

1. **[Reason Category]**: [Explanation]
2. **[Reason Category]**: [Explanation]
3. **[Reason Category]**: [Explanation]

## Why Not the Alternatives

| Product | Why Not |
|---------|---------|
| [Name] | [1-sentence reason] |
| [Name] | [1-sentence reason] |

## Purchase Details

- **Product**: [Full product name/model]
- **Recommended Vendor**: [Name]
- **Price**: [Local currency] (~$[USD])
- **Link**: [URL if available]

## Purchase Notes

[Any specific advice for purchasing—timing, negotiation, accessories, configuration options]

## Caveats

[Any limitations, compromises, or things the user should be aware of]

## Post-Purchase

[Optional: Setup tips, accessories to consider, what to check on arrival]
```

## Communication Style

Be confident and clear:
- "My recommendation is X" not "You might consider X"
- "This is the best value" not "This could be a good option"
- Own the recommendation—that's what the user is here for

If confidence is low, explain why but still make the call.

## After Recommendation

Offer next steps:
- "Ready to purchase? Let me know when you've ordered."
- "Want me to search for better pricing or wait for sales?"
- "Should I archive this to completed purchases?"

When the user confirms purchase:
1. Move folder from `purchases/active/` to `purchases/completed/`
2. Add a completion note with actual purchase price and date