# Zero Fees Validation Survey — Full Execution Spec

## Status
Draft for execution after review against `00_context.md`

## Companion document
This file depends on:
- `00_context.md`

This file must not redefine terms inconsistently with `00_context.md`.

---

# 0. PURPOSE OF THIS DOCUMENT

This document specifies the research survey for validating a "zero fees" payments strategy.

This is not a generic concept survey.

This survey exists to answer a very specific strategic question:

> Can a "0% credit card processing fees" positioning, paired with one or more concrete pricing models, drive meaningful merchant switching, activation intent, retention intent, and monetization potential without relying on impossible or non-compliant behavior?

This survey is meant to produce signal strong enough to influence:
- product strategy
- pricing strategy
- GTM positioning
- sequencing of surfaces
- whether to build, narrow, or stop

This document is written so that:
- a researcher can field the survey
- a PM can understand what it is testing
- a designer can understand what scenarios are being shown
- an LLM can execute on it with minimal interpretation drift

---

# 1. WHAT THIS SURVEY IS TRYING TO LEARN

This survey is trying to learn all of the following:

## 1.1 Messaging fit
Does the headline:
- "0% credit card processing fees"

actually create strong merchant interest?

Not vague interest. Not "sounds nice."

Specifically:
- does it make merchants willing to explore switching?
- does it create expectations that are compatible or incompatible with real product behavior?

---

## 1.2 Pricing-model fit
Which pricing model feels workable enough that a merchant would actually run their business that way?

The survey tests these primary pricing realities:

### Model A — Credit Fee Model
Merchant keeps base visible prices low.  
Credit transactions pay a visible fee.  
Debit and cash do not.

### Model B — Prices Include Fees + Cash/ACH Discount
Merchant posts a fee-inclusive price.  
System helps calculate that price.  
Customers can pay less with cash and/or ACH.

### Model C — Channel-Based Decision Layer
Merchant may want different pricing approaches for:
- in person
- invoice
- online

Model C is not a standalone pricing model.  
Model C is a decision framework about whether merchants want:
- one pricing model everywhere
or
- different models by channel

For channel-based thinking:
- POS can use Model A or Model B
- invoice/online can use Model A, Model B, or convenience fee

---

## 1.3 Constraint tolerance
Will merchants accept the real constraints that come with these models?

Especially:
- pre-tender pricing requirements
- debit cannot be surcharged
- higher posted prices vs lower posted prices + visible fee
- consistency between posted prices and charged prices
- operational issues in manual entry workflows

---

## 1.4 Merchant mental model alignment
Which of the pricing realities feels most natural to merchants?

This matters because merchant adoption depends not only on economics, but on whether the model fits how they think about running their business.

Examples:
- "customers pay the fee"
- "my prices already include the cost"
- "cash gets a better deal"
- "online is different from in-person"
- "just lower my costs and don't change pricing"

---

## 1.5 Setup and system trust
If merchants like a pricing model, how do they want to configure it?

This is secondary to pricing-model preference, but still important.

Examples:
- guided recommendation
- single model everywhere
- choose by channel
- manual control
- system-calculated markup with edit rights

---

## 1.6 Retention reality
A model may look attractive on first glance and still be poor for long-term use.

This survey must distinguish:
- switching intent
- activation intent
- retention confidence

A model with strong switching but weak retention is not a full win.

---

## 1.7 Monetization potential
If merchants want the product, how do they want to pay for it?

This survey must test both:
- SaaS willingness to pay
- willingness to accept higher processing economics if total merchant outcome is good

---

# 2. WHAT THIS SURVEY IS NOT

This survey is NOT trying to prove that merchants like low fees.

That is already too obvious to be useful.

This survey is NOT trying to collect vanity signal such as:
- "this sounds good"
- "I like this idea"
- "lower fees are attractive"

This survey is NOT testing:
- abstract product enthusiasm
- UI preference
- impossible adaptive logic
- post-tender pricing changes

This survey is NOT allowed to:
- imply debit can be surcharged
- imply the system will dynamically change price after card type is known
- quietly assume embedded pricing as fallback
- hide complexity in order to make a model look cleaner

---

