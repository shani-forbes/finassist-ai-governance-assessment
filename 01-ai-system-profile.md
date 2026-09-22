# 01 — AI System Profile

## System
**Name:** FinAssist  
**Type:** Generative-AI customer-support assistant  
**Deployment context:** Authenticated customer portal for a fictional financial-services company

## Problem Statement
The existing rules-based chatbot struggles with natural-language requests, leading to failed self-service and unnecessary human escalation. FinAssist is intended to improve the customer experience while maintaining clear boundaries around financial advice, sensitive data, and autonomous actions.

## Intended Use
FinAssist is intended to provide authenticated customers with factual, approved information regarding the company's financial products, fees, policies, and supported services.

It may objectively compare approved product characteristics such as published interest rates, fees, eligibility requirements, and terms. It may perform approved calculations or scenario comparisons when the result can be derived objectively from customer-provided inputs and clearly stated assumptions.

## Prohibited Use
FinAssist must not:
- Determine which financial product is appropriate for an individual customer.
- Provide personalized financial or investment recommendations.
- Tell a customer to buy, sell, invest, or move funds based on individualized circumstances.
- Execute financial transactions.
- Retrieve another customer's information.
- Bypass authorization or use unapproved tools/data sources.

Questions requiring individualized financial judgment must be escalated or referred to an appropriately qualified human representative.

## Decision Boundary
A practical boundary is used:
1. **Factual information** — permitted.
2. **Objective comparison** — permitted using approved data.
3. **Approved calculation/scenario analysis** — conditionally permitted using objective inputs and disclosed assumptions.
4. **Personalized recommendation** — prohibited; escalate.
5. **Financial action/transaction** — prohibited.

Voluntarily disclosed customer characteristics do not automatically become relevant inputs. For example, a customer's age or retirement status should not be used to transform a factual rate question into a personalized recommendation.

## Primary Users and Affected Stakeholders
- Authenticated customers.
- Customer-support agents receiving escalations or AI-generated summaries.
- Other data subjects whose information may appear in account/support records.
- Product and AI/Engineering teams.
- Compliance, Legal, Privacy, Security, Risk, and Audit functions.

## High-Level Architecture Assumptions
This assessment assumes:
- Customer-specific data is retrieved through authenticated APIs.
- Customer identity is derived from the authenticated session rather than user-supplied identifiers.
- Authorization is enforced outside the LLM.
- The LLM cannot query arbitrary customer IDs.
- Approved product/support content is retrieved through a curated knowledge layer using retrieval-augmented generation (RAG).
- FinAssist has no authority to execute financial transactions.

These assumptions must be verified with architecture documentation and testing before launch.

## Success Measures
Business success should be evaluated alongside risk metrics. Candidate measures include self-service resolution, escalation rate, customer satisfaction, support handling time, answer accuracy/groundedness, abstention/escalation quality, customer-reported errors, and agent correction/override rate.
