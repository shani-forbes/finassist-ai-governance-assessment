# 05 — NIST AI RMF Mapping

The project uses the four NIST AI RMF Core functions as an organizing structure. NIST describes GOVERN as cross-cutting and emphasizes that the Core actions are not a checklist or fixed sequence.

## GOVERN
**Project application:** establish policies, accountability, risk tolerance, legal/compliance review, ownership, decision rights, lifecycle responsibilities, and documentation.

**FinAssist artifacts:**
- Governance/accountability model.
- Risk and control ownership.
- Data-governance decisions.
- Required remediation and launch gates.
- Change-management and incident-response responsibilities.

**Representative alignment:** GOVERN 1 (risk-management policies/processes) and GOVERN 2 (accountability structures and responsibilities).

## MAP
**Project application:** establish context of use, business objectives, intended users, affected stakeholders, intended/prohibited use, data, system boundaries, foreseeable misuse, and harms.

**FinAssist artifacts:**
- AI system profile.
- Intended-use boundary.
- Stakeholder map.
- Data inventory.
- Risk identification and consolidation.

## MEASURE
**Project application:** define qualitative/quantitative methods to test identified risks and control effectiveness before deployment and regularly during operation.

**FinAssist artifacts:**
- Accuracy and grounding evaluation.
- Boundary/advice tests.
- Cross-customer authorization tests.
- Prompt-injection/adversarial testing.
- Production quality/security metrics.
- Human-oversight measures.
- Change-triggered regression testing.

## MANAGE
**Project application:** prioritize and treat risks, decide whether deployment should proceed, respond to incidents, monitor residual risk, and improve controls.

**FinAssist artifacts:**
- Mitigation decisions for R-01 through R-05.
- Current vs target residual risk.
- Required remediation.
- Conditional launch decision.
- Incident response and re-assessment triggers.

## Generative-AI Profile Considerations
Because FinAssist is generative AI, the assessment gives additional attention to confabulation/inaccurate output, information integrity, prompt injection/adversarial manipulation, data/privacy risks, human-AI configuration, and ongoing evaluation.

## References
- NIST AI RMF 1.0: https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- NIST AI RMF Core: https://airc.nist.gov/airmf-resources/airmf/5-sec-core/
- NIST AI RMF Playbook: https://airc.nist.gov/airmf-resources/playbook/
- NIST AI 600-1 Generative AI Profile: https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence
