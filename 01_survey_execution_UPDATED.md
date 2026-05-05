# Zero Fees Validation Survey — Full Execution Spec (UPDATED)

## Status
Updated to align with Cash + ACH Discounting PRD and strategic pivot to direct-first GTM

## Companion document
This file depends on:
- `Cash_Discounting_PRD.txt`
- `00_context.md`

This file must not redefine terms inconsistently with those documents.

---

# 0. PURPOSE OF THIS DOCUMENT

This document specifies the research survey for validating a cash + ACH discounting strategy positioned as true "zero fees."

This survey exists to answer a very specific strategic question:

> Can a "0% credit card processing fees" positioning drive meaningful merchant switching and activation — and does cash + ACH discounting (Model B) meaningfully expand the addressable market beyond surcharge-only (Model A)?

The core insight: Model A (surcharge) will attract a large segment, but a significant portion need TRUE zero fees (including debit) and are willing to accept Model B's trade-offs (higher posted prices). The question is whether Model B meaningfully increases the size of the pot (A + B together vs neither).

This survey is meant to produce signal strong enough to influence:
- Whether to build cash + ACH discounting capability
- Segmentation understanding (who wants A, who wants B, who wants neither, and why)
- Pricing strategy and merchant controls (auto-calculate ON/OFF preference)
- GTM positioning (Rate Saver evolution vs standalone)
- Surface prioritization and omni-channel acceptance
- Whether to build, narrow, or stop

This is an **intensive research study** using AI-driven conversations with in-depth follow-ups. Survey length is not a concern; depth and fidelity are priorities.

---

# 1. WHAT THIS SURVEY IS TRYING TO LEARN

## 1.1 Messaging fit
Does the headline "0% credit card processing fees" create strong merchant interest and switching intent?

Specifically:
- Does it make merchants willing to explore switching?
- Does it create expectations compatible with Model A and/or Model B reality?

---

## 1.2 Model validation: Current state (Model A) vs Future state (Model B) — NOT a competition, but market expansion

### Model A — Credit Fee Model (Current Rate Saver / Surcharge)
Merchant keeps base visible prices low (list/card price).  
Credit transactions pay a visible surcharge.  
Debit and cash do not (debit surcharge is illegal).

**Key limitation:** Merchant still pays processing fees on debit cards.  
**Key benefit:** Lower posted prices, familiar approach.

### Model B — Cash + ACH Discounting (Future State)
Merchant posts a fee-inclusive (higher) list/card price.  
System helps calculate that price (auto-calculate mode).  
Customers who pay with cash or ACH get a discount, paying lower amount.

**Key benefit:** TRUE zero fees on all cards (credit + debit).  
**Key trade-off:** Higher posted prices.

**This survey must validate:**
- Which merchants prefer Model A, which prefer Model B, and why?
- Does Model B meaningfully expand the addressable market (A + B together vs neither)?
- What segmentation dimensions predict preference (vertical, sub-vertical, cash mix, consumer frequency, peer behavior, channel)?
- This is NOT about Model B "beating" Model A. It's about understanding whether Model B captures a meaningful segment that would NOT adopt Model A.

---

## 1.3 Operational and compliance understanding

Do merchants grasp what's operationally and compliance-wise required of them for each model?

### Model A operational requirements:
- Post signage disclosing surcharge
- Show surcharge as separate line item at checkout
- Staff trained to explain "credit card fee"
- Cannot surcharge debit (accept paying fees on debit)

### Model B operational requirements:
- Update all posted prices (menus, shelves, website) to higher list/card prices
- Post signage: "Save X% with cash/ACH"
- Show discount as line item for cash/ACH payments
- Staff trained to explain "list/card price, save with cash/ACH"
- Attestation: independently setting prices, not linking to processing fees

**This survey must validate:**
- Do merchants understand these requirements?
- How much do they care about achieving zero fees to do these things?
- Which operational burden is more acceptable (Model A vs Model B)?
- Is operational complexity a blocker for either model?