# 3. HARD CONSTRAINTS — MUST BE PRESERVED IN EVERY QUESTION AND SCENARIO

Every scenario, mockup, example, and question must respect all of the following.

## 3.1 Pre-tender pricing rule
The customer must see either:
- final price
or
- clear pricing logic

before payment.

The system cannot decide the final price after the payment method is presented, except in the specific case of surcharge where a disclosed fee is part of the model.

---

## 3.2 Card-type unknown rule
Credit vs debit is not known when the merchant is posting prices or when the customer first sees the pricing model.

Therefore:
- constructs cannot rely on hidden logic that changes behavior once the card is known
- the merchant-facing pricing model must make sense before card presentation

---

## 3.3 Debit rule
Debit cannot be surcharged.

Do not show or imply debit surcharge in any scenario.

---

## 3.4 Transparency rule
No hidden fallback logic.
No post-tender "surprise" price changes.
No undisclosed pricing transformations.

---

## 3.5 Surface rule
Convenience fee is relevant to:
- invoice
- online

It is not a POS model.

---

## 3.6 Posted-price consistency rule
If testing embedded/list-price models, remember:
- a merchant cannot advertise one lower shelf/menu price and then charge a higher embedded price at the till
- the posted/list/menu price has to be the price the customer sees as the standard price

Discounting can be tested, but the survey must not accidentally normalize deceptive presentation.

---

# 4. PRIMARY HYPOTHESES THIS SURVEY SHOULD HELP EVALUATE

These hypotheses are inherited from the context and sharpened for survey use.

## H1
A combination of:
- "0% fees" messaging
and
- the right pricing model

can drive strong merchant switching intent.

## H2
The winning pricing model may differ from the winning headline.

## H3
Model A and Model B represent fundamentally different tradeoffs:
- Model A: lower posted prices + visible fee
- Model B: higher posted prices + no surprise fee

## H4
Some merchants will prefer one model everywhere; others will prefer channel-based differences.

## H5
Invoice/online may work as a wedge, but wedge success alone is not enough unless it plausibly translates to the larger POS / GPV opportunity.

## H6
Trust in system-calculated markup is a key gating factor for Model B.

## H7
Debit mix and cash mix materially influence whether merchants perceive a model as a true "zero fee" solution.

## H8
Monetization viability depends not just on savings, but on confidence, trust, and perceived durability.

---

# 5. SUCCESS CRITERIA FOR THIS SURVEY

The survey is useful if it can identify whether at least one pricing path clears the thresholds below.

## 5.1 Primary success threshold
At least one model produces:
- 50% or greater switching intent

This does not mean the whole strategy is proven.
It means there is enough signal to investigate further.

---

## 5.2 Secondary thresholds
At least one model produces:
- 50% or greater activation intent
- meaningful retention confidence
- willingness to pay via SaaS and/or pricing economics

---

## 5.3 Failure / kill interpretation
If all of the following are weak:
- switching intent
- activation intent
- willingness to pay

then the strategy should be narrowed or reconsidered.

---

# 6. SURVEY METHOD PRINCIPLES

## 6.1 Use concrete scenarios
Do not ask abstract questions where a concrete scenario can be shown.

## 6.2 Ask behavior-facing questions
Prefer:
- "Would you run your business this way?"
- "Would you switch providers for this?"

Avoid:
- "Do you like this?"
- "Does this sound useful?"

## 6.3 Separate attraction, activation, and retention
Each needs distinct measurement.

## 6.4 Capture segmenting information early
Collect awareness stage, vertical, ticket size, channel mix, and decision role before model comparisons.

## 6.5 Keep models fair
Do not show one model in more favorable or more detailed language than another.

## 6.6 Force tradeoffs
Every pricing model must be shown with its downside.

---

# 7. TARGET RESPONDENTS

This survey is best used on merchants or merchant prospects who are:
- SMBs, ideally concentrated near the core target range
- decision makers or meaningful influencers in payment/pricing choice
- operating on at least one relevant surface:
  - POS
  - invoice/paylink
  - online

---

# 8. REQUIRED OUTPUTS FROM THE SURVEY

The survey analysis must produce all of the following.

