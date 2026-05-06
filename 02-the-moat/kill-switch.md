# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | Claude 2 version previous | M | Evalute when a new version is released is it viable against our true data set and allow switching to if needed to in 48hrs |
| **Abstraction** | Y | L | should be simple to swap out in the code as it would be API calls that would follow MCP in theory |
| **Routing** | Achitecture allows to swap out LLM API easily but also if there are AI issues, that it comes back with current issue and proper error handling| M | Support Team provided awareness to ensure switching can be done within a quick time frame (24hrs) |
| **Eval** | Compare golden dataset with the other vendor options | M | Run this every month against the top 2 open source LLM and top 2 other LLM models|

## Portability Score
<!-- Ready / Partial / Locked -->
Partially ready - AI should all be archtected out to be easy to swap out, however testing it would take time as we don't have an automated test system yet.

## If [primary vendor] doubles pricing tomorrow:
<!-- What's your 48-hour response? -->
Evaluate options to bring in a Open Source model that we can control long term as this use of AI shouldn't need the latest all teh time...only nuances is language related improvements like local language or slang that may not always be picked up from older LLM. We would do that in the next few weeks so that when tokens do go up we have our list of what open source version we can go to.

## If [primary vendor] ships a competing product:
<!-- What's defensible that they can't replicate? -->
They shouldn't but if they do, then again it goes back to leveragy both portability for other LLM, but also our other value adds like personal bespoke support and guidance for the leadership team.

**This week:** 
Add in as prebuilt / configurable alternative LLMs which is controlled by a flag to swithch LLM.
**This month:** 
Execute all the core testing needed to performa a switch and that post switching testing is completed across all functionality for the top alternative LLM.

**This quarter:** 
Execute the same as above but now for the 2nd alternative LLM.