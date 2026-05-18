# Compounding System Design

<!--
## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| | | | Y/N | active / broken / missing |
| | | | Y/N | active / broken / missing |
| | | | Y/N | active / broken / missing |

**Broken loop identified by partner:**
**Fix plan:**

## Context Connectivity
-->
<!-- How does knowledge flow across teams and domains? Where does it silo? -->


## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | User correction by retyping or modifying what they stated and clicks to refresh AI version | data for the system to learn how to write better summaries for users | Y | missing |
| Cross-Domain Transfer | Summary dashboard feedback based on clicking refresh | Drives possible golden data set changes | Y | missing |
| Network Intelligence | Each companies survey results gets added to our overall data (anonymized) | We have our own private view by sector by industry to help us provide trends to our customers | Y | active |

**Broken loop identified by partner:** —
Network Intelligence can be used to gauge not only industry and other company comparison, but help findout what other aspects to our company we can help provide and refine/update our value prop as well. We could also partner with other national and international organizations that gather this kind of data and work to align with them to increase our reputation in this space.
**Fix plan:** —



## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Support team -> Product Leadership team -> Engineering/Dev team -> QA -> Operations -> Sales -> Support team

**Where it silos:** Not sure yet, but to start no gap with a small team besides possible late at night support.


<!--
## Governance Policy

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

## Agent Topology
-->
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

<!-- Governance Policy -->

## Governance Policy

**Scope:** AI features in the OrgDiagnosis product — generate a qualitative rewrite of user response up to threshold of tries, while post Survey feedback analysis of each question and summarize based on extreme positive and extreme negative, but also the median sentiment with approx qualitative on who agreed with the most positive and most negative and the median, and resolution scoring. Also the overall summary of the surveys collective sentiment for the key themes and sentiment for leadership. Excludes: Internal-only analytics dashboards focused on collectively accumulated data (covered by separate data-team policy).

**Autonomy boundaries:** Drafting user rewrites — human approval required. Summarizing sentiments of the survey by all users of the same question — auto. Summarizing themes of the overall survey takers themes and areas of concern and areas of improvement — auto. Generate report with admin approval — never auto.

**Escalation triggers:** (1) Confidence < 75% on response. (2) Customer message flagged legal, dissatisfaction, or distressed. (3) Any reply mentioning refund, credit, or policy exception. (4) Customer requests human contact.

**Audit cadence:** Monthly — Automated eval against golden dataset (PM: Koemen). Quarterly — Human review of 50 random conversations + all escalation cases (Legal). Quarterly — Full policy review with security + legal (CTO sign-off).

**Regulatory exposure (EU AI Act / other):** EU AI Act, GDPR, SOC 2, PII. Risk tier: minimal. Controls: AI is used to remove PII· No training on customer PII · SOC 2 log retention controls in place · DPIA to be confirmed..

## Agent Topology

_Not shipping agents this version._


<!--
## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
-->
Shadow AI Audit

## Discover
- ChatGPT | Any including external  | users: 100 | access: Write | approved: Yes
- Gemini | Any including external | users: 100 | access: Write | approved: Yes
- Claude | Any including external | users: 100 | access: Write | approved: Yes

## Risk
- Total shadow tools: 3
- Unapproved + Write/Admin: 0
- Risk level: Low

## Action Plan
### Consolidate
None. All are allowed for all of the LLMs as we know users may try to do them as well, we should be able to accommodate the top 3 key LLM systems.

### Approve
All 3, but no others.

### Block
Any other LLMs.

## Policy Draft
Based on your audit: 3 tools discovered, 0 require action.

Recommended policy: Maintain an approved-tool catalog, lightweight quarterly audits, and clear channels for teams to request new tools before adoption.

Consolidate redundant tools, document owners and data classes, and align procurement with security review.
