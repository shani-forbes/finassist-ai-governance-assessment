# 03 — Risk Assessment

## Method
Risk statements use the structure:

> **Because of [cause], FinAssist may [risk event], resulting in [impact].**

The assessment distinguishes:
- **Risk event:** the harmful event that may occur.
- **Cause:** a condition that can contribute to the event.
- **Control gap:** a missing or inadequate safeguard.
- **Inherent risk:** risk before controls.
- **Current residual risk:** risk remaining after controls that are implemented and evidenced.
- **Target residual risk:** expected risk after required remediation is implemented and validated.

Qualitative ratings are Low / Medium / High. Where evidence is insufficient, the rating is marked TBD rather than inventing certainty.

## R-01 — Cross-Customer Data Disclosure
**Category:** Privacy & Security  
**Statement:** Because of inadequate authorization or customer data-isolation controls, FinAssist may retrieve or disclose account information belonging to another customer, resulting in unauthorized disclosure of sensitive customer information and privacy, regulatory, and reputational impacts.

**Inherent likelihood:** TBD pending architecture assessment  
**Inherent impact:** High  
**Current residual:** TBD / High pending validation of architecture, authorization controls, and cross-customer isolation testing.

**Target residual:** Low / High  
**Treatment:** Mitigate

**Key controls:** customer-scoped API authorization; customer ID derived from authenticated session; API returns only that customer's records; no arbitrary-ID querying by the LLM; cross-customer testing.

**Required action:** periodic and change-triggered regression/security testing of data-isolation controls.

## R-02 — Inaccurate Product Information
**Category:** Accuracy & Reliability / Consumer Harm  
**Statement:** Because FinAssist may generate responses that are inaccurate or unsupported by approved source information, it may provide incorrect information regarding financial products, fees, policies, or terms, resulting in customers making decisions based on inaccurate information and potentially experiencing financial harm.

**Inherent likelihood:** Medium  
**Inherent impact:** High  
**Current residual:** Medium / High until implementation/effectiveness evidence and lifecycle controls are complete  
**Target residual:** Low / High  
**Treatment:** Mitigate

**Key controls:** curated approved knowledge; RAG; source grounding; abstain/escalate when support is insufficient; pre-launch evaluation.

**Required actions:** production monitoring, knowledge change management, periodic evaluation, change-triggered re-testing, and error remediation workflow.

## R-03 — Personalized Financial Advice Outside Intended Use
**Category:** Consumer Harm / Compliance  
**Statement:** Because FinAssist may fail to adhere to its defined intended-use boundaries, it may use customer-provided or account information to generate personalized financial recommendations, resulting in customers making financial decisions based on AI-generated advice that may be unsuitable and could lead to financial harm.

**Inherent likelihood:** Medium  
**Inherent impact:** High  
**Current residual:** Medium / High pending boundary-test evidence  
**Target residual:** Low / High  
**Treatment:** Mitigate

**Key controls:** documented intended-use boundary; prohibited recommendation/action rules; human escalation; approved factual comparison/calculation patterns.

**Required actions:** boundary/adversarial test suite, monitoring for advice-like outputs, and re-evaluation after material model/prompt/capability changes.

## R-04 — Adversarial Manipulation / Prompt Injection
**Category:** Security  
**Statement:** Because FinAssist may be susceptible to adversarial inputs such as prompt injection, an attacker may manipulate the system into behavior outside approved boundaries, potentially resulting in unauthorized disclosure of sensitive information, misuse of connected tools or data sources, or other unauthorized system behavior.

**Inherent likelihood:** Medium  
**Inherent impact:** High  
**Current residual:** Medium / High until threat-model and adversarial-test evidence is reviewed  
**Target residual:** Low / High  
**Treatment:** Mitigate

**Key controls:** least privilege; authorization outside the LLM; tightly scoped tools/APIs; input/output protections; no arbitrary customer-ID access.

**Required actions:** prompt-injection/red-team testing, permission review, suspicious-pattern monitoring, incident response, and change-triggered re-testing.

## R-05 — Human Overreliance on AI Output
**Category:** Human Oversight / Operational  
**Statement:** Because employees may place excessive reliance on FinAssist outputs, they may accept or act on inaccurate or incomplete AI-generated information without appropriate verification, resulting in incorrect customer handling, financial or operational harm, or ineffective human oversight.

**Inherent likelihood:** Medium  
**Inherent impact:** Medium  
**Current residual:** Medium / Medium pending workflow validation  
**Target residual:** Low / Medium  
**Treatment:** Mitigate

**Key controls:** human escalation, access to underlying sources where feasible, defined prohibited uses.

**Required actions:** risk-based verification rules, agent training, source visibility, and monitoring of corrections/overrides/escalation outcomes.

## Consolidated Findings
Several brainstormed items were intentionally not retained as separate risks:
- **Stale/unapproved knowledge** is primarily a cause/control issue contributing to R-02.
- **Unsuitable model selection** is a governance/control consideration that can contribute to multiple risks.
- **Availability** is addressed through existing business-continuity/IT resilience controls for the current non-transactional use case; reassess if FinAssist becomes a critical or exclusive channel.
- **Inadequate monitoring/incident response** is a cross-cutting control gap rather than a standalone harmful event.
- **Unclear ownership/accountability** is a governance control gap and a pre-launch blocker even though it is not itself a risk event.
