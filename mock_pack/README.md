# Zero Fees Mock Pack — README

## Purpose

This mock pack contains lightweight, high-signal HTML mocks for testing SMB merchant reactions to "zero fees" pricing models. These are research tools, not production UI or marketing materials.

## Files Created

### Documentation
- `README.md` — this file
- `mock_strategy.md` — strategic rationale for each mock
- `mock_list.md` — quick reference table of all mocks
- `copy_deck.md` — language and messaging reference for each model

### Visual Mocks (HTML)
- `mock_01_price_comparison.html` — Customer price comparison across models
- `mock_02_pricing_transparency.html` — Shelf/menu/site vs checkout consistency
- `mock_03_merchant_setup_model_a.html` — Merchant setup summary for Model A
- `mock_04_merchant_setup_model_b.html` — Merchant setup summary for Model B
- `mock_05_channel_matrix.html` — Channel-based model selection (Model C)
- `mock_06_manual_entry.html` — Manual entry edge case handling
- `mock_07_coverage_economics.html` — Coverage and economics summary
- `mock_08_explanation_helper.html` — Staff/customer explanation reference

### Shared Assets
- `styles.css` — shared styling for consistent presentation

## How to Use These Mocks

### Suggested Order for Research Sessions

**Option A — Model-First Approach**
1. Start with `mock_01_price_comparison.html` to establish the three models
2. Show `mock_02_pricing_transparency.html` to surface transparency concerns
3. Deep dive into Model A with `mock_03_merchant_setup_model_a.html`
4. Deep dive into Model B with `mock_04_merchant_setup_model_b.html`
5. Test channel thinking with `mock_05_channel_matrix.html`
6. Surface operational concerns with `mock_06_manual_entry.html`
7. Ground expectations with `mock_07_coverage_economics.html`
8. Test operability with `mock_08_explanation_helper.html`

**Option B — Economics-First Approach**
1. Start with `mock_07_coverage_economics.html` to establish savings potential
2. Show `mock_01_price_comparison.html` to introduce the models
3. Show `mock_03_merchant_setup_model_a.html` and `mock_04_merchant_setup_model_b.html` back-to-back
4. Test channel thinking with `mock_05_channel_matrix.html`
5. Surface operational concerns with `mock_06_manual_entry.html` and `mock_08_explanation_helper.html`
6. Return to transparency with `mock_02_pricing_transparency.html`

**Option C — Scenario-Driven**
Pick mocks based on merchant segment:
- For **S3/S4** (active switchers, pain-triggered): start with `mock_07_coverage_economics.html`
- For **S0/S1** (unaware, aware-inactive): start with `mock_01_price_comparison.html`
- For **S5** (optimizers): start with `mock_05_channel_matrix.html`

### Viewing the Mocks

Open each HTML file in a browser. No server required — these are static files with minimal JavaScript.

## What NOT to Conclude from These Mocks

❌ **Do not conclude** that these represent final product UI  
✅ These are research artifacts designed to expose tradeoffs

❌ **Do not conclude** that the visual design reflects brand direction  
✅ The design is intentionally neutral and spec-like

❌ **Do not conclude** that all edge cases are solved  
✅ These mocks focus on core model mechanics and key constraints

❌ **Do not conclude** that merchants will understand everything immediately  
✅ Confusion is signal — these mocks are designed to surface it

❌ **Do not conclude** that one model is "recommended" based on layout or prominence  
✅ All models are presented with equal fidelity to their tradeoffs

## Design Philosophy

These mocks are:
- **Constraint-aware**: Every scenario respects the hard rules from `00_context.md`
- **Tradeoff-explicit**: Each model's downsides are shown, not hidden
- **Comparably detailed**: No model gets unfair advantage through extra explanation
- **Operationally realistic**: Manual entry, staff explanation, and edge cases are included
- **Coverage-honest**: No overclaiming of "100% zero fees" unless warranted

## Key Numbers Used (for consistency)

- Base item price: **$100**
- Credit fee percentage: **3%**
- Model A credit card total: **$103**
- Model B posted price: **$103**
- Model B cash/ACH price: **$100**
- Debit card price: **$100** (Model A) or **$103** (Model B)

These numbers are used consistently across mocks unless context requires variation.

## Constraint Compliance

Every mock in this pack enforces:
1. ✅ Pre-tender pricing (price defined before payment method)
2. ✅ No post-card dynamic pricing
3. ✅ Debit cannot be surcharged
4. ✅ No hidden fallback behavior
5. ✅ Convenience fee only for online/invoice (not POS)
6. ✅ Posted price consistency for embedded pricing
7. ✅ Customer transparency before payment

## Research Questions Alignment

These mocks primarily support survey sections:
- **Mock 01**: Section C (headline), Section D (constraints), Section H (comparison)
- **Mock 02**: Section D (constraint tolerance)
- **Mock 03**: Section E (Model A), Section L (activation/retention)
- **Mock 04**: Section F (Model B), Section J (trust in calculation)
- **Mock 05**: Section G (Model C / channel-based thinking)
- **Mock 06**: Section K (manual entry)
- **Mock 07**: Section M (monetization), Section L (retention)
- **Mock 08**: Section L (staff operability), Section I (language)

## Feedback and Iteration

When using these mocks in research:
- Note which mocks generate the most questions
- Track which model representations feel clearest
- Identify where merchants get confused
- Document what language works better than other language
- Capture whether comparison format helps or hinders decision-making

These observations should inform both product strategy and the next iteration of research materials.
