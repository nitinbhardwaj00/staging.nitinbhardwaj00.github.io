---
title: "Same label, different formula: why your ARR isn't my ARR"
date: 2026-10-12
permalink: /posts/2026/10/same-label-different-formula/
featured: true
excerpt: "Most metric fights aren't about the numbers. They're about two teams using the same word for two different calculations — and nobody noticing until the board deck."
tags:
  - SaaS metrics
  - data governance
  - finance
---

Most metric fights aren't about the numbers. They're about two teams using the same word for two different calculations — and nobody noticing until the board deck.

I call this **"same label, different formula."** It's the single most expensive data-quality problem I've seen in SaaS companies, and it almost never shows up as a bug. Every dashboard is internally consistent. Every query runs. The numbers are just answering different questions.

## What it looks like in practice

Take ARR. Ask five people in a scale-up how it's calculated and you'll often get answers like these:

- **Finance:** contracted recurring revenue at month-end, annualised, excluding one-off setup fees.
- **Sales:** signed bookings including deals that haven't gone live yet.
- **RevOps / CRM:** whatever the "ARR" field on the opportunity says, which reps sometimes overwrite.
- **Product analytics:** MRR × 12 from the billing system, including usage overages from last month.
- **The investor deck:** a blend, chosen because it grew the fastest.

Each is defensible. Together they guarantee that a CFO and a CRO will walk into a meeting with different numbers and both be "right".

Net revenue retention is worse. Is the cohort defined by start month or fiscal year? Are downgrades netted against expansion at the customer or at the cohort level? Is churn counted when notice is given or when the contract ends? Change any one of these and NRR can move by several points — enough to change a valuation conversation.

## Why it gets worse as you grow

In a small company, one person usually owns the numbers, so definitions live in their head and are at least consistent. The problem appears when:

1. **Tools multiply.** CRM, billing, ERP, the planning tool and the BI layer each get their own copy of the logic.
2. **Teams multiply.** Each function hires an analyst who rebuilds the metric "properly".
3. **Companies multiply.** In a PE buy-and-build, every acquired business arrives with its own definitions — and its own reasons for liking them.

By the time you notice, the cost isn't one wrong number. It's that nobody trusts *any* number, so every decision gets a second meeting.

## What actually fixes it

I've tried the usual remedies. Here's my honest ranking.

**1. A metric dictionary nobody reads — weak.** A Confluence page of definitions is a good start and a bad finish. If the definition isn't enforced in code, it drifts within a quarter.

**2. One "source of truth" dashboard — better, but fragile.** It works until someone exports to Excel and adds a column.

**3. Definitions as code, owned by finance — strongest.** Put the metric logic in one governed layer (a semantic layer, a dbt model, or the EPM tool if that's where planning lives), give each metric a named owner, and make every downstream tool read from it. Disagreements then become pull requests instead of meeting topics.

The governance part matters more than the technology. Every metric needs:

- **An owner** who can say "no" to a change.
- **A written formula** in plain language *and* in code.
- **Explicit edge cases**: reactivations, multi-currency, mid-term upgrades, credit notes.
- **A version history**, so you can explain why last year's number changed.

## The contrarian view

To be fair to the other side: forcing one definition everywhere has real costs. Sales *should* care about bookings before go-live; that's how they manage pipeline. Product *should* look at usage-based revenue weekly. Over-standardising can make the governed metric so conservative that teams quietly build shadow versions again.

The answer I've landed on isn't "one definition". It's **one name per definition**. Call it "Contracted ARR", "Booked ARR" and "Run-rate ARR" if you need all three — but never let two formulas share a label.

## Why this matters even more with AI

If you plan to point an LLM at your warehouse and let people ask "what was our ARR last quarter?", this problem stops being an annoyance and becomes a liability. A model will happily pick one of the five definitions and answer confidently. I'll write about how semantic layers address this in a follow-up post.

*If your company has its own version of this story, I'd love to hear it.*
