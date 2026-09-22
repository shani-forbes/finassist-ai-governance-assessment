# 07 — Governance and Accountability

## Principle
Risk ownership, control ownership, and independent/specialist review are related but distinct.

- **Risk Owner:** accountable for ensuring the risk is managed and residual risk is appropriately addressed.
- **Control Owner:** accountable for implementing and maintaining a specific control.
- **Review/Oversight:** provides specialist review, challenge, or assurance where appropriate.

## Working Accountability Model
| Area | Risk Owner | Control Owner(s) | Review / Oversight |
|---|---|---|---|
| FinAssist overall system risk | Product/System Owner | Multiple | Risk / Compliance / Security / Privacy as applicable |
| Customer authorization & isolation | Product/System Owner | Engineering | Security + Privacy |
| Product knowledge accuracy | Product/System Owner | Knowledge/Content Owner + AI Engineering | Compliance / Risk |
| Intended-use boundaries | Product/System Owner | Product + AI Engineering | Compliance / Legal/Risk |
| AI security/adversarial misuse | Product/System Owner | Security Engineering + AI Engineering | Security/Risk |
| Human oversight | Customer Support/Operations Owner | Support Operations + Product | Risk / Compliance |

## Decision Rights Required Before Launch
The organization must explicitly identify:
- Who accepts residual risk.
- Who can approve initial production launch.
- Who can suspend FinAssist or a specific capability.
- Who leads AI incident response.
- Who approves remediation and return to service.
- Who approves new data sources, tools, and capabilities.
- Who determines whether a system change requires re-assessment.

## Separation of Responsibilities
Engineering should test the controls it builds, but higher-risk controls should also receive appropriate challenge or specialist review. For example, Security may test whether authorization can be bypassed while Privacy assesses whether the data being processed is necessary and appropriate. A technically secure design can still present a privacy or governance problem.

## Launch-Blocking Governance Gap
FinAssist should not proceed to full production if overall accountability, risk-acceptance authority, shutdown authority, incident ownership, and re-launch authority remain undefined. This is a **control/governance gap**, not a separate risk event, but it can still be severe enough to block approval.