---

## 1.4 Segmentation dimensions

Which merchants prefer which model, and why?

**Hypothesized segmentation dimensions:**
- **Vertical**: Restaurant/cafe vs retail vs services
- **Sub-vertical**: Cafe vs bakery vs full-service restaurant; convenience store vs boutique retail
- **Size**: Revenue band, transaction volume
- **Cash mix**: High-cash businesses (>20% cash) vs low-cash (<10%)
- **Consumer frequency**: Regulars (coffee shop, salon) vs one-time (HVAC repair, event vendor)
- **Peer behavior**: What local competitors or similar businesses are doing
- **Channel**: In-person vs invoice vs online — do consumers have different comfort levels with fees/discounts by channel?
- **Ticket size**: Sub-$25 vs $100+ — does visible pricing matter more at lower tickets?
- **Debit sensitivity**: High-debit businesses (grocery, gas) vs low-debit (luxury retail)

**This survey must validate:**
- Which dimensions predict Model A vs Model B preference?
- Are there vertical-specific patterns (e.g., restaurants prefer Model B, retail prefers Model A)?
- Do cash-heavy businesses naturally gravitate to Model B?
- Do high-frequency consumer businesses prefer Model A (avoid higher posted prices for regulars)?
- Does peer behavior matter ("my competitors do X, so I should too")?

---

## 1.5 Channel-based expectations

Do merchants think about pricing differently by channel, and WHY?

**Hypotheses:**
- Consumers may be more comfortable with fees on invoices/online (less friction) vs in-person (face-to-face discomfort)
- In-person: Lower posted prices matter more (impulse purchases, comparison shopping)
- Invoice/online: Transparency matters more (customer has time to review, less sticker shock)

**This survey must validate:**
- Which channels do merchants expect to use different pricing models, and why?
- Is there a specific rationale (consumer comfort, operational ease, competitive norms)?
- Do merchants want flexibility to choose Model A for POS and Model B for invoicing?

---

## 1.6 Convenience fee alternative (invoice/online)

For invoice and online channels specifically, do merchants expect to slap on a convenience fee regardless of payment method (no discounts at all)?

**Example:**
All online transactions: +3% convenience fee (card, ACH, all methods)

**This survey must validate:**
- Is convenience fee (flat add-on for all online/invoice) more attractive than Model A or Model B for those channels?
- Does convenience fee feel simpler or more problematic?
- Would merchants use convenience fee instead of Model A/B for online/invoice?

---

## 1.7 Auto-Calculate Preference (Core Merchant Control — Model B only)

Model B offers two modes:

### Auto-Calculate ON (Recommended)
Merchant enters desired **cash/ACH price** (target net revenue).  
System calculates **list/card price** by backing out discount with rounding.

**Example:**  
Cash price: $100 (merchant wants to net)  
List/card price: $100 ÷ (1 - 0.03) = $103.09 → rounds to $103.25  
Card customers pay $103.25, cash customers pay $100.15 after 3% discount.

### Auto-Calculate OFF (Pure Cash Discounting)
Merchant enters **list/card price**.  
Cash/ACH customers receive discount off that price.

**Example:**  
List/card price: $100 (merchant sets)  
Cash/ACH discount: $100 × 3% = $3.00  
Cash/ACH customers pay $97.00.

**This survey must validate:**
- Which mode do merchants prefer (within Model B adopters)?
- Do merchants understand the difference?
- Does rounding (e.g., $103.25 instead of $103.09) help or hinder?

---

## 1.8 Presentation preference: Cash Discounting vs Dual Pricing (Model B only)

### Cash Discounting (Single Price + Discount Line) — MVP
Single price displayed (list/card price).  
Discount shown as line item at checkout/receipt for cash/ACH payments.

**Example:**  
Menu shows: $103.25  
Cash receipt shows: $103.25 - $3.10 discount = $100.15

### Dual Pricing (Two Prices Shown Everywhere) — Future
Two prices displayed everywhere (shelf, menu, invoice):  
Card price $103.25 | Cash price $100.15

**This survey must validate:**
- Which presentation do merchants prefer (within Model B adopters)?
- Would merchants update menus/shelves to show dual pricing?
- Does dual pricing reduce friction or increase complexity?

---

## 1.9 Omni-channel acceptance

Cash + ACH discounting must apply across ALL payment surfaces:
- POS (in-person terminal)
- Mobile (GoDaddy Mobile app)
- Invoicing
- Paylinks
- Virtual Terminal / Phone orders

**This survey must validate:**
- Is omni-channel requirement acceptable?
- Which surfaces are most critical?
- Would surface-specific adoption (e.g., invoicing only) satisfy merchant needs?

---

## 1.10 ACH readiness

Invoicing and paylinks surfaces require ACH payment capability to offer ACH discount.

**This survey must validate:**
- Do merchants currently accept ACH?
- Would they enable ACH to offer discounts on invoices/paylinks?
- Is ACH unfamiliar or undesirable?

---

## 1.11 Disclosure and signage acceptance

Merchants must attest to:
- Posting physical signage: "Save 3% when you pay with cash or ACH"
- Pricing visibility on all materials (menus, boards, website)
- Independence claim: "I am independently setting prices, not linking them to processing fees"

**This survey must validate:**
- Is signage requirement acceptable (Model A and Model B both require signage)?
- Do merchants trust the positioning as compliant?
- Would disclosure burden block activation?

---

## 1.12 Payment mix shift expectations

Model B's economics improve if customers shift from cards to cash/ACH.

**This survey must validate:**
- Current payment mix (credit, debit, cash, ACH %)
- Expected payment shift if discount is offered
- Do merchants overestimate or underestimate shift potential?

---

## 1.13 Monetization reality

If we inflate processing rates to 3.5-4% to subsidize cash/ACH discounts (3-5%), what rate would merchants accept?

**This survey must validate:**
- Willingness to accept higher effective rates if net outcome is zero fees
- Rate acceptance varies by segment (high-volume vs low-volume, high-margin vs low-margin)

---

## 1.14 UX and trust validation (prototype interactions)

Merchants will be shown prototype interactions to test:
- Words and positioning (do they trust it?)
- UX clarity (do they understand it?)
- Willingness to act (do they care enough about zero fees to make the jump?)

**This survey must validate:**
- Does the UX build confidence or create confusion?
- Are the right levers exposed (auto-calculate, rounding, discount %)?
- Does the prototype feel like "the right product"?

---

# 2. WHAT THIS SURVEY IS NOT

This survey is NOT testing:
- Abstract enthusiasm for "lower fees" (already obvious)
- Impossible adaptive logic or post-tender pricing
- Debit surcharge (illegal, explicitly out of scope)
- Channel-based coexistence of surcharge + cash discount (out of scope for MVP)

---

# 3. HARD CONSTRAINTS — MUST BE PRESERVED IN EVERY QUESTION AND SCENARIO

## 3.1 Pre-tender pricing rule
Customer must see either final price or clear pricing logic before payment method selection.

## 3.2 Card-type unknown rule
Credit vs debit is not known until card is presented. Pricing model must work before card type is known.

## 3.3 Debit rule
Debit cannot be surcharged. Do not show or imply debit surcharge.

## 3.4 Transparency rule
No hidden fallback logic. No post-tender price changes. No undisclosed transformations.

## 3.5 Posted-price consistency rule
Merchant cannot advertise lower price and charge higher embedded price. List/card price is the standard price.

## 3.6 Terminology rule
Use "list/card price" consistently (not just "list price") to reinforce that this is the price card customers pay.

---

# 4. PRIMARY HYPOTHESES

