# Golden Dataset & Reliability Contract

## Golden Dataset Spec

| # | Input | Expected Output | Edge Case? | Judge Type |
|---|-------|----------------|-----------|-----------|
| 1 | Account has less then 80% user participation | Client leadership concerned with the team participation or negative escalation to the participants | N | rule + LLM |
| 2 | Users leverage the AI rewrite and find it doesn't satisfy or improve upon what they wrote | Negative feedback to leadership about what's the value in this product and escalation to our leadership with recovery plan | N | rule + LLM |
| 3 | Those that have access to the dashboard (Leaders or admins) see the AI suggests by each question and doubt the accuracy of the feedback | Correction to the system so recovery plan with escalation to leaderhship | N | rule + LLM |
| 4 | The theme role up for each question isn't accurate and therefore erodes trust and causes the wrong actions to be taken by the client organization | Correction to the system so recovery plan with escalation to leadership | Y | rule + LLM |
| 5 | Users of they system type in negative feedback such that its hard for anyone in the org to believe if AI was hallucinating | Have our logs to be reviewed for any extreme views (e.g. doing harm, propery damage, threats, etc.) | N | rule + LLM |
| 6 | Leadership reviews the AI dashboard and finds the summary to be flawed based on their evaluation of the lower level detail and find no value in what is provided | Our leadership gets customer disatisfaction on the tool and wants to pull out of our system | Y | rule + LLM |
| 7 | Users feel frustrated as the rewrites don't convey the level of postitive or negative sentiment they want to convey | Both organizations leadership voice concerns that it isn't an accurate reflection of the team | Y | rule + LLM |
| 8 | Leadership wants to see data and evidence that this system is helpful vs adds noise to the feedback process| Our leadership provides our sample data via dashboard results of the different industries we have data for and insights we would have derived with manual evaluation vs what AI has done in witht the same inputs | N | rule + LLM |
| 9 | Users requested AI generation more times then expected (e.g. 20 times per question) | We have cap on the number of generations by user can use per question (target 3) | N | LLM |
| 10 | Leader or admin requested AI generation multiple times and want to see how the results are as they come in | Provide an understanding of the cap is also 3 times do not enable until after all input is recieved/expired date of survey and guide them to wait until all employee feedback is recieve before they can request the AI summary update | N | rule / LLM |

<!-- Edge = rare but legit input
Boundary = sits exactly at a limit/threshold (a subset of edge)
Adversarial = someone deliberately trying to break it -->

**Adversarial rows included:** 3
**Coverage gaps identified by partner:**
The users can start using the same AI feedback (e.g. the same exact words etc.). Sentiment adjustment maybe needed by users / helping triangulate.

<!--Golden Dataset —

Test cases:
  1. Edge: N · Judge: both — IN: Account has less then 80% user participation  → OUT: Client leadership concerned with the team participation or negative escalation to the participants 
  2. Edge: N · Judge: both — IN:  Users leverage the AI rewrite and find it doesn't satisfy or improve upon what they wrote → OUT: Negative feedback to leadership about what's the value in this product and escalation to our leadership with recovery plan
  3. Edge: N · Judge: both — IN: Those that have access to the dashboard (Leaders or admins) see the AI suggests by each question and doubt the accuracy of the feedback → OUT: Correction to the system so recovery plan with escalation to leadership
  4. Edge: Y · Judge: both — IN: The theme role up for each question isn't accurate and therefore erodes trust and causes the wrong actions to be taken by the client organization → OUT: Correction to the system so recovery plan with escalation to leaderhship
  5. Edge: N · Judge: both — IN: Users of they system type in negative feedback such that its hard for anyone in the org to believe if AI was hallucinating → OUT: Have our logs to be reviewed for any extreme views (e.g. doing harm, propery damage, threats, etc.)
  6. Edge: N · Judge: both — IN:  Leadership reviews the AI dashboard and finds the summary to be flawed based on their evaluation of the lower level detail and find no value in what is provided → OUT: Our leadership gets customer disatisfaction on the tool and wants to pull out of our system
  7. Edge: Y · Judge: both — IN: Users feel frustrated as the rewrites don't convey the level of postitive or negative sentiment they want to convey → OUT: Both organizations leadership voice concerns that it isn't an accurate reflection of the team
  8. Edge: N · Judge: both — IN: Leadership wants to see data and evidence that this system is helpful vs adds noise to the feedback process → OUT: Our leadership provides our sample data via dashboard results of the different industries we have data for and insights we would have derived with manual evaluation vs what AI has done in witht the same inputs
  9. Edge: N · Judge: LLM — IN: Users requested AI generation more times then expected (e.g. 20 times per question)  → OUT: We have cap on the number of generations by user can use per question (target 3)
  10. Edge: N · Judge: both — IN: Leader or admin requested AI generation multiple times and want to see how the results are as they come in → OUT: Provide an understanding of the cap is also 3 times do not enable until after all input is recieved/expired date of survey and guide them to wait until all employee feedback is recieve before they can request the AI summary update

