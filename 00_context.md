# ZERO FEES PRODUCT STRATEGY — MASTER CONTEXT (EXECUTION VERSION)

---

## ⚠️ INSTRUCTIONS (LLM + HUMAN)

You MUST:
- use only definitions in this document
- NOT assume missing logic
- NOT add fallback behavior unless explicitly selected by merchant
- enforce pre-tender price transparency
- NOT decide fee method after card type is known (card type is unknown at presentation time)

If conflict:
→ follow rules matrix and transparency constraints

---

# 1. BUSINESS OBJECTIVE

## Primary Objective
Increase GPV by driving merchant switching using a “0% credit card processing fees” positioning.

## Secondary Objective
Monetize via:
- SaaS subscription
- higher effective processing rates (where applicable)

---

## Success Criteria

### Primary
≥50% merchants indicate willingness to switch

---

### Secondary
- willingness to pay:
  - SaaS (range to be determined)
  - OR higher processing rates

---

### Activation
≥50% indicate willingness to activate

---

## Kill Criteria

- switching intent <30%
- OR no willingness to pay (SaaS OR pricing)
→ STOP / REVISE

---

# 2. CURRENT STATE (BASELINE)

## Pricing Model

### Cohort A (~30%)
- Credit: surcharge (~3%) passed to customer
- Debit: lower % fee (not passed)

### Cohort B (~70%)
- Flat pricing (same rate across payment types)

---

## Messaging

- Marketed: “zero fees” (in some cases)
- Actual: “lower fees”

---

## Product Scope

- POS + invoicing/paylinks + online

---

# 3. DEFINITIONS

## Surcharge
- applied to credit cards only
- NOT allowed on debit across all surfaces
- subject to state restrictions + caps

---

## Embedded Pricing
- merchant sets a single displayed price
- pricing may be adjusted to offset costs
- may include discounting for specific payment types (e.g. ACH)
- NOT assumed as fallback — must be explicitly selected

---

## Convenience Fee
- can be applied in:
  - invoice
  - online
- NOT used in POS

---

## Coverage %
% of transactions where fees are offset

---

## Activation
- “Would turn on this week”
- OR prototype completion

---

## Retention
- “Would rely on this as primary system”
- includes willingness to pay

---

# 4. HARD CONSTRAINTS (CRITICAL)

## Pre-Tender Pricing Constraint

- Final price must be known BEFORE payment method is presented
- System cannot:
  - change price after card type is known
  - apply different pricing post-selection (except surcharge where allowed)

---

## Card-Type Constraint

- Card type (credit vs debit) is UNKNOWN before presentation
- System must define pricing BEFORE card is presented

---

## Transparency Constraint

- Customer must see:
  - final price
  - or clear pricing logic
BEFORE payment method selection

Violation risk:
- UDAAP / lack of transparency

---

# 5. RULES MATRIX (REVISED)

## CREDIT

| Surface | Allowed |
|--------|--------|
| POS | surcharge |
| Invoice | surcharge OR convenience fee |
| Online | surcharge OR convenience fee |

---

## DEBIT

| Surface | Allowed |
|--------|--------|
| POS | embedded pricing OR no fee |
| Invoice | embedded pricing OR convenience fee |
| Online | embedded pricing OR convenience fee |

---

## ACH

| Surface | Allowed |
|--------|--------|
| Invoice | no fee OR convenience fee OR embedded discount |
| Online | no fee OR convenience fee OR embedded discount |

---

## INVALID RULE HANDLING

- illegal configurations are BLOCKED
- system does NOT auto-correct

---

# 6. SEGMENTATION MODEL

## Segments

S0 — Unaware  
S1 — Aware inactive  
S2 — Curious  
S3 — Active switcher  
S4 — Pain-triggered  
S5 — Optimizer  

---

## Additional Dimensions (MANDATORY)

- Industry
- Ticket size
- Customer type

---

## Assignment

- primary segment
- attribute tagging

---

# 7. FEE MECHANISM TAXONOMY

## Pass-through
- credit only

## Embedded pricing
- applies to all payment types
- must be explicitly configured

## Contextual
- invoice / online only

## Hybrid
- combination of mechanisms
- must still satisfy pre-tender constraint

---

# 8. PRODUCT CONSTRUCTS (REVISED FOR CONSTRAINTS)

## GLOBAL RULES

ALL constructs MUST:

- define pricing BEFORE payment method
- NOT rely on card-type detection
- NOT apply hidden fallback
- explicitly show:
  - what customer sees
  - what varies by method (if allowed)

---
PRODUCT CONSTRUCTS :

## 🔴 CONSTRUCT A — CREDIT FEE MODEL (“CARD FEE” / SURCHARGE)

### Pricing Definition (Pre-Tender)
- Shelf/menu price = base price  
- Customer sees:
  - “+X% for credit card payments”

---

### Payment Behavior

| Payment Type | Price |
|-------------|------|
| Credit | base + fee |
| Debit | base |
| Cash | base |

---

### Merchant Configuration
- Set fee % (within allowed caps)
- Choose display language:
  - “card fee” OR “surcharge”

---

### Customer Experience
- Lower visible price upfront  
- Fee appears at payment step (allowed for surcharge)

---

### Compliance Constraints
- Debit cannot be surcharged  
- Disclosure/signage required  
- Fee must be shown before payment  

