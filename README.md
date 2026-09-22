# FinAssist AI Governance Assessment

## Portfolio Case Study

This project presents a governance and risk assessment for **FinAssist**, a fictional generative-AI customer-support assistant proposed by a mid-sized financial-services company. The assessment demonstrates a practical, risk-based approach to evaluating an AI system before deployment and throughout its lifecycle.

The project uses the **NIST AI Risk Management Framework (AI RMF 1.0)** as its primary organizing framework and draws on the **NIST Generative AI Profile (NIST AI 600-1)** for generative-AI considerations.

> **Important:** FinAssist and the company in this case study are fictional. Risk ratings and governance decisions are illustrative and are not legal, financial, compliance, or security advice.

## Scenario

The company currently uses a rules-based chatbot that performs poorly with natural-language requests and frequently escalates customers to human support. FinAssist is proposed to improve self-service while providing customers with approved information about products, fees, policies, and—within strict authorization boundaries—their own account information.

FinAssist is **not** authorized to provide individualized financial/investment advice or execute financial transactions.

## Business Objectives

- Improve customer self-service resolution.
- Reduce routine support contacts and unnecessary escalations.
- Improve customer satisfaction.
- Provide easier access to accurate, approved product, fee, policy, and supported account information.

## Assessment Conclusion

**Decision: Conditional approval / remediation required before full production launch.**

The proposed architecture and governance approach can reduce the identified risks to an acceptable target state, but the assessment identifies several controls that must be formalized and evidenced before or at launch: production monitoring and incident response; explicit system accountability and decision rights; knowledge lifecycle/change management; and change-triggered regression/TEVV testing.

No single control eliminates AI risk. The recommended approach combines technical authorization, retrieval grounding, defined intended-use boundaries, human escalation, security testing, monitoring, governance ownership, and lifecycle re-evaluation.

## Key Risks

1. **Cross-customer data disclosure** — unauthorized disclosure caused by failures in customer authorization or data isolation.
2. **Inaccurate product information** — incorrect or unsupported information leading to customer financial or other harm.
3. **Personalized financial advice outside intended use** — the system crosses from factual information/comparison into individualized recommendations.
4. **Adversarial manipulation / prompt injection** — malicious inputs attempt to move FinAssist outside approved boundaries or misuse connected data/tools.
5. **Human overreliance on AI output** — employees rely on incorrect or incomplete AI output without appropriate risk-based verification.

## Repository Contents

- `01-ai-system-profile.md` — purpose, users, intended use, boundaries, stakeholders, architecture assumptions.
- `02-data-inventory.md` — proposed data sources and governance decisions.
- `03-risk-assessment.md` — risk methodology, consolidated risks, and control gaps.
- `04-controls-evidence-plan.md` — controls, expected evidence, and pre-launch requirements.
- `05-nist-ai-rmf-mapping.md` — mapping to GOVERN, MAP, MEASURE, and MANAGE.
- `06-testing-monitoring-plan.md` — pre-launch TEVV, production monitoring, regression testing, and incident response.
- `07-governance-accountability.md` — risk owners, control owners, oversight, and decision rights.
- `08-executive-assessment.md` — concise decision memo and launch conditions.
- `FinAssist_Risk_Register.xlsx` — working risk register, control gaps, data inventory, and NIST mapping.

## Framework References

- NIST AI Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- NIST AI RMF Playbook: https://airc.nist.gov/airmf-resources/playbook/
- NIST Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile (NIST AI 600-1): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence

## Skills Demonstrated

AI risk identification and consolidation; intended-use analysis; data governance; risk and control design; inherent/current/target residual risk reasoning; control evidence planning; human oversight; security and prompt-injection considerations; lifecycle monitoring; stakeholder/accountability mapping; NIST AI RMF application; executive risk communication.