## H1
A combination of "0% fees" messaging + either Model A or Model B can drive strong merchant switching intent. Model A will attract a large segment, but Model B meaningfully expands the addressable market by capturing merchants who need TRUE zero fees (including debit).

## H2
Model preference is predicted by segmentation dimensions:
- **Vertical/sub-vertical**: Restaurants/cafes prefer Model B (higher check sizes, cash culture), retail prefers Model A (price comparison, impulse)
- **Cash mix**: High-cash businesses (>20%) prefer Model B (easier to shift behavior)
- **Consumer frequency**: High-frequency regulars prefer Model A (avoid higher posted prices), one-time transactions prefer Model B
- **Peer behavior**: Merchants follow local/similar business norms
- **Channel**: Consumers more comfortable with fees on invoices/online vs in-person

## H3
Operational and compliance understanding is low initially, but merchants who care deeply about zero fees are willing to execute on Model B requirements (higher posted prices, signage, attestation).

## H4 (Model B only)
Auto-calculate ON (enter cash price, system calculates list/card price) is more attractive than auto-calculate OFF (enter list/card price, system calculates discount).

## H5 (Model B only)
Dual pricing (two prices shown everywhere) is preferred over cash discounting (single price + discount line), but operational burden (updating menus/shelves) may limit adoption.

## H6
Omni-channel requirement is acceptable if merchant transacts across multiple surfaces. Surface-specific adoption (e.g., invoicing only) may be viable wedge.

## H7
ACH readiness is a gating factor for invoicing/paylinks adoption. Many merchants unfamiliar with ACH or unwilling to enable it.

## H8
Disclosure/signage requirements are acceptable for both Model A and Model B and do not block activation (merchants expect compliance burden).

## H9
Merchants will overestimate payment mix shift (expect 10-20% shift to cash/ACH, reality may be 5-10%).

## H10
Merchants will accept higher processing rates (3.5-4% effective rate) if net outcome is zero fees via cash/ACH shift, especially high-volume merchants.

## H11
Channel-based thinking is real: merchants want flexibility to use Model A for POS and Model B (or convenience fee) for invoicing/online.

---

# 5. SUCCESS CRITERIA FOR THIS SURVEY

## 5.1 Primary success threshold
**Combined (Model A + Model B) vs neither:**
- **≥50% switching intent** for at least one model (A or B)
- **Meaningful vertical-specific performance**: At least one vertical shows ≥60% preference for A or B

**Model B specific:**
- Model B captures **≥20% of respondents** as preferred model (not majority, but meaningful segment)

This validates that Model B expands the addressable market beyond Model A alone.

## 5.2 Secondary thresholds
At least one model (A or B) produces:
- **≥50% activation intent**
- **Meaningful retention confidence** (≥60% would use long-term)
- **Willingness to accept rate inflation** (3.5-4% effective rate acceptable to ≥50% of Model B adopters)

## 5.3 Failure / kill interpretation
**If Model A + Model B combined does NOT meaningfully expand addressable market:**
- If <50% prefer any model (A or B or channel-based mix) over "neither," the strategy should be reconsidered.

**If Model B does NOT capture a meaningful segment:**
- If <15% prefer Model B, there is limited rationale to build it (Model A alone may suffice).

**If merchants reject operational/compliance requirements:**
- Higher posted prices (Model B)
- Auto-calculate logic (Model B)
- Omni-channel requirement
- ACH enablement
- Disclosure/signage (both models)

Then activation will stall and the strategy should be reconsidered.

---

# 6. SURVEY METHOD PRINCIPLES

## 6.1 Use concrete scenarios
Show worked examples with real prices, not abstract concepts.

## 6.2 Ask behavior-facing questions
Prefer: "Would you run your business this way?"  
Avoid: "Do you like this?"

## 6.3 Separate attraction, activation, and retention
Each needs distinct measurement.

## 6.4 Capture segmenting information early
Awareness stage, vertical, sub-vertical, ticket size, channel mix, cash mix, consumer frequency, peer behavior collected before model testing.