Dataset health
- Total: 10
- Edge cases: 2 (20.0%)
- Judge mix: 0% rule / 10% LLM / 90% both
-->

## Confidence UX Design

**Approach:** With each survey question, AI will attempt to rewrite/summarize what participant stated, but users don't have to accept or use. They can stick with what they wrote

**Confident (>90%):** With what you have provided, this is another way of saying what you want that also protects anonymity:

**Uncertain (50-90%):** With what you have provided we think you meant something like this, however it may not be exact as it sounds like you have nuances I am not familiar with:

**Not confident (<50%):** We can not provide a suggest to what you want to say as its not clear what you are suggesting, sorry. If you write it in a different way, we can evaluate again.

**User control surface:** 

Every answer that was wrong or needed regeneration, requires logging the user answer as well as the answer that didn't satisfy the users request.

- Users correct & override outputs
- Corrections feed back into the model / dataset
- Users adjust the confidence threshold _(not yet)_
- Users see AI reasoning / drivers _(not yet)_


**User control surface:**


## Defender Briefing — 60 seconds

**Bet:** AI for Survey Anonymity, Sentiment, and Summary with suggestion on Actions
**Users + domain:** SMB - starting with Small to Mid size business, then move to large corporations once vetted enough SMB post interview for consulting services.

**Top 3 golden rows already covered:**
1. Edge: N · Judge: both — IN: Users of they system type in negative feedback such that its hard for anyone in the org to believe if AI was hallucinating → OUT: Have our logs to be reviewed for any extreme views (e.g. doing harm, property damage, threats, etc.)
2. Edge: N · Judge: both — IN:  Leadership reviews the AI dashboard and finds the summary to be flawed based on their evaluation of the lower level detail and find no value in what is provided → OUT: Our leadership gets customer dissatisfaction on the tool and wants to pull out of our system
3. Edge: Y · Judge: both — IN: Users feel frustrated as the rewrites don't convey the level of positive or negative sentiment they want to convey → OUT: Both organizations leadership voice concerns that it isn't an accurate reflection of the team

**Confidence threshold + low-confidence behavior:** Approach:With each survey question, AI will attempt to rewrite/summarize what participant stated, but users don't have to accept or use. They can stick with what they wrote

Confident (>90%):With what you have provided, this is another way of saying what you want that also protects anonymity:

Uncertain (50-90%): With what you have provided we think you meant something like this, however it may not be exact as it sounds like you have nuances I am not familiar with:

Not confident (<50%): We can not provide a suggest to what you want to say as its not clear what you are suggesting, sorry. If you write it in a different way, we can evaluate again.

**Where I think the holes are:** The users can start using the same AI feedback (e.g. the same exact words etc.). Sentiment adjustment maybe needed by users / helping triangulate.




## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 92% | Review each survey response and each dashboard output · 20 golden rows · LLM-as-Judge (GPT-4o, accuracy rubric) | <88% → trigger gold-set audit |
| Hallucination rate | <1% | Same run with each survey response and each dashboard output · safety rubric flags fabricated policies/numbers | >2% → auto-rollback to last good model |
| Latency (p95) | <800ms | Auto run user test before launch of each survey to check for speed monitoring (Datadog) · p95 by endpoint | >1200ms for 5min → auto-rollback to last good model |
| Drift velocity | <0.5%/wk | Quarterly rolling accuracy trend vs. golden dataset | >1% decay/wk → trigger gold-set audit |

## HITL Architecture

**Trigger:** Confidence <60% OR safety rubric flag fires on a customer-facing output

**Reviewer:** PM on call (weekday 9–5 CT) · senior CSM after hours

**Feedback loop:** Reviewer corrections feed back into the new user survey sessions gold-set audit. 5+ corrections in a week triggers a model retrain candidate.

## Red-Team Findings
*What failure mode did your partner find that you missed?*
