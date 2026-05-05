# Mock Pack — Quick Reference

## All Mocks

| # | Mock Name | Primary Purpose | Model(s) Covered | Audience | Key Research Question |
|---|-----------|-----------------|------------------|----------|----------------------|
| 01 | Customer Price Comparison | Show customer-facing pricing differences across models | A, B, C | Merchant | Which pricing reality feels most natural? |
| 02 | Pricing Transparency | Show shelf → checkout → receipt consistency | A, B | Merchant + Customer proxy | Will customers perceive this as transparent? |
| 03 | Merchant Setup Summary: Model A | Show merchant-facing setup, limitations, and disclosures for Model A | A | Merchant | Can I operate Model A given debit inconsistency? |
| 04 | Merchant Setup Summary: Model B | Show merchant-facing setup, calculation trust, and pricing control for Model B | B | Merchant | Do I trust system-calculated pricing? |
| 05 | Channel Matrix | Show channel-based model selection and composition | C (A+B) | Merchant | Do I think differently about POS vs online/invoice? |
| 06 | Manual Entry Edge Case | Show manual entry workflow and pricing behavior | A, B | Merchant (services, invoice-heavy) | Does this work outside catalog/register flows? |
| 07 | Coverage and Economics | Show realistic fee offset by model and payment mix | A, B, C | Merchant | Is partial coverage acceptable or dealbreaker? |
| 08 | Explanation Helper | Show staff/customer explanation scripts | A, B, C | Merchant + Staff proxy | Can my staff explain this consistently? |

---

## By Model Focus

### Model A Focused
- Mock 03 — Merchant Setup Summary: Model A
- Mock 06 — Manual Entry Edge Case (Model A variant)

### Model B Focused
- Mock 04 — Merchant Setup Summary: Model B
- Mock 06 — Manual Entry Edge Case (Model B variant)

### Model C Focused
- Mock 05 — Channel Matrix

### All Models
- Mock 01 — Customer Price Comparison
- Mock 02 — Pricing Transparency
- Mock 07 — Coverage and Economics
- Mock 08 — Explanation Helper

---

## By Audience

### Merchant Decision-Maker
All mocks

### Staff / Operations
- Mock 06 — Manual Entry
- Mock 08 — Explanation Helper

### Customer Proxy
- Mock 01 — Price Comparison
- Mock 02 — Pricing Transparency

---

## By Survey Section Alignment

| Survey Section | Supported By Mocks |
|----------------|-------------------|
| Section C — Headline reaction | 01, 07 |
| Section D — Constraint tolerance | 01, 02 |
| Section E — Model A | 01, 02, 03, 06, 08 |
| Section F — Model B | 01, 02, 04, 06, 08 |
| Section G — Channel-based (Model C) | 05 |
| Section H — Model comparison | 01, 07 |
| Section I — Language/terminology | 08 |
| Section J — Setup preference, trust | 04 |
| Section K — Manual entry | 06 |
| Section L — Activation/retention | 03, 04, 07, 08 |
| Section M — Monetization | 07 |

---

## By Strategic Tension

| Tension | Mock |
|---------|------|
| Posted price vs final price | 01, 02 |
| Simplicity vs coverage | 03, 07 |
| Control vs convenience | 04 |
| Consistency vs context-optimization | 05 |
| Structured vs unstructured workflows | 06 |
| Headline promise vs economic reality | 07 |
| Merchant understanding vs customer understanding | 08 |

---

## Suggested Mock Sequences

### Sequence 1: Economics → Models → Operations
1. Mock 07 (economics)
2. Mock 01 (comparison)
3. Mock 03 or 04 (setup)
4. Mock 06 (manual entry)
5. Mock 08 (explanation)

### Sequence 2: Models → Transparency → Operations
1. Mock 01 (comparison)
2. Mock 02 (transparency)
3. Mock 03 and 04 (both setups)
4. Mock 05 (channel thinking)
5. Mock 08 (explanation)

### Sequence 3: Problem → Solution → Reality Check
1. Mock 07 (show the pain)
2. Mock 03 or 04 (show the solution)
3. Mock 02 (transparency check)
4. Mock 06 (edge case check)
5. Mock 08 (operability check)

---

## Files

### HTML Mocks
- `mock_01_price_comparison.html`
- `mock_02_pricing_transparency.html`
- `mock_03_merchant_setup_model_a.html`
- `mock_04_merchant_setup_model_b.html`
- `mock_05_channel_matrix.html`
- `mock_06_manual_entry.html`
- `mock_07_coverage_economics.html`
- `mock_08_explanation_helper.html`

### Shared Assets
- `styles.css`

### Documentation
- `README.md`
- `mock_strategy.md`
- `mock_list.md` (this file)
- `copy_deck.md`
