# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a product strategy and research documentation project for a "Zero Fees" payment processing product offering. The goal is to validate whether a "0% credit card processing fees" positioning can drive merchant switching, activation, and retention while maintaining monetization viability.

## Core Documents

### 00_context.md - Master Context Document
The authoritative source for all product definitions, constraints, and rules. This document defines:

- **Business objectives**: Primary goal is increasing GPV through merchant switching using "0% credit card processing fees" positioning
- **Success criteria**: ≥50% merchant switching intent, willingness to pay (SaaS or higher processing rates), ≥50% activation intent
- **Kill criteria**: Switching intent <30% OR no willingness to pay
- **Critical definitions**: Surcharge, embedded pricing, convenience fee, coverage %, activation, retention
- **Product constructs**: Three main models (A: Credit Fee Model, B: Embedded Price + Discount, C: Channel-Based)
- **Hard constraints**: Pre-tender pricing, card-type unknowns, transparency rules, debit restrictions, no silent fallback

### 01_survey_execution.md - Survey Specification
Complete execution specification for the validation survey including:
- Full questionnaire with 15 sections (A-N)
- Target respondents, analysis plan, and required outputs
- Quality control checklist

### mock_pack/ - Research Materials
HTML mocks and documentation for merchant research sessions:
- Eight HTML mocks covering price comparison, transparency, setup flows, and edge cases
- `README.md` - usage guide with suggested research session flows
- `mock_strategy.md` - strategic rationale for each mock
- `copy_deck.md` - messaging and language reference

### Supporting Documents
- `Cash_Discounting_PRD.txt`, `Dual Pricing PRD.txt` - Additional product context
- `*.html` files - Prototypes and comparison tools for merchant testing
- `01_survey_execution_UPDATED.md` - Revised survey specification

## Critical Constraints (MUST BE ENFORCED)

When working on any content in this repository, the following constraints are **BLOCKING REQUIREMENTS**:

1. **Pre-Tender Pricing Constraint**: Final price must be known BEFORE payment method is presented. System cannot change price after card type is known.

2. **Card-Type Constraint**: Card type (credit vs debit) is UNKNOWN before presentation. System must define pricing BEFORE card is presented.

3. **Transparency Constraint**: Customer must see final price or clear pricing logic BEFORE payment method selection. Violation risks UDAAP / lack of transparency.

4. **Debit Rule**: Surcharge is NOT allowed on debit cards across all surfaces.

5. **No Silent Fallback**: System does NOT auto-correct or apply hidden fallback behavior. Merchant must explicitly select embedded pricing if used.

## Rules Matrix

### Credit Cards
- **POS**: surcharge allowed
- **Invoice**: surcharge OR convenience fee allowed
- **Online**: surcharge OR convenience fee allowed

### Debit Cards
- **POS**: embedded pricing OR no fee
- **Invoice**: embedded pricing OR convenience fee
- **Online**: embedded pricing OR convenience fee

### ACH
- **Invoice**: no fee OR convenience fee OR embedded discount
- **Online**: no fee OR convenience fee OR embedded discount

## Product Constructs

### Construct A - Credit Fee Model
- Base price shown upfront
- Credit transactions: base + fee
- Debit/cash: base price only
- Customer sees: "+X% for credit card payments"

### Construct B - Embedded Price + Discount Model
- Fee-inclusive price shown upfront (system-calculated)
- Credit/debit: full price
- Cash/ACH: discounted price
- Customer sees: "pay less with cash/ACH"

### Construct C - Channel-Based Model
- Different pricing models per surface (POS vs Invoice vs Online)
- Each channel must independently comply with constraints
- Not a standalone model, but a decision framework

## Segmentation Model

**Primary Segments** (S0-S5):
- S0: Unaware
- S1: Aware inactive
- S2: Curious
- S3: Active switcher
- S4: Pain-triggered
- S5: Optimizer

**Mandatory Dimensions**: Industry, ticket size, customer type

## Key Metrics

### Primary
- Switching intent (target: ≥50%)

### Secondary
- Willingness to pay (SaaS or higher processing rates)
- Activation intent (target: ≥50%)
- Retention confidence

### Coverage
- Percentage of transactions where fees are offset

## Document Consistency Rules

When editing or creating documents:

1. **No Contradictions**: Never redefine terms inconsistently with `00_context.md`
2. **Explicit References**: Always reference the master context when dependent
3. **No Assumptions**: Do NOT assume missing logic or add fallback behavior
4. **Enforce Transparency**: All pricing examples must show what customer sees BEFORE payment selection
5. **Invalid Rules Blocked**: Illegal configurations (e.g., debit surcharge) are BLOCKED, not auto-corrected

## Survey Quality Control

Before fielding any survey content, verify:
- Model A shows debit inconsistency clearly
- Model B shows higher posted prices clearly
- Model C framed as channel choice, not standalone model
- No model benefits from extra explanation vs others
- All scenarios honor pre-tender pricing
- No hidden fallback logic implied
- Manual entry workflows covered
- Both SaaS and pricing monetization tested
- Switching, activation, and retention measured separately

## Analysis Requirements

All analysis must include cuts by:
- **Segments**: S0-S5
- **Merchant attributes**: vertical, revenue band, ticket size, decision role
- **Channel mix**: POS-heavy, invoice-heavy, online-heavy, mixed
- **Sensitivity**: debit sensitivity, cash sensitivity

For each model, measure:
- Naturalness, adoption, switching intent
- Staff operability, retention confidence
- Monetization willingness

## Disallowed Patterns

Never include in any document:
- Questions like "Would you like zero fees?" or "Does this sound good?"
- Scenarios implying debit surcharge
- Scenarios using post-tender pricing changes
- Hidden pricing changes until after payment selection
- Silent fallback to embedded pricing
- Generic outputs like "merchants liked zero fees"

## Working with Mocks and Prototypes

When creating or editing HTML mocks:
- Use consistent test values: $100 base, 3% fee, $103 credit total (Model A) or posted price (Model B)
- Maintain equal fidelity across all three models - no model should appear more polished or better explained
- Include edge cases: manual entry, staff explanation needs, debit card scenarios
- Verify constraint compliance before presenting to users
- Follow mock pack design philosophy: constraint-aware, tradeoff-explicit, operationally realistic

When reviewing HTML files:
- Check that pricing is defined before payment method selection
- Verify no dynamic pricing based on card type detection
- Confirm debit cards are never surcharged
- Validate that convenience fees only appear in invoice/online contexts
- Ensure embedded pricing shows consistent posted prices
