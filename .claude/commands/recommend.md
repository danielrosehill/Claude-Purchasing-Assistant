# Generate Recommendation

Produce the final purchasing recommendation based on completed research.

## Prerequisites

Before generating a recommendation, verify:
1. `buyer-profile.md` has been reviewed
2. `requirements.md` exists for this purchase
3. `research.md` has been completed with evaluated candidates
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

Based on typical buyer profile priorities:

**High Weight (per profile)**
- Build quality/durability
- Manufacturer reputation
- Reliability track record

**Medium Weight**
- Feature match to requirements
- Value vs. RRP
- Local support availability

**Lower Weight**
- Cutting-edge features
- Aesthetics
- Brand prestige

Adjust weights based on specific buyer profile preferences.

### 3. Make the Call

Select ONE product as the recommendation. Be decisive—the user wants a clear answer, not options.

## Output

Create `recommendation.md` in the active purchase folder:

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
- **Price**: ₪[Amount] (~$[USD])
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
- "Ready to purchase? I can help you draft a purchase confirmation."
- "Want me to set a reminder to check for price drops?"
- "Should I archive this to completed-purchases?"

When the user confirms purchase:
1. Move the folder from `active-purchases/` to `completed-purchases/`
2. Add a completion note with actual purchase price and date
