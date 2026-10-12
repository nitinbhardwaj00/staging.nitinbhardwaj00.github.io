---
title: "Where AI actually helps FP&A today — and where it quietly doesn't"
date: 2026-09-07
permalink: /posts/2026/09/where-ai-helps-fpa/
excerpt: "AI is already useful in finance — just not where most vendor slides put it. A practitioner's map of what works, what's risky and what's still hype."
tags:
  - AI
  - FP&A
  - finance
---

AI is already useful in finance — just not where most vendor slides put it. A practitioner's map of what works, what's risky and what's still hype.

I use AI tools daily in finance and analytics work. The pattern I keep seeing: the biggest gains are in the unglamorous middle of the job, not in the "autonomous CFO" headlines.

## Where it works well today

**Variance commentary drafts.** Give a model the actuals-vs-budget table and the drivers you already know, and it produces a solid first draft of month-end commentary. The analyst edits instead of writing from scratch. Time saved is real; judgment stays human.

**Writing and reviewing formulas and SQL.** Explaining an inherited 40-line Excel formula, translating logic between SQL dialects, or drafting a dbt model — this is where AI pays for itself fastest.

**Structuring messy problems.** Case studies, planning scenarios, "what are we missing?" checklists. A model is a fast sparring partner for structuring before you do the real analysis.

**Document-heavy work.** Pulling terms from contracts, summarising board materials, comparing vendor proposals. Useful as long as someone checks the source for anything that matters.

## Where it's risky

**Answering numeric questions directly from raw data.** Without governed definitions, models give confident, plausible and inconsistent numbers. (More on that in [this post]({{ '/posts/2026/10/llms-need-a-semantic-layer/' | relative_url }}).)

**Forecasting without context.** A model can extrapolate a trend. It doesn't know that your biggest customer gave notice last week or that pricing changes next quarter. Forecasts are mostly about information the data doesn't contain yet.

**Anything that goes to auditors or investors unchecked.** The output may be right 95% of the time. The other 5% is exactly what due diligence finds.

## Where it's still mostly hype

**Fully autonomous planning.** Planning is a negotiation between people with different incentives. AI can support that conversation; it doesn't replace it.

**"Just connect it to everything."** Access without definitions and permissions creates more noise and more risk, not more insight.

## How I'd roll it out in a finance team

1. Start with drafting tasks where a human always reviews the output.
2. Write down which data the AI may use and which definitions it must follow.
3. Measure time saved on specific recurring tasks, not "productivity" in general.
4. Expand to data questions only once metrics are governed.

## The contrarian view

There's a strong case that finance teams are being *too* cautious. The cost of a reviewed AI draft is low, and teams that wait for perfect governance will fall behind those that experiment now with sensible guardrails. Some of the "risks" above are just as true of junior analysts with spreadsheets — we manage those with review, not prohibition.

I agree with more of that than my list suggests. The point isn't to wait. It's to be deliberate about which outputs need a human signature.