## 8.1 By pricing model
For Model A, Model B, and channel-based preference:
- naturalness
- switching intent
- willingness to run the business that way
- retention confidence
- major objections
- trust level
- staff-operability confidence
- monetization willingness

## 8.2 By segment
Cut results by S0–S5.

## 8.3 By merchant attributes
Cut results by:
- vertical
- revenue band
- ticket size
- decision-maker role
- channel mix
- debit sensitivity
- cash sensitivity

## 8.4 Decision outputs
The readout must answer:
- Which model wins on switching?
- Which model wins on long-term use?
- Is there a meaningful segment split?
- Is channel-based pricing real or just theoretical?
- Is invoice/online only a wedge, or part of a broader viable strategy?
- Is SaaS monetization viable?
- Is pricing-based monetization viable?

---

# 9. FULL SURVEY FLOW

The survey should be structured in this exact order.

1. Qualification and segmentation  
2. Current state and fee sensitivity  
3. Headline reaction  
4. Meaning / expectation of "zero fees"  
5. Constraint tolerance  
6. Model A scenario  
7. Model B scenario  
8. Channel-based thinking (Model C decision layer)  
9. Model comparison and tradeoffs  
10. Language and terminology  
11. Setup preference and markup-calculation trust  
12. Manual entry behavior  
13. Activation and retention  
14. Monetization  
15. Final synthesis

Do not reorder unless there is a very strong reason.

---

# 10. DETAILED QUESTIONNAIRE

## SECTION A — QUALIFICATION AND SEGMENTATION

### A1. Industry
**Question:** Which best describes your business?

- restaurant / cafe
- retail
- services
- other

**Why this matters:**  
Vertical likely affects:
- tolerance for fee visibility
- price competition
- staff explanation burden
- customer expectations

---

### A2. Annual revenue
**Question:** Which best describes your annual revenue?

- under $300K
- $300K–$1M
- $1M–$5M
- over $5M

**Why this matters:**  
Core target concentration and ability to compare smaller vs larger SMBs.

---

### A3. Channel mix
**Question:** Where do you take payments today?

- mostly in person
- mostly invoices / paylinks
- mostly online
- mix of in person, invoice/paylink, and/or online

**Why this matters:**  
Channel mix is required for interpreting Model C and wedge viability.

---

### A4. Typical ticket size
**Question:** Which best describes your typical transaction size?

- mostly under $25
- mostly $25–$100
- mostly $100–$500
- mostly over $500

**Why this matters:**  
Ticket size changes:
- visible fee tolerance
- convenience-fee tolerance
- posted-price sensitivity

---

### A5. Role in decision making
**Question:** Which best describes your role in payments/pricing decisions?

- I make the final decision
- I strongly influence the decision
- I provide input but do not decide
- I am not involved in this decision

**Usage note:**  
Respondents with no decision role may still be useful for directional feedback but should be analyzed separately or filtered.

---

### A6. Awareness / behavior stage
**Question:** When it comes to payment processing fees, where are you today?

- I do not think about them much
- I know fees matter, but I have not acted
- I casually explore options from time to time
- I am actively comparing providers or setups
- I need to fix this now
- I already optimize this actively

**Maps to:**  
- S0
- S1
- S2
- S3
- S4
- S5

**Why this matters:**  
This is a primary segmentation variable, not a nice-to-have.

---

## SECTION B — CURRENT STATE AND SENSITIVITY

### B1. Current approach
**Question:** Which best describes how you handle processing fees today?

- I absorb them and keep pricing the same
- I use or have used a credit-card fee / surcharge approach
- I build the cost into prices
- I handle it differently by channel
- not sure / mixed

**Why this matters:**  
Current state influences both openness and resistance.

---

### B2. Current urgency
**Question:** How important are payment processing fees to you right now?

- critical
- important
- somewhat important
- not very important

**Why this matters:**  
Distinguishes mild interest from active motivation.

---

### B3. Debit sensitivity
**Question:** How important is correct debit handling in any fee/pricing setup?

- critical
- important
- somewhat important
- not important

**Why this matters:**  
Model A weakness and broader trust variable.

---

### B4. Cash sensitivity
**Question:** How important is your cash mix in deciding whether a pricing model works for you?