## 6.5 Keep models fair
Do not show one model in more favorable language than another.

## 6.6 Force tradeoffs
Every model must be shown with its downside.

## 6.7 Use AI-driven follow-ups
This is an intensive study. Probe verbatim responses, ask "why," explore objections deeply.

## 6.8 Integrate prototype interactions
Show key UX moments from prototypes to validate words, positioning, and trust.

## 6.9 Test operational and compliance understanding
Show what's required of merchants (signage, pricing updates, attestation) and measure acceptance.

## 6.10 Explore segmentation dimensions deeply
Vertical, sub-vertical, cash mix, consumer frequency, peer behavior, channel comfort — all must be captured and analyzed.

---

# 7. TARGET RESPONDENTS

Merchants or merchant prospects who are:
- **SMBs, ideally $300K–$5M annual revenue**
- **Decision makers or strong influencers in payment/pricing**
- **In-person first: >50% of revenue from in-store card transactions on POS or mobile**
- Operating on at least one relevant surface (POS, invoice, online)

**Why in-person first:**  
POS/mobile is the largest GPV opportunity. Invoice/online may be wedge, but primary validation must be on in-person transactions.

---

# 8. REQUIRED OUTPUTS FROM THE SURVEY

## 8.1 By pricing model
For Model A (surcharge) and Model B (cash + ACH discounting):
- Naturalness
- Switching intent
- Adoption intent
- Retention confidence
- Major objections
- Trust level
- Staff-operability confidence
- Operational burden acceptance
- Compliance confidence
- Monetization acceptance

## 8.2 Combined market expansion analysis
- **A + B vs neither**: What percentage prefer any model over current state?
- **A vs B vs neither**: Distribution of preferences
- **Channel-based mix**: Percentage who want A for some channels, B for others

## 8.3 By merchant configuration (Model B only)
- Auto-calculate ON vs OFF preference
- Rounding acceptance
- Cash discounting (single price + discount) vs dual pricing (two prices everywhere) preference

## 8.4 By segment
Cut all metrics by:
- **S0–S5** (awareness/behavior stage)
- **Vertical**: Restaurant/cafe, retail, services
- **Sub-vertical**: Cafe vs bakery vs full-service restaurant; convenience vs boutique retail
- **Revenue band**: <$300K, $300K–$1M, $1M–$5M, >$5M
- **Ticket size**: <$25, $25–$100, $100–$500, >$500
- **Cash mix**: High (>20%), medium (10-20%), low (<10%)
- **Debit sensitivity**: High-debit businesses (>30% debit) vs low-debit (<10%)
- **Consumer frequency**: Regulars (high-frequency repeat) vs one-time/infrequent
- **Peer behavior**: Following local/similar business norms vs independent
- **Channel mix**: POS-heavy (>70%), invoice-heavy (>30%), online-heavy (>30%), mixed
- **Current payment mix**: Credit %, debit %, cash %, ACH %

## 8.5 Decision outputs
The readout must answer:
- Does Model B meaningfully expand the addressable market beyond Model A? (A + B vs neither)
- Which merchants prefer Model A, which prefer Model B, and why? (segmentation patterns)
- Which auto-calculate mode wins (ON vs OFF) for Model B adopters?
- Which presentation wins (cash discounting vs dual pricing) for Model B adopters?
- Is omni-channel requirement acceptable? Which surfaces are most critical?
- Is ACH readiness a blocker for invoicing/paylinks?
- Are operational/compliance requirements (higher prices, signage, attestation) acceptable?
- What rate inflation is acceptable for Model B adopters?
- Is channel-based pricing (A for POS, B for invoice) a meaningful preference?
- Is convenience fee (invoice/online) an alternative to A or B?
- Should we build Model B capability?

---

# 9. FULL SURVEY FLOW

The survey should be structured in this exact order:

