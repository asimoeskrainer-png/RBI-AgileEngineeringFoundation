# Risk-Based Test Prioritization using MoSCoW

| User Story | Risk Level | MoSCoW Priority | Reasoning |
|---|---|---|---|
| US3100 - Add PayU Payment Support for Czech Customers | Very High | MUST | Direct impact on checkout, payment processing, revenue generation, and customer trust. High integration and production risk due to external payment provider dependencies. |
| US3409 - Fix vulnerability in "Auth-X32" | Very High | MUST | Security-critical change affecting authentication and customer data protection. Failure could lead to unauthorized access and compliance issues. |
| US4700 - Login during checkout workflow | High | SHOULD | Changes a business-critical checkout workflow and introduces session and authentication complexity with high regression potential. |
| US2300 - Czech Language Support | Medium | COULD | Important for localization and customer experience but lower production and security risk than payment or authentication changes. |
| US5003 - Replace ORMapper | High | COULD | Technically risky backend refactoring with broad regression potential, but lower direct customer visibility during this sprint. |
| US2350 - Provide Product Articles in Czech Language | Low | WON’T | Mainly content-related functionality with limited impact on system stability or critical business workflows. |
| US3206 - MD5 Hashed password | Medium | WON’T | Security-related improvement, but partially covered by the authentication library replacement and vulnerability fix. Lower standalone business impact this sprint. |
| US6001 - Minor UI Styling Improvements | Low | WON’T | Cosmetic changes with low business and production risk. Limited impact on critical workflows. |

---

# Summary

## MUST
- US3100 - Add PayU Payment Support for Czech Customers
- US3409 - Fix vulnerability in "Auth-X32"

## SHOULD
- US4700 - Login during checkout workflow

## COULD
- US2300 - Czech Language Support
- US5003 - Replace ORMapper

## WON’T
- US2350 - Provide Product Articles in Czech Language
- US3206 - MD5 Hashed password
- US6001 - Minor UI Styling Improvements

---

# Key Observations

- Payment and authentication stories carry the highest production and business risk.
- Security-related changes require stronger validation than localization or content updates.
- Customer-facing checkout workflows should receive higher testing priority.
- Internal technical refactorings may require selective regression testing rather than full sprint focus.
- Content and cosmetic changes are lower risk and suitable for reduced testing scope.

---

# Recommended Testing Focus

Prioritize testing efforts on:
1. Payment workflows
2. Authentication and security
3. Checkout and session handling
4. High-risk integration scenarios
5. Regression-prone workflows

Following the principle:

> "No risk, no test."

the testing effort should focus on stories with the highest business
impact and production risk.