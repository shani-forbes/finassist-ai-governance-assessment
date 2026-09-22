# 02 — Data Inventory and Governance Decisions

## 1. Public Product Documentation — APPROVE
Use current, approved product documentation for factual answers. Controls should include ownership, effective dates, versioning, review, and removal of obsolete information.

## 2. Internal Knowledge Base — CONDITIONAL
FinAssist should not receive unrestricted access to the full internal knowledge base. Create a curated, AI-approved customer-support collection containing only information necessary for approved support use cases, such as approved procedures and escalation guidance.

Exclude unrelated HR information, security procedures, strategy documents, employee data, and other sensitive operational material unless a separately approved use case establishes necessity.

## 3. Customer Account Data — CONDITIONAL
Customer-specific data may be accessed only:
- Within an authenticated and authorized session.
- When required for the specific approved customer request.
- Through backend authorization that the LLM cannot override.
- Using contextual data minimization.

Examples:
- “What is my balance?” may require balance data.
- “What was the Starbucks charge?” may require relevant transaction history.
- “What is the interest rate on Premier Savings?” should not require customer account data.

Full account numbers, routing information, and other high-sensitivity fields should not be supplied to the model unless explicitly necessary for an approved use case.

## 4. Seven Years of Historical Support Conversations — CONDITIONAL
Do not use the corpus by default. First assess:
- Permitted secondary use / purpose limitation.
- Privacy and sensitive-data handling.
- Applicable retention requirements.
- Accuracy, currentness, and relevance of historical answers.
- Whether outdated policies/products are represented.
- Representativeness of languages, products, populations, and support scenarios expected at launch.

Remove, anonymize, or otherwise protect unnecessary personal/sensitive information. Historical CSAT can be one quality signal but is not sufficient proof that an agent answer is accurate, current, or approved.

## Data Governance Principle
**Necessary + permitted + appropriate.** A data source should not be used merely because it is available. The assessment asks whether the data is suitable for the use case, whether the organization is permitted to use it that way, and whether all of it is actually necessary.