- critical
- important
- somewhat important
- not important

**Why this matters:**  
Model B and discount-based logic depend on this.

---

### B5. Current payment mix
**Question:** Approximately what percentage of your transactions are paid with each method today?

- Credit cards: ____%
- Debit cards: ____%
- Cash: ____%
- ACH/bank transfer: ____%

**Why this matters:**  
Baseline payment mix is critical for understanding coverage gaps (Model A doesn't cover debit) and discount economics (Model B benefits from cash/ACH shift). This data segments merchants by current reality.

---

### B6. Expected payment shift
**Question:** If you offered a discount for cash or ACH payments, how much do you think your cash/ACH volume would increase?

- significantly (10%+ shift to cash/ACH)
- moderately (5-10% shift to cash/ACH)
- slightly (1-5% shift to cash/ACH)
- not at all
- not sure

**Why this matters:**  
Model B's economics depend on whether merchants believe customers will actually shift payment methods. Unrealistic expectations could lead to activation without retention.

---

## SECTION C — HEADLINE REACTION

### C1. Headline appeal
**Question:** How compelling is this offer?

**Stimulus:**  
“0% credit card processing fees”

- very compelling
- somewhat compelling
- not very compelling
- not compelling at all

**What this measures:**  
Top-of-funnel attractiveness only.

---

### C2. Exploration intent
**Question:** Based on that claim alone, would you explore switching providers?

- yes
- maybe
- no

**What this measures:**  
Early acquisition pull before model reality.

---

### C3. Meaning expectation
**Question:** What do you think “0% credit card processing fees” most likely means?

- customers pay a visible fee
- prices are higher and fees are built in
- it depends on channel or payment method
- the provider absorbs the cost
- not sure

**Why this matters:**  
Captures expectation before reality is shown.

---

### C4. Zero fees value proposition depth
**Question:** How important is achieving “zero processing fees” to your business?

- extremely important — I would change my pricing to achieve it
- very important — worth exploring different approaches
- somewhat important — nice to have but not a priority
- not important — I care more about other factors

**Why this matters:**  
Tests whether “zero fees” is compelling enough to justify trade-offs like higher posted prices or pricing model changes. This distinguishes genuine willingness from casual interest.

---

### C5. Switching motivation
**Question:** If a payment provider could help you achieve zero processing fees, which best describes your level of interest?

- I would strongly consider switching providers
- I would explore it if the setup is straightforward
- I would be interested but skeptical about trade-offs
- I'm not interested in switching

**Why this matters:**  
Measures switching intent strength before exposing model details and constraints.

---

## SECTION D — CONSTRAINT TOLERANCE

### D1. Pre-tender pricing acceptance
**Question:** How acceptable is this rule to you?

**Stimulus:**  
“Prices must be defined before payment. They cannot change after the card is presented.”

- fully acceptable
- acceptable with clear setup
- somewhat problematic
- not acceptable

---

### D2. Debit handling expectation
**Question:** If debit cards cannot be charged a surcharge, what feels most workable to you?

- keep debit at the lower/base price
- raise prices so all card transactions are covered
- offer discounts for cash and/or ACH instead
- not sure

**Why this matters:**  
Surfaces natural fallback expectations without assuming them.

---

### D3. Different prices by payment type
**Question:** How acceptable is it if customers pay different amounts depending on how they pay?

- very acceptable
- somewhat acceptable
- somewhat unacceptable
- very unacceptable

---

### D4. Posted price vs checkout price
**Question:** Which is closest to your view?

- posted price and charged price should always match
- they can differ if a fee is clearly disclosed
- they can differ if a discount is clearly disclosed
- depends on the pricing model

---

### D5. Main risk perception
**Question:** What feels riskiest to you?

- visible fee at checkout
- higher posted prices
- staff confusion
- compliance / disclosure risk
- not sure

---

## SECTION E — MODEL A: CREDIT FEE MODEL

### E0. Scenario framing
**Instruction to respondent:**  
Please answer based on whether you would actually run your business this way.

### E1. Scenario
**Stimulus:**  
Posted/menu price: $100  
If customer pays with credit card: $103  
If customer pays with debit card: $100  
If customer pays with cash: $100

The customer sees the base price first and sees that credit card payments include a fee.

---

### E2. Naturalness
**Question:** How natural does this feel for how you would run your business?

- very natural
- somewhat natural
- somewhat unnatural
- very unnatural

---

### E3. Adoption
**Question:** Would you run your business this way?

- yes
- maybe
- no

---

### E4. Switching
**Question:** Would this make you more likely to switch providers if it worked as shown?

- yes
- maybe
- no

---

### E5. Main concern
**Question:** What concerns you most about this model?

- customer reaction to visible fee
- debit inconsistency
- compliance / signage
- staff explanation
- nothing major

---

### E6. Customer expectation fit
**Question:** How well do you think your customers would understand this pricing approach?

- very well
- somewhat well
- somewhat poorly
- very poorly

---

## SECTION F — MODEL B: PRICES INCLUDE FEES + CASH/ACH DISCOUNT

### F1. Scenario
**Stimulus:**  
Posted/menu price: $103  
If customer pays with credit card: $103  
If customer pays with debit card: $103  
If customer pays with cash: $100  
If customer pays with ACH: $100

The system helps calculate the posted price so the merchant keeps their target margin.  
Customers can pay less with cash and/or ACH.

---

### F2. Naturalness
**Question:** How natural does this feel for how you would run your business?

- very natural
- somewhat natural
- somewhat unnatural
- very unnatural

---

### F3. Trust in calculated pricing
**Question:** How comfortable are you with the system calculating the posted price for you?

- very comfortable
- somewhat comfortable
- somewhat uncomfortable
- very uncomfortable

---

### F4. Adoption
**Question:** Would you run your business this way?

- yes
- maybe
- no

---

### F5. Switching
**Question:** Would this make you more likely to switch providers if it worked as shown?

- yes
- maybe
- no

---

### F6. Main concern
**Question:** What concerns you most about this model?

- higher visible prices
- trusting the calculated markup
- customer confusion about discounts
- compliance / posted-price rules
- nothing major

---

### F7. Customer expectation fit
**Question:** How well do you think your customers would understand this pricing approach?

- very well
- somewhat well
- somewhat poorly
- very poorly


---

## SECTION F2 — PRICING DISPLAY & OPERATIONAL IMPACT (MODEL B REALITY CHECK)

This section tests the real-world implications of Model B that are not immediately obvious from the pricing logic alone.

Model B requires:
- higher posted prices (fee-inclusive)
- consistent pricing across all customer-facing surfaces
- explicit discount logic for cash/ACH
- correct implementation across menus, shelves, websites, and invoices

This section exists to measure:
- operational burden
- compliance confidence
- likelihood of implementation errors
- whether this becomes a blocking factor for adoption

---

### F2.1 — Price display approach

**Question:**  
If you use a pricing model where fees are built into prices, how would you prefer to display prices?

- One price (higher), with discounts applied at payment (cash/ACH)
- Two prices shown everywhere (card price and cash price)
- Depends on the channel (e.g. one approach in-store, another online)
- Not sure

**Why this matters:**  
This determines whether merchants naturally lean toward:
- single-price embedded models
- dual pricing models
- or channel-dependent hybrids

---

### F2.2 — Operational burden of updating prices

**Question:**  
How difficult would it be for you to update your pricing everywhere (menus, shelves, website, etc.) to reflect a new pricing structure?

- Very easy
- Somewhat easy
- Somewhat difficult
- Very difficult

**Why this matters:**  
Model B requires updating all visible prices.  
This is often underestimated and can be a primary adoption blocker.

---

### F2.3 — Compliance confidence

**Question:**  
How confident are you that you would implement this correctly across all surfaces?

- Very confident
- Somewhat confident
- Not very confident
- Not confident at all

**Why this matters:**  
Incorrect implementation creates:
- customer trust issues
- regulatory risk
- inconsistent experiences

---

### F2.4 — Adoption blocker

**Question:**  
Would the requirement to update all displayed prices stop you from adopting this model?

- Yes
- Maybe
- No

**Why this matters:**  
Directly tests whether Model B fails due to operational burden rather than pricing logic.

---

### F2.5 — Most difficult surface

**Question:**  
Where would updating pricing be most difficult?

- In-store menus or shelf labels
- Website or online ordering
- Invoices / paylinks
- Keeping everything consistent across all surfaces
- Not sure

**Why this matters:**  
Identifies where product support or tooling would be required.

---

### F2.6 — Dual pricing clarity

**Question:**  
If two prices are shown (e.g. card price and cash price), how clear do you think that would be to your customers?

- Very clear
- Somewhat clear
- Somewhat confusing
- Very confusing

**Why this matters:**  
Dual pricing may reduce surprise but increase cognitive load.

---

### F2.7 — Preference vs friction tradeoff

**Question:**  
Which would you prefer, even if it requires more effort?

- One higher posted price with discounts at payment
- Two prices shown everywhere (card vs cash)
- Depends on context
- Not sure

**Why this matters:**  
Forces a tradeoff between:
- operational simplicity
- pricing transparency


---

## SECTION G — MODEL C: CHANNEL-BASED THINKING

Important: this section is testing whether merchants want a different pricing model by channel. It is not presenting Model C as a standalone pricing mechanism.

### G1. Channel mindset
**Question:** Do you think about pricing differently by channel?

- yes, in-person and online/invoice should be handled differently
- maybe, depending on the business
- no, pricing should be handled consistently everywhere

---

### G2. POS model preference
**Question:** For in-person payments, which approach feels more appropriate?

- Model A — lower posted price + credit fee
- Model B — posted prices include fees + cash/ACH discount
- not sure

---

### G3. Online / invoice model preference
**Question:** For online or invoice payments, which approach feels more appropriate?

- Model A — visible card fee
- Model B — prices include fees + cash/ACH discount
- convenience fee
- not sure

---

### G4. Why that combination makes sense
**Question:** Why does this combination make sense to you?

- customers expect different behavior online vs in person
- easier to explain
- better economics
- matches how my business already works
- not sure

---

### G5. Channel-based adoption
**Question:** Would you run your business using different pricing models by channel?

- yes
- maybe
- no

---

### G6. Channel-based switching
**Question:** Would a channel-based approach make you more likely to switch providers?

- yes
- maybe
- no

---

### G7. Main concern
**Question:** What concerns you most about using different pricing by channel?

- customer confusion
- staff confusion
- hard to manage
- compliance concerns
- no major concerns

---

## SECTION H — MODEL COMPARISON AND TRADEOFFS

### H1. Most realistic
**Question:** Which approach feels most realistic for your business?

- Model A
- Model B
- a mix depending on channel
- not sure

---

### H2. Strongest switching driver
**Question:** Which approach would most likely make you switch providers?

- Model A
- Model B
- a mix depending on channel
- none of these

---

### H3. Best long-term fit
**Question:** Which approach would you be most likely to use long term?

- Model A
- Model B
- a mix depending on channel
- not sure

---

### H4. Core tradeoff preference
**Question:** Which tradeoff would you choose?

- lower posted prices + visible fee
- higher posted prices + no surprise fee
- different pricing by channel
- not sure

---

### H4a. Willingness to raise prices for zero fees
**Question:** If raising your posted prices by 3% would allow you to achieve zero processing fees on all card transactions (credit and debit), would you do it?

**Context provided:**  
"You would keep the same net revenue per sale. Customers who pay with cash or ACH would get a discount, paying your current price. Card customers would pay the higher price."

- yes, I would raise prices to achieve zero fees
- yes, but only if the provider helps me calculate the right prices
- maybe, depending on how it affects customer perception
- no, I prefer to keep lower posted prices even if I pay fees on debit
- not sure

**Why this matters:**  
This is the core question distinguishing Model A (lower prices + surcharge with gaps) from Model B (higher prices + true zero fees). It tests whether "zero fees" is compelling enough to accept higher shelf/menu prices, which is the fundamental trade-off.

---

### H4b. Model A limitations acceptance
**Question:** If you chose Model A (lower posted prices with a credit card fee), how acceptable is it that you would still pay processing fees on debit card transactions?

**Context provided:**  
"Credit card fees would be passed to customers. Debit cards cannot be surcharged by law, so you would continue to pay processing fees on debit transactions (typically 1.5-2% of debit volume)."

- fully acceptable — debit fees are small enough
- somewhat acceptable — I prefer lower posted prices despite this gap
- somewhat problematic — I thought zero fees meant all cards
- not acceptable — this defeats the purpose

**Why this matters:**  
Tests whether merchants understand and accept Model A's inherent limitation (debit coverage gap) or whether "zero fees" messaging creates expectation mismatch.

---

### H5. "Zero fees" threshold
**Question:** When would you consider a program like this to legitimately feel like “zero fees”?

- only if nearly all transactions are covered
- if most transactions are covered
- if savings are meaningful even if coverage is partial
- depends on how it is explained

---

## SECTION I — LANGUAGE AND TERMINOLOGY

This section matters because market language, merchant understanding, and search behavior all matter.

### I1. Credit-fee language
**Question:** Which phrasing feels clearer?

- card fee
- surcharge
- both are equally clear
- neither is clear

---

### I2. Embedded/discounte language
**Question:** Which phrasing feels clearer?

- prices include fees, pay less with cash/ACH
- cash discount
- both are equally clear
- neither is clear

---

### I3. Naming style preference
**Question:** If evaluating a provider, which naming style would you prefer?

- industry terms
- plain-language explanation
- both together
- no preference

---

## SECTION J — SETUP PREFERENCE AND CALCULATION TRUST

Important: this section comes after model preference, because setup should not overshadow the core pricing choice.

### J1. Setup preference
**Question:** If you chose one of these approaches, how would you prefer to set it up?

- tell me what to do and recommend a setup
- let me choose one model for everything
- let me choose by channel
- let me edit the details myself
- not sure

---

### J2. Markup calculation preference
**Question:** If posted prices need to be calculated to preserve your margin, what would you want?

- system calculates it for me
- system recommends it but I can edit
- I want to set it manually
- not sure

---

### J3. Trust breaker
**Question:** What would most reduce your trust in the setup?

- not knowing how pricing was calculated
- not being able to edit it
- seeing prices that feel too high
- unclear customer communication
- something else

---

## SECTION K — MANUAL ENTRY / NON-CATALOG WORKFLOW

This section is important because manual entry may behave differently from register/catalog flows.

### K1. Manual-entry frequency
**Question:** How often do you manually enter an amount and card details without a standard register/catalog workflow?

- very often
- sometimes
- rarely
- never

---

### K2. Manual-entry expectation
**Question:** In a manual-entry workflow, what would you expect to enter?

- the base amount
- the final amount the customer pays
- I would expect the system to guide me
- not sure

---

### K3. Customer visibility in manual entry
**Question:** In a manual-entry workflow, what should the customer see before paying?

- final price only
- final price plus explanation
- different options by payment type
- depends on the pricing model

---

### K4. Manual-entry importance
**Question:** How much does manual entry affect whether a pricing model is workable for you?

- a lot
- somewhat
- very little
- not at all

---

## SECTION L — ACTIVATION AND RETENTION

### L1. Activation intent
**Question:** Which approach would you be most willing to turn on this week?

- Model A
- Model B
- a mix depending on channel
- none

---

### L2. Retention confidence
**Question:** Which approach would you be most willing to rely on as your primary way of handling payment costs?

- Model A
- Model B
- a mix depending on channel
- none

---

### L3. Staff-operability
**Question:** Which approach do you think your staff would understand and apply most consistently?

- Model A
- Model B
- a mix depending on channel
- not sure

---

### L4. Customer reaction risk
**Question:** Which approach feels riskiest from a customer-reaction standpoint?

- Model A
- Model B
- a mix depending on channel
- they feel equally risky

---

### L5. Minimum worthwhile coverage
**Question:** What minimum level of fee offset would make this worthwhile to you?

- at least 25%
- at least 50%
- at least 75%
- nearly all transactions
- depends on economics

---

## SECTION M — MONETIZATION

### M1. SaaS willingness to pay
**Question:** If one of these approaches saved you meaningful money and worked reliably, what monthly software fee would feel acceptable?

- $0
- $1–49
- $50–99
- $100–249
- $250+
- depends on savings

---

### M2. Pricing-based monetization tolerance
**Question:** Would you accept slightly higher processing rates if the setup delivered meaningful fee reduction and was easy to use?

- yes
- maybe
- no

---

### M3. Monetization preference
**Question:** Which would you prefer?

- pay via SaaS
- pay via pricing / processing economics
- depends on total economics
- neither

---

### M4. Confidence needed before paying
**Question:** If this became your primary system for handling fees, how confident would you need to be before paying for it?

- low confidence is fine if economics are good
- moderate confidence
- high confidence
- very high confidence / nearly certain

---

## SECTION N — FINAL SYNTHESIS

### N1. Best overall path
**Question:** Which feels like the best overall approach for your business?

- Model A
- Model B
- a mix depending on channel

---

### N2. Main reason
**Question:** Why did you choose that?

- best economics
- best customer experience
- easiest to explain
- simplest to operate
- feels safest / most compliant

---

### N3. Overall switching likelihood
**Question:** Overall, how likely are you to switch based on your preferred approach?

- very likely
- somewhat likely
- somewhat unlikely
- very unlikely

---

# 11. ANALYSIS PLAN

The analysis must not stop at overall percentages.

## 11.1 Segment cuts
Cut all critical model measures by:
- S0
- S1
- S2
- S3
- S4
- S5

## 11.2 Merchant-attribute cuts
Cut by:
- vertical
- revenue band
- ticket size
- decision role

## 11.3 Surface / channel cuts
Cut by:
- POS-heavy
- invoice-heavy
- online-heavy
- mixed

## 11.4 Sensitivity cuts
Cut by:
- debit sensitivity
- cash sensitivity

## 11.5 Key dependent variables
For each model or approach:
- naturalness
- adoption
- switching
- staff-operability
- retention confidence
- monetization willingness

---

# 12. REQUIRED READOUT QUESTIONS

The final readout must answer these explicitly:

1. Which model wins on switching?
2. Which model wins on long-term use?
3. Is the same model winning across segments, or is there a segment split?
4. Are merchants naturally single-model or channel-based?
5. Is invoice/online a wedge only, or plausibly a broader strategy component?
6. Are merchants more attracted to:
   - lower visible prices + visible fee
   - higher visible prices + no surprise fee
   - channel-based mixture
7. Is markup calculation trust a major blocker for Model B?
8. Is willingness to pay sufficient for product investment?
9. Is pricing-based monetization more acceptable than SaaS, or vice versa?
10. Where do manual-entry workflows break the model?

---

# 13. DISALLOWED QUESTION TYPES

Do not use:
- “Would you like zero fees?”
- “Does this sound good?”
- “Would this be useful?”
- any question that hides the downside of a model
- any scenario that implies debit surcharge
- any scenario that uses impossible post-tender behavior
- any scenario that hides pricing changes until after payment selection

---

# 14. QUALITY-CONTROL CHECKLIST BEFORE FIELDING

Before launching the survey, verify all of the following:

- Model A shows the debit inconsistency clearly
- Model B shows higher posted prices clearly
- Model C is framed as a channel choice, not a fake standalone pricing model
- no model benefits from extra explanation or cleaner visuals than the others
- all scenarios honor pre-tender pricing
- no hidden fallback logic is implied
- manual entry is covered
- both SaaS and pricing monetization are tested
- switching, activation, and retention are measured separately

---

# 15. WHAT GOOD OUTPUT LOOKS LIKE

## Good output example
“Among S3 and S4 POS-heavy merchants, Model A creates the strongest switching pull, especially in lower-ticket contexts, but Model B creates stronger willingness to rely on it long term and stronger SaaS willingness to pay among operators who are comfortable with system-calculated pricing. Mixed-channel merchants show real openness to channel-based combinations, especially with convenience fee online/invoice, but staff and complexity concerns remain high.”

## Bad output example
“Merchants liked zero fees.”
“Model B performed well.”
“People want lower costs.”

The final readout must be specific enough to directly inform:
- GTM message
- pricing-model priority
- surface sequencing
- build/no-build decision