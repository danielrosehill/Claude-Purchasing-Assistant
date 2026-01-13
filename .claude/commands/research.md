# Research Phase

Begin the research phase for an active purchase. This command evaluates all candidate products and documents findings.

## Pre-Research Checklist

1. Read `buyer-profile.md` to understand standing preferences
2. Identify the active purchase folder in `active-purchases/`
3. Read `requirements.md` for specific needs
4. Inventory any sources provided in the `sources/` folder

## Research Process

### For Each Candidate Product

1. **Identify the product**
   - Exact model name/number
   - Manufacturer
   - Price and vendor

2. **Manufacturer Assessment**
   - Company reputation and history
   - Quality track record
   - Support/warranty reputation
   - Presence in Israeli market

3. **Product Assessment**
   - Build quality and materials
   - Feature match to requirements
   - Review aggregation (multiple sources)
   - Known issues or failure modes
   - Longevity/durability reports

4. **Value Assessment**
   - Price in ILS
   - Equivalent USD/EUR price
   - Comparison to international RRP
   - Calculate markup percentage
   - Factor in shipping/import costs if applicable

5. **Verdict**
   - CONSIDER: Meets criteria, worthy of final comparison
   - DISQUALIFIED: Fails on one or more criteria (document which)

### Applying Disqualification Criteria

Immediately disqualify products if they have:
- Poor manufacturer reputation
- Review scores below 3.5/5 aggregate
- Markup exceeding 50% over international RRP (without clear justification)
- Known reliability issues with the specific model
- No viable warranty/support path in Israel

### Additional Discovery (if permitted)

If the user has allowed expanded search:
- Search for alternatives not in the provided sources
- Look for industrial/professional alternatives to consumer products
- Check for current sales or promotions
- Consider refurbished or open-box options if appropriate

## Output

Create `research.md` in the active purchase folder with:

```markdown
# [Purchase Name] Research

**Date**: [Date]
**Budget**: [Budget]
**Requirements Summary**: [Brief summary]

## Candidates Evaluated

### [Product 1 Name]
- **Price**: ₪X,XXX ($XXX USD)
- **RRP**: $XXX (markup: +X%)
- **Vendor**: [Name]
- **Manufacturer**: [Name] - [1-sentence reputation]
- **Reviews**: X.X/5 from [sources]
- **Meets Requirements**: Yes/Partial/No
- **Build Quality**: [Assessment]
- **Key Strengths**:
  - Point 1
  - Point 2
- **Concerns**:
  - Point 1
  - Point 2
- **Verdict**: CONSIDER / DISQUALIFIED ([reason])

[Repeat for each product]

## Summary

- **Total Evaluated**: X products
- **Considered**: X products
- **Disqualified**: X products
- **Ready for Recommendation**: Yes/No

## Notes

[Any additional observations, patterns noticed, or factors to consider]
```

## After Research

Inform the user:
- How many products were evaluated
- How many passed initial screening
- Whether you need more information
- Readiness to proceed to recommendation phase

Prompt: "Research complete. I've evaluated X products, with Y making it through to consideration. Would you like me to proceed with my recommendation, or would you like to review the research first?"
