# 06 — Testing and Monitoring Plan

## Objective
Provide evidence that FinAssist performs its intended purpose within approved boundaries and that material failures can be detected, contained, remediated, and re-evaluated throughout the lifecycle.

## Pre-Launch TEVV
### Accuracy and Grounding
- Build an approved evaluation set covering products, fees, terms, policies, edge cases, and ambiguous questions.
- Compare responses with approved source answers.
- Test whether cited/retrieved support actually substantiates the response.
- Test abstention when evidence is missing or conflicting.

### Intended-Use Boundary
Test prompts that move from factual questions toward individualized advice, including customers volunteering age, savings amount, retirement status, goals, or other contextual information. Confirm that factual information remains factual and personalized recommendations escalate.

### Privacy and Authorization
- Attempt cross-customer requests.
- Attempt direct/indirect identifier manipulation.
- Confirm customer identity comes from the authenticated session.
- Confirm the model cannot expand its own data scope.

### Security / Adversarial Testing
- Direct prompt-injection attempts.
- Attempts to reveal system/internal instructions or restricted knowledge.
- Attempts to invoke unapproved tools/actions.
- Tests using malicious or conflicting retrieved content where applicable.
- Rate/abuse patterns and logging/alerting behavior.

### Human Oversight
- Validate agent escalation workflows.
- Confirm higher-impact cases expose sufficient source/context for meaningful review.
- Test whether procedures are usable without forcing agents to independently re-do every low-risk task.

## Production Monitoring
Monitor a risk-based set of signals, including:
- Customer-reported incorrect answers.
- Unsupported/ungrounded answer rate.
- Abstention and escalation rate.
- Advice/boundary-violation detections.
- Suspicious/adversarial input patterns.
- Agent correction/override rate.
- Complaints and incident reports linked to FinAssist.
- Knowledge-source freshness/change failures.

Metrics require documented thresholds, owners, review cadence, and escalation paths. A periodic review alone is not sufficient for high-volume production issues that may require faster detection.

## Periodic Evaluation
Run a broader scheduled evaluation against a controlled test set. The exact cadence should be set by organizational policy and system risk rather than invented for the case study.

## Change-Triggered Evaluation
Re-test when a material change occurs, including:
- Model/model-version change.
- System prompt or major configuration change.
- Retrieval architecture change.
- New or materially changed data source.
- API/tool permission change.
- New customer-facing capability.
- Material product/policy change.

## Incident Response
The AI incident process should define:
1. Detection/intake.
2. Severity and affected-scope assessment.
3. Containment, including authority to disable a feature or FinAssist itself.
4. Investigation/root-cause analysis.
5. Customer/regulatory/internal communications as applicable.
6. Remediation and validation.
7. Re-launch approval when suspended.
8. Risk-register and test-suite updates to prevent recurrence.
