# Architecture

Status: ACTIVE in Module 3.

## Gate

Name hard constraints and three concrete options. Weights and scores use 1–5; a score of 5 always means most favorable. Define 1/3/5 anchors. Multiply weights by scores and sum. Record estimates and run one sensitivity check.

Hard Constraints: The feature must have 0 monetary cost, run in the provided Codespace, use HTML, CSS, and JavaScript, persist submitted availability using localStorage, and be simple enough to inspect and verify below the assignment deadline. 

Scoring anchors: (Scores use a 1-5 scale where 5 is the most favorable)
- 1 = Poor fit: expensive, slow, hard to inspect, or does not meet the specification well
- 3 = Acceptable fit: meets the basic need but involves noticeable trade-offs.
- 5 = Strong fit: low cost, quick to implement, easy to inspect, and closely meets the specifications well.

| Criterion | Weight | Hand-built option | Existing-service option | AI-assisted build |
|---|---:|---:|---:|---:|
| Cost to start |4 |5 |3 |5 |
| Cost to maintain |3 |5 |3 |4 |
| Time to working |4 |3 |4 |5 |
| Inspectability |5 |5 |2 |3 |
| Switching cost |2 |5 |2 |4 |
| Fit to spec |5 |5 |3 |4 |
| Weighted total | | 105 | 59 | 94 |

## ADR-001

Title and date: September 16, 2026 - Hand-build the member availability feature
Status: Accepted
Door / concrete acquisition and execution choice: Build - hand-build the feature using HTML, CSS, JavaScript, and browser localStorage
Context: The selected feature allows competitive dance team members to submit unavailable times and view their submitted availability. The project has a zero-dollar budget and must be completed before the deadline. The implementation also needs to run in the Codespace and be simple enough for me to inspect and verify against the specification. The Build-Buy-Delegate Gate gave the hand-built option the highest weighted score at 105, compared with 94 for an AI-assisted build and 59 for an existing service. 
Decision: I plan on hand-building the member availability entry feature using HTML for structure, CSS for presentation, JavaScript for behavior, and localStorage for persistence
Consequences and revisit trigger: This keeps the implementation inexpensive, directly aligned with the specification, and easier for me to inspect and verify. However, the feature will only store data in the user's browser and will not provide shared availability across different team members. It also requires more manual development time than relying primarily on an AI-assisted build. The localStorage decision should be revisited when the project requires shared storage in a later module. 

Keep superseded ADRs. The pedagogical browser build can coexist with a different architecture recommendation; explain the distinction.
