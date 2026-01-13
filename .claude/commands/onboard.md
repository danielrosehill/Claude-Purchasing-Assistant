# Onboard — Intelligent Entry Point

You are starting a purchasing evaluation. Your goal is to get to a recommendation with **minimal user interaction**.

## Step 1: Assess Current State

Read and check these files:

1. **`buyer-profile.md`** — Is status "Configured" or "Not yet configured"?
2. **`for-ai/`** — Are there any files (screenshots, PDFs, links)?
3. **`purchases/active/`** — Is there an existing purchase folder with requirements?

## Step 2: Determine Path

### Path A: Everything Ready (Profile + Sources)

If buyer profile is configured AND sources exist in `for-ai/`:

1. Summarize what you found:
   - "Profile: [Country], [Currency], priorities are [X, Y, Z]"
   - "Sources: Found [N] files in for-ai/[folder]"
   - "Requirements: [Brief summary if requirements.md exists]"
2. Ask: "Ready to proceed with research and generate your recommendation report?"
3. If yes, proceed directly to research phase

### Path B: Sources but No Profile

If files exist in `for-ai/` but profile not configured:

1. Note: "I see you've provided product sources but don't have a buyer profile yet."
2. Ask only **essential** questions:
   - Country and currency
   - Budget range for this purchase
   - Any hard requirements or dealbreakers
3. Fill in sensible defaults for everything else
4. Proceed to research

### Path C: Profile but No Sources

If profile is configured but `for-ai/` is empty:

1. Ask: "What are you looking to buy?"
2. Ask: "Do you have specific products in mind, or should I search?"
3. Create purchase folder and requirements.md
4. Either wait for user to add sources or proceed with web research

### Path D: Nothing Configured

If both profile and sources are missing:

1. Run abbreviated interview (essentials only):
   - Country/currency
   - What they're buying
   - Budget
   - Must-have features
2. Create buyer profile with defaults
3. Create purchase folder
4. Ask for sources or proceed with search

## Step 3: After Assessment

Once you have enough context, remind the user of the deliverable:

"I'll research these options and generate a PDF recommendation report with:
- Top 3 ranked picks with your #1 choice highlighted
- Price comparisons across vendors
- Spec adherence matrix showing how each meets your requirements
- Purchase links

The report will be saved to `from-ai/[purchase]/report.pdf` and emailed to you if Resend is configured."

## Key Principles

- **Don't ask questions you already have answers to** — Check files first
- **Use sensible defaults** — Don't block on non-essential preferences
- **One deliverable focus** — Everything leads to the PDF report
- **Cache data** — Save product specs to `data/products/` for reuse
- **Minimize friction** — Get to the recommendation fast

## Example Flows

### User drops screenshots and runs /onboard
```
You: "I see you've added 3 screenshots to for-ai/monitors/. Your profile shows you're in Israel (ILS), prioritizing durability and value.

Ready to analyze these options and generate your recommendation report?"

User: "Yes"

You: [Proceeds to extract → research → PDF generation]
```

### First-time user with a question
```
User: "I need a new mechanical keyboard"

You: "Let me set up a quick profile. What country are you in and what's your budget range?"

User: "US, around $150"

You: "Got it. Any must-have features (hot-swap, wireless, specific switch type)?"

User: "Hot-swap, wired is fine"

You: [Creates profile with defaults, creates purchase folder, begins research]
```