1. **Qualification and segmentation**  
   - Industry (vertical)
   - Sub-vertical
   - Revenue band
   - Role in decision making
   - Awareness / behavior stage (S0–S5)
   - Typical ticket size

2. **Current state, channel usage, and payment mix baseline**  
   - Current approach to fees
   - Current urgency
   - Channel usage (where you take payments)
   - Current payment mix (credit %, debit %, cash %, ACH %)
   - ACH familiarity and usage
   - Debit sensitivity
   - Cash sensitivity
   - Consumer frequency (regulars vs one-time)
   - Peer behavior (what competitors/similar businesses do)

3. **Headline reaction**  
   - Headline appeal
   - Exploration intent
   - Meaning expectation
   - Zero fees value proposition depth
   - Switching motivation

4. **Constraint tolerance**  
   - Pre-tender pricing acceptance
   - Debit handling expectation
   - Different prices by payment type
   - Posted price vs checkout price
   - Main risk perception

5. **Model A scenario (Current State: Surcharge)**  
   - Scenario framing
   - Naturalness
   - Adoption intent
   - Switching intent
   - Main concern
   - Customer expectation fit
   - Debit gap acceptance
   - Operational requirements understanding

6. **Model B scenario (Future State: Cash + ACH Discounting)**  
   - Scenario framing
   - Naturalness
   - Higher posted price acceptance
   - Trust in calculated pricing
   - Adoption intent
   - Switching intent
   - Main concern
   - Customer expectation fit
   - Coverage benefit (credit + debit)
   - Operational requirements understanding

7. **Auto-calculate preference (Model B configuration)**  
   - Auto-calculate ON explanation
   - Auto-calculate OFF explanation
   - Preference
   - Rounding acceptance
   - Comprehension check

8. **Presentation preference: Cash Discounting vs Dual Pricing (Model B configuration)**  
   - Cash discounting (single price + discount line) explanation
   - Dual pricing (two prices everywhere) explanation
   - Preference
   - Operational burden (dual pricing)
   - Customer clarity (dual pricing)

9. **Omni-channel and surface preferences**  
   - Omni-channel requirement acceptance
   - Surface importance ranking
   - Surface-specific adoption (if omni-channel rejected)

10. **Channel-based thinking**  
    - Channel mindset (do you think differently by channel?)
    - Channel-specific model preferences (POS vs invoice/online)
    - Why that combination makes sense
    - Convenience fee alternative (invoice/online)
    - Other models preferred (open-ended)

11. **Model comparison and tradeoffs**  
    - Most realistic model
    - Strongest switching driver
    - Best long-term fit
    - Core tradeoff preference
    - "Zero fees" threshold

12. **Payment mix shift expectations**  
    - Expected shift with cash/ACH discount (slider)
    - Customer behavior assumption

13. **Language and terminology**  
    - Credit-fee language clarity
    - Discount language clarity
    - Naming style preference

14. **Disclosure and signage acceptance**  
    - Signage requirement acceptance
    - Pricing visibility attestation
    - Independence attestation
    - Compliance confidence

15. **Prototype interaction and UX validation**  
    - Setup screen interaction
    - Payment method selection interaction
    - Receipt interaction
    - Manual entry / virtual terminal interaction
    - Invoice creation interaction (if applicable)
    - Overall UX trust
    - Right levers exposed?
    - Willingness to jump

16. **Activation and retention**  
    - Activation intent
    - Activation blockers
    - Retention confidence
    - Retention risk

17. **Monetization and rate acceptance**  
    - Processing rate context and acceptance (slider)
    - Rate vs zero fees tradeoff
    - SaaS willingness (optional)

18. **Final synthesis**  
    - Overall appeal rating
    - Main benefit (open-ended)
    - Main concern (open-ended)
    - Recommendation likelihood
    - Final verbatim

---

# 10. DETAILED QUESTIONNAIRE

[To be created by another agent based on sections 0-9 above]

---

# END OF SURVEY SPECIFICATION (Sections 0-9)
