---
title: "What I learned evaluating EPM platforms (and implementing Pigment)"
date: 2026-09-21
permalink: /posts/2026/09/choosing-an-epm-platform/
excerpt: "Most EPM selections are decided by the demo. They should be decided by your messiest planning process and who will own the model in two years."
tags:
  - FP&A
  - EPM
  - finance systems
---

Most EPM selections are decided by the demo. They should be decided by your messiest planning process and who will own the model in two years.

I've been through a full evaluation of planning platforms and a hands-on Pigment implementation. The market has improved a lot — modern tools are far more flexible than the old generation — but the way companies choose them hasn't. Here's the framework I'd use next time.

## Start with the problem, not the shortlist

Before talking to a single vendor, write down:

- **The three planning processes that hurt most today.** Headcount planning, revenue forecasting and opex budgeting are the usual suspects.
- **Who builds and maintains models.** A dedicated finance-systems person? An FP&A analyst part-time? This decides how much complexity you can afford.
- **Where actuals come from** and how clean they are. An EPM tool doesn't fix bad source data; it presents it faster.

## Run the demo on your data, not theirs

Vendor demos use beautifully clean sample companies. Ask each finalist to build a slice of *your* hardest model — for example, headcount with start-date phasing, salary bands and currency — using your anonymised data. You learn more in that week than in five polished demos.

## The criteria that actually mattered

1. **Modelling flexibility vs. guardrails.** Very flexible tools let you build anything — including an unmaintainable mess. Look at how the tool handles dimensions, versions and scenarios.
2. **Integrations.** How do actuals arrive from the ERP, CRM and HRIS? Native connectors, a middleware layer, or CSV uploads every month?
3. **Ownership after go-live.** Can a strong FP&A analyst maintain it, or do you need the implementation partner on retainer?
4. **Business-user experience.** Budget holders will open it twice a year. If they can't find their cost centre in under a minute, they'll go back to email and Excel.
5. **Total cost.** Licences are the visible part. Implementation, training and the internal time to maintain models are often larger.

## Implementation lessons

- **Rebuild, don't replicate.** Copying your old Excel logic one-to-one carries over every workaround. Use the migration to simplify.
- **Ship one process first.** Get headcount or opex live and trusted before starting revenue.
- **Lock definitions early.** Planning tools inherit the [same-label-different-formula]({{ '/posts/2026/10/same-label-different-formula/' | relative_url }}) problem. Decide what "ARR" or "FTE" means before building it.
- **Train the owners, not just the users.** The system is only as good as the person who can change it on a Friday afternoon.

## The contrarian view

Not every company needs an EPM platform. Below a certain size, a well-structured spreadsheet model with good version control and a disciplined monthly close can outperform an under-owned EPM tool. I've seen companies buy a powerful platform, implement 30% of it, and keep the real forecast in Excel anyway.

If you can't name the person who will own the model in two years, you're probably not ready to buy one.
