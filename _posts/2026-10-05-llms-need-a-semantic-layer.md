---
title: "Your LLM doesn't need more data. It needs a semantic layer."
date: 2026-10-05
permalink: /posts/2026/10/llms-need-a-semantic-layer/
excerpt: "Text-to-SQL demos look magical until someone asks a finance question. The fix isn't a bigger model — it's giving the model definitions it can't improvise around."
tags:
  - AI
  - semantic layer
  - dbt
---

Text-to-SQL demos look magical until someone asks a finance question. The fix isn't a bigger model — it's giving the model definitions it can't improvise around.

## The demo vs. the Monday morning

The demo goes like this: connect an LLM to the warehouse, ask "how many customers signed up last month?", get a correct chart in five seconds. Everyone claps.

Then a finance lead asks: *"What was net revenue retention for the 2025 cohort, excluding the reseller channel?"*

To answer that correctly, the model needs to know which table is the source of truth for revenue, how cohorts are defined, whether credit notes reduce revenue in the month issued or the month of the original invoice, what "reseller channel" maps to in the data, and which currency to report in. None of that is in the schema. A model that writes raw SQL will guess — and in finance, a plausible wrong answer is worse than no answer.

## What a semantic layer changes

A semantic layer sits between the warehouse and anything that asks questions — BI tools, spreadsheets, or an LLM. Instead of tables and columns, it exposes **metrics, dimensions and entities** with their logic defined once.

With something like dbt and MetricFlow, `net_revenue_retention` becomes a governed object with its formula, grain, allowed dimensions and filters. The LLM's job shrinks from "write correct SQL against 400 tables" to "pick the right metric and the right filters". That's a much easier problem, and when the model does get it wrong, the error is visible: it chose the wrong metric, not a subtly wrong join.

The practical benefits I care about:

- **Consistency.** The chatbot, the board deck and the dashboard all return the same number, because they call the same definition.
- **Auditability.** Every answer can show *which* metric and filters were used — something a finance team can actually review.
- **Smaller blast radius.** You can expose ten well-defined metrics to AI first, instead of the whole warehouse.

## What I'm building to test this

I'm working through a small project to pressure-test the idea: a sample SaaS dataset modelled in dbt, with a semantic layer on top, running on a free lakehouse tier, and an LLM interface that can only query through the metric layer.

The interesting part is deliberately ambiguous: I'm defining MRR, ARR and NRR in more than one legitimate way (see [same label, different formula]({{ '/posts/2026/10/same-label-different-formula/' | relative_url }})) and testing whether the model asks for clarification or silently picks one. I'll share what I learn, including what doesn't work.

## The contrarian view

Semantic layers are not free. Someone has to model and maintain every metric, and in a fast-moving company that backlog grows quickly. Many teams will find that a well-documented set of curated tables plus good prompting gets them 80% of the way at a fraction of the effort. And for exploratory questions — "anything odd in churn by region?" — a strict metric layer can feel restrictive.

My view: for **exploration**, give analysts and models freedom. For **any number that leaves the finance team**, route it through governed definitions. The mistake is using the same path for both.

## A simple test for your own setup

Ask your AI assistant the same revenue question three different ways. If you get three different numbers, you don't have an AI problem. You have a definitions problem that AI just made visible.
