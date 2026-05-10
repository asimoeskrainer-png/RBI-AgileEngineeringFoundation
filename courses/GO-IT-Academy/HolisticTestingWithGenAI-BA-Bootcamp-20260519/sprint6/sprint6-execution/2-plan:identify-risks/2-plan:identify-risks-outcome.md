# Risk-Based Test Prioritization using MoSCoW

## Risk Assessment Overview

| User Story | Impact | Likelihood | Risk Level |
|---|---|---|---|
| US2300-Czech Language Support | Medium | Medium | Medium |
| US2350-Provide Product Articles in Czech Language | Low | Medium | Low |
| US3100-Add PayU Payment Support for Czech Customers | Critical | High | Very High |
| US3206-MD5 Hashed password | Critical | High | Very High |
| US3409-Fix vulnerability in "Auth-X32" | Critical | High | Very High |
| US4700-Login during checkout workflow | High | High | High |
| US5003-Replace ORMapper | High | Medium | High |

---

# MoSCoW Prioritization

## MUST

### US3100 - Add PayU Payment Support for Czech Customers

#### Reasoning

This story directly impacts:
- Revenue generation
- Checkout completion
- Customer trust
- Czech market entry

Payment integrations are highly risk-prone because they involve:
- External systems
- Transaction consistency
- Security
- Real-money processing

A failure would immediately affect production sales and customer
experience.

#### Risk Drivers
- High business impact
- Complex integration
- Production payment risk
- Checkout dependency
- Financial impact

---

### US3409 - Fix vulnerability in "Auth-X32"

#### Reasoning

This story addresses a known security vulnerability.

Authentication vulnerabilities can lead to:
- Unauthorized access
- Account compromise
- Compliance violations
- Production security incidents

Security fixes must be validated before release because failures can
have severe legal, financial, and reputational impact.

#### Risk Drivers
- Critical security exposure
- Authentication dependency
- High production risk
- Customer data protection
- Compliance relevance

---

# SHOULD

### US4700 - Login during checkout workflow

#### Reasoning

This story changes a highly business-critical workflow.

Checkout and authentication are already high-risk areas individually.
Combining both increases:
- Session risks
- Workflow complexity
- Regression potential

Failures would significantly impact conversion rates and checkout
stability.

#### Risk Drivers
- High customer visibility
- Checkout dependency
- Session handling complexity
- High regression probability

---

# COULD

### US2300 - Czech Language Support

#### Reasoning

The feature is important for localization and market readiness but has
lower technical and business risk compared to payment and security
changes.

Most failures would likely result in:
- UX problems
- Translation inconsistencies
- Reduced customer experience

The risk is moderate but not critical for production stability.

#### Risk Drivers
- Localization complexity
- Medium customer impact
- Limited security impact
- Lower production risk

---

# WON’T

### US2350 - Provide Product Articles in Czech Language

#### Reasoning

This story mainly affects product content and localization quality.

Potential failures would:
- Not block checkout
- Not affect security
- Not impact core system stability

The business impact is relatively low compared to other sprint items.

#### Risk Drivers
- Low technical complexity
- Low production risk
- Mostly content-related impact

---

### US5003 - Replace ORMapper

#### Reasoning

Although technically risky, the change is mostly internal and may not
have direct visible business impact during this sprint.

Testing effort would likely be high due to:
- Broad regression scope
- Backend dependencies
- Potential hidden side effects

Given limited testing capacity, the focus should remain on directly
customer-facing and security-critical functionality.

#### Risk Drivers
- Technical complexity
- High regression effort
- Lower immediate customer visibility
- Internal architectural change

---

# Final Testing Recommendation

## Highest Testing Priority

Focus testing efforts on:
1. Payment workflows
2. Authentication and security
3. Checkout/login integration

These areas combine:
- Highest business impact
- Highest production risk
- Highest customer visibility
- Highest likelihood of severe failure

---

# Reflection

The prioritization shows that:
- Security and payment stories dominate risk exposure
- Customer-facing workflows require stronger validation
- Localization features carry lower operational risk
- Internal technical refactorings may require selective regression
  instead of full sprint focus

Following the principle:

> "No risk, no test."

the testing effort should concentrate on the stories with the highest
combination of impact and likelihood.