---

### Coverage Reality
- Only credit transactions offset fees  
- Debit + cash not covered  

---

### Key Risks
- Debit inconsistency  
- Customer pushback on fee  
- Perceived “nickel-and-diming”  

---

---

## 🔴 CONSTRUCT B — EMBEDDED PRICE + DISCOUNT MODEL  
**(“PRICES INCLUDE FEES, PAY LESS WITH CASH/ACH”)**

### Pricing Definition (Pre-Tender)
- Shelf/menu price = fee-inclusive price (system-calculated)  
- Customer sees full price upfront  

---

### Payment Behavior

| Payment Type | Price |
|-------------|------|
| Credit | full price |
| Debit | full price |
| Cash | discounted |
| ACH | discounted |

---

### Merchant Configuration
- Set margin goal OR fee recovery target  
- Select discount rule:
  - cash only OR cash + ACH  

System calculates:
- list price  
- discount amount  

---

### Customer Experience
- No surprise fees  
- Discount shown as:
  - “pay less with cash/ACH”

---

### Compliance Constraints
- Posted price MUST match charged price  
- Discount must be clearly disclosed  
- Cannot show lower shelf price and increase later  

---

### Coverage Reality
- All transactions priced to recover fees  
- Discount reduces margin selectively  

---

### Key Risks
- Higher visible price vs competitors  
- Merchant distrust in calculated pricing  
- Discount misunderstanding  

---

---

## 🟡 CONSTRUCT C — CHANNEL-BASED MODEL  
**(“DIFFERENT PRICING BY CONTEXT”)**

### Pricing Definition (Pre-Tender)
Merchant selects pricing model per surface:

- POS → Model A OR Model B  
- Invoice → Model A OR Model B OR convenience fee  
- Online → Model A OR Model B OR convenience fee  

---

### Payment Behavior (Example)

**POS (Model A — surcharge)**

| Payment Type | Price |
|-------------|------|
| Credit | base + fee |
| Debit | base |
| Cash | base |

---

**Invoice / Online (Convenience Fee)**

| Payment Type | Price |
|-------------|------|
| Card | base + fee |
| Debit | base + fee |
| ACH | base |

---

---

### Merchant Configuration
- Select model for each:
  - POS
  - Invoice
  - Online  

---

### Customer Experience
- Pricing differs by channel  
- Customer expectations vary:
  - in-person → fee sensitivity higher  
  - online → fee more accepted  

---

### Compliance Constraints
- Each channel must independently comply  
- Pricing defined before payment selection  
- No mixing rules within a transaction  

---

### Coverage Reality
- Depends on channel mix  
- Invoice/online often higher coverage  

---

### Key Risks
- Inconsistent experience across channels  
- Staff confusion  
- Harder to reason about total pricing  

---

# GLOBAL CONSTRUCT RULES

## Pre-Tender Pricing
- Final price must be determined BEFORE payment method selection  
- System cannot adjust pricing after card is presented  

---

## Card-Type Constraint
- Credit vs debit unknown at pricing time  
- Constructs must not depend on detecting card type  

---

## Transparency Rule
- Customer must see:
  - final price OR clear pricing logic  
before payment  

---

## No Silent Fallback
- System cannot:
  - switch models automatically  
  - apply hidden adjustments  

---

## Language Modes (TESTABLE)
- Plain:
  - “card fee”
  - “pay less with cash”

- Industry:
  - “surcharge”
  - “cash discount”


---
# 9. SURFACE DEFINITIONS

## POS
- surcharge allowed
- no convenience fee

---

## Invoice / Paylink
- surcharge allowed
- convenience fee allowed

---

## Online
- surcharge allowed
- convenience fee allowed

---

# 10. RISKS & BIAS CONTROLS

## Risk: “0% fees” misinterpretation
→ must show actual pricing behavior

---

## Risk: hidden fallback
→ disallowed

---

## Risk: post-tender pricing change
→ disallowed

---

## Risk: acquisition vs retention mismatch
→ measure separately

---

# 11. HYPOTHESES

H1:
Combination of messaging AND product construct increases switching

H2:
simpler constructs increase activation

H3:
clear pricing increases retention

H4:
merchants will pay if savings are credible

---

# 12. METRICS

## Primary
- switching intent

## Secondary
- willingness to pay:
  - SaaS
  - higher pricing

## Activation
- willingness to turn on

## Retention
- willingness to rely + pay

---

# 13. DECISION LOGIC

## GO
- ≥50% switching intent
- activation ≥50%
- willingness to pay present

---

## NO-GO
- low switching
- OR no monetization

---

# 14. WEDGE VS CORE

## Invoice / Paylink

Must:
- demonstrate path to POS usage

Otherwise:
→ insufficient

---

# 15. OPEN QUESTIONS

- debit mix by segment
- cash mix by segment
- acceptance of visible pricing differences
- compliance variation
- willingness to pay ranges

---

# 16. INSTRUCTIONS FOR DOWNSTREAM FILES

## Survey
- must show:
  - exact pricing scenarios
  - no hidden behavior
- must test:
  - expectation vs reality

---

## Prototype
- must:
  - define pricing before payment
  - show customer pricing clearly
  - not simulate post-card logic

---

## Experiment
- must separate:
  - acquisition
  - activation
  - retention