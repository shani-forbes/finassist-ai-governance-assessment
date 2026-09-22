# 04 — Controls and Evidence Plan

A control should not be treated as effective merely because it appears in a design document. The assessment should identify what evidence demonstrates that the control is implemented and operating as intended.

| Control Area | Control | Primary Risks | Expected Evidence |
|---|---|---|---|
| Authorization | Customer identity derived from authenticated session; backend enforces customer-level authorization | R-01, R-04 | Architecture/data-flow diagram; API authorization configuration; access-control tests |
| Data isolation | LLM cannot request arbitrary customer IDs | R-01, R-04 | Tool/API schema; permissions review; negative tests |
| Knowledge governance | Only approved, current product/support content is retrievable | R-02 | Approved source inventory; owners; version/effective dates; change log |
| Grounding | Product/fee answers must be supported by retrieved approved content | R-02 | RAG configuration; evaluation results; sampled grounded responses |
| Abstention/escalation | Insufficient support triggers “cannot confirm” and human escalation | R-02, R-03 | Test cases; escalation logs; acceptance criteria |
| Intended-use boundary | Personalized recommendations and transactions are prohibited | R-03 | Policy; prompt/configuration; boundary test suite; escalation design |
| Least privilege | FinAssist receives only required data/tool permissions | R-01, R-04 | Permissions matrix; tool inventory; security review |
| Adversarial testing | Prompt-injection and misuse attempts are tested | R-04 | Threat model; red-team/adversarial test report; remediation log |
| Human oversight | Higher-impact agent workflows require appropriate verification | R-05 | Agent procedure; training; UI/source visibility; audit samples |
| Production monitoring | Defined signals detect quality, misuse, and boundary failures | R-02–R-05 | Monitoring specification; dashboards/alerts; review records |
| Incident response | AI incidents have triage, containment, escalation, communication, recovery, and reassessment | All | AI incident runbook; roles; tabletop/test evidence |
| Change management | Material changes trigger review and regression/TEVV | All | Change policy; trigger list; release checklist; test reports |

## Pre-Launch Evidence Minimum
Before full production launch, reviewers should have sufficient evidence to confirm:
1. Customer authorization and data-isolation architecture is implemented and tested.
2. Approved knowledge sources have named owners and lifecycle procedures.
3. Intended-use and prohibited-use boundaries are implemented and tested.
4. Pre-launch accuracy/grounding and escalation tests meet documented acceptance criteria.
5. Prompt-injection/adversarial testing has been performed against the actual tool/data permissions.
6. Production monitoring and incident response have defined owners, thresholds, and procedures.
7. System/risk ownership and shutdown/re-launch decision rights are approved.
