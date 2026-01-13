# Interview Questions Reference

*This file defines the questions the agent should ask during `/interview` to populate the buyer profile and purchase requirements.*

---

## Part 1: Buyer Profile Questions

These questions establish standing preferences that apply across all purchases. Only ask these if `buyer-profile.md` shows "Status: Not yet configured" or if the user explicitly wants to update their profile.

### Geographic Context

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| What country are you located in? | Determines market, currency, pricing context | USA, UK, Israel, Germany, Australia |
| What is your local currency? | For price displays and conversions | USD, GBP, ILS, EUR, AUD |
| What is the VAT/sales tax rate in your area? | For true cost calculations | 0%, 7%, 17%, 20%, varies by state |
| Are you VAT exempt or able to reclaim VAT? | Affects best-value calculations | Standard, exempt, business (reclaimable) |

### Purchasing Philosophy

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| What matters most when you make purchases? Rank these: durability, features, price, brand reputation, aesthetics | Establishes priority weighting | "Durability first, then reputation, then price" |
| How would you describe your risk tolerance with new or lesser-known brands? | Determines openness to alternatives | Low (stick to known brands), Medium, High (will try anything) |
| Do you prefer consumer, prosumer, or professional/industrial equipment? | Product tier preference | Consumer, prosumer, professional, "whatever works" |

### Quality & Build Preferences

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| How important is build quality and durability to you? | Weight for recommendations | Critical, Important, Moderate, Not important |
| Do you prefer rugged/industrial designs over sleek consumer designs? | Style preference | Yes strongly, Sometimes, No preference, Prefer sleek |
| Are there specific materials you prefer or avoid? | Material preferences | Prefer metal, avoid cheap plastic, no preference |

### Brand Attitudes

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Are there manufacturers you particularly trust? | Positive brand list | Apple, Lenovo, Sony, "no strong preferences" |
| Are there manufacturers you avoid or distrust? | Negative brand list | [Brand X] - bad experience, cheap brands generally |
| How important is the manufacturer's reputation and history? | Brand weight | Very important, Somewhat, Don't care |
| How important is local warranty and support? | Support requirements | Essential, Preferred, Will accept international |

### Budget Patterns

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Do you typically set hard budgets or are you flexible for the right product? | Budget rigidity | Hard limit, Flexible +20%, Very flexible |
| How much premium would you pay for better quality/durability? | Premium tolerance | 0%, up to 25%, up to 50%, price is secondary |
| What's the maximum markup over international RRP you'd accept? | Markup threshold | 20%, 30%, 50%, depends on product |

### Feature Preferences

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Do you prefer cutting-edge features or proven, reliable technology? | Technology stance | Cutting-edge, Balanced, Proven only |
| Do you prefer simple products or feature-rich ones? | Complexity preference | Simple and reliable, Full-featured, Depends |

### Marketplace & Vendor Preferences

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Are there online marketplaces you prefer to buy from? | Preferred sources | Amazon, local retailers, manufacturer direct |
| Are there marketplaces or vendors you avoid? | Avoided sources | [Marketplace X] - bad experience, grey market sellers |
| Are you comfortable with international shipping and imports? | Import tolerance | Yes, Only if significant savings, No |
| Have you had particularly good or bad experiences with specific vendors? | Vendor history | [Vendor] was great/terrible because... |

---

## Part 2: Purchase-Specific Questions

These questions are asked for each new purchase decision.

### Basic Requirements

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| What are you looking to buy? | Product category | 5G router, laptop, office chair, headphones |
| What is the primary purpose/use case? | Context for features | Home office, gaming, travel, professional work |
| What specific features or specs are must-haves? | Hard requirements | WiFi 6, 16GB RAM, ergonomic, noise-canceling |
| What features would be nice to have but aren't essential? | Soft requirements | USB-C, wireless, specific color |
| What's your budget range? | Price constraint | $200-300, up to $500, flexible |

### Sources & Research Scope

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Have you already found some options you'd like me to evaluate? | Starting candidates | Yes - [links/screenshots], No - please search |
| Should I only consider sources you provide, or search for additional options? | Research scope | Only mine, You can expand, Please find options |
| Are there specific websites or vendors you want me to check? | Targeted search | Check [store], look at [brand]'s website |

### Timeline & Urgency

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| How soon do you need this? | Urgency level | ASAP, Within a week, No rush - can wait for deals |
| Would you wait for a sale or better price if one is likely? | Price patience | Yes definitely, Maybe, No - need it now |

### Context & History

| Question | Purpose | Example Answers |
|----------|---------|-----------------|
| Have you owned similar products before? What was your experience? | Past context | Yes - loved/hated [product] because... |
| Is this replacing something? If so, what and why? | Replacement context | Yes - old one broke/outdated/insufficient |
| Is there anything else I should know about this purchase? | Open-ended | Environment constraints, compatibility needs, etc. |

---

## Interview Flow Guidelines

### For New Users (no buyer profile)

1. Welcome and explain the process
2. Ask geographic context questions first (establishes currency, market)
3. Ask philosophy and priority questions
4. Ask quality and brand preference questions
5. Ask budget pattern questions
6. Ask marketplace preferences
7. Summarize and confirm the profile
8. Proceed to purchase-specific questions

### For Returning Users (profile exists)

1. Confirm profile is still accurate (offer to update)
2. Skip directly to purchase-specific questions
3. Reference profile preferences in clarifying questions

### Question Grouping

- Group related questions together to reduce back-and-forth
- Use multiple-choice where appropriate (via AskUserQuestion tool)
- Offer sensible defaults when the user seems unsure
- Skip questions that are already answered from context

### Handling "I Don't Know" Responses

- For priority rankings: suggest common patterns
- For brand preferences: "no preference" is valid
- For budget: ask for a rough range or "what feels expensive"
- For technical specs: offer to explain or use reasonable defaults

---

## Output Mapping

After the interview, map responses to `buyer-profile.md` fields:

| Question Area | Maps To |
|---------------|---------|
| Country, currency, VAT | Geographic Context section |
| Priority ranking | General Philosophy > Priority Order |
| Risk tolerance | General Philosophy > Risk Tolerance |
| Build quality importance | Quality Preferences |
| Product style | Quality Preferences > Product Style |
| Trusted manufacturers | Brand & Manufacturer > Trusted |
| Avoided manufacturers | Brand & Manufacturer > Avoided |
| Budget flexibility | Budget Patterns > Budget Style |
| Premium tolerance | Budget Patterns > Premium Tolerance |
| Markup threshold | Budget Patterns > Markup Threshold |
| Technology preference | Feature Preferences > Technology Stance |
| Preferred marketplaces | Marketplace Preferences > Preferred |
| Avoided marketplaces | Marketplace Preferences > Avoided |
