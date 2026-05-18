# Cost Curve & Pricing Strategy

##Packaging decision 
**Leader:**
Anonymity and trust for their employers as well as our leadership consulting.

**Filler:**
Survey customization, templates, and dashboard.

**Killer:**
Retaking the survey multiple times (but control with once per quarter) or AI other AI products to be sold seperatly vs bundling.

**Killer usage %:**
20%

**Bundle or add-on:**
That is add-on - additional price to customer

**70% rule: if Killer usage is <70%, it is probably an add-on**


## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | $1.90 | Mid model, as this is sentiment and summary activities for each survey|
| Inference (cascading/triage) | $3.90| Frontier model for summary of dashboard done only a few times by the leadership|
| Infrastructure | $1.50 | Only used at most twice per user if they wanted to restart |
| Data/storage | $0.70 | Only used after users submit their responses but it is encrypted and protected |
| Human-in-the-loop | $2.25 | QA review for continuity between what users typed or said to AI generated output makes sense|
| **Total AI COGS** | 10.25 | Still need to apply weighting to this for proper calculation |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:** GPT4.1min or equivalent Gemini
**Frontier model:** GPT5.5 or Sonnet 
**Routing rule:** Small model used for post analysis, buy customer facing related should be frontier model. 
**Expected cascade ratio:** 50% small modle / 50% frontier model

## Pricing Model

**Current pricing:** Free as a customer of the consultancies

**Proposed AI pricing:** Non-AI free fold in with consulting service / with AI additional $29 per user.

**Model:** seat-based / usage-based / outcome-based / ***hybrid***

## Pricing Strategy
- Strategy posture: **Maximize**
- Pricing model: **Hybrid (base + usage)**
- Unit of work metered: —
- Base fee ($/month): Retainer
- Price per unit: $1
- Estimated units/user/survey: 29.00
- **Implied revenue/user: $29.00**

## Decision Note
Why this pricing structure fits the buyer and the value delivered:




## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | | |
| Heaviest segment doubles | | |
| Model provider raises prices 50% | | |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):**
**After (AI-enabled):**
**Net margin shift:**

Use my Cost Model, Cascading Strategy, Pricing Model, and Break-Even Math as source material. Do not invent new numbers unless something is missing. If a number is missing, mark it as `[NEEDS INPUT]`.

Write the Board One-Pager in this structure:

Before (traditional SaaS):
- Current pricing:
- Current gross margin:
- Value framed as:

After (AI-enabled):
- Proposed pricing:
- AI COGS per user/month:
- Expected gross margin:
- Value framed as:

Net margin shift:
- Margin moves from ___% to ___%.
- Explain why the margin changes.

Why this is still a good business:
- Explain whether gross profit, revenue per user, retention, NRR, or customer value improves enough to justify the margin shift.

Board-ready narrative:
- Write 3-5 sentences I could say to a CFO or board member.
- Make it concrete, not hype.
- Include the main risk and the mitigation.

End with:
"The bet works if..."
