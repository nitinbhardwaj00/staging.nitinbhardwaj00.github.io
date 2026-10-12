---
title: "Ten portfolio companies, ten definitions of revenue: the PE roll-up data problem"
date: 2026-09-14
permalink: /posts/2026/09/pe-roll-up-data-problem/
excerpt: "Buy-and-build strategies assume you can compare and combine the businesses you acquire. Usually, you can't — at least not without a lot of quiet manual work."
tags:
  - private equity
  - consolidation
  - finance
---

Buy-and-build strategies assume you can compare and combine the businesses you acquire. Usually, you can't — at least not without a lot of quiet manual work.

Vertical SaaS roll-ups are a popular private equity play: buy several smaller software companies in a niche, share infrastructure, and grow the platform. The investment thesis depends on numbers like retention, growth and margin *across* the group. The operational reality is that every acquired company reports those numbers differently.

## Where it breaks

A typical add-on arrives with:

- **Its own accounting setup** — often a small-business ledger with its own chart of accounts.
- **Its own billing logic** — annual prepay, monthly, usage-based, or a mix.
- **Its own metric definitions** — usually set by a founder years ago and never revisited.
- **Its own spreadsheet** that the founder trusts more than anything you'll build.

The group finance team then spends each month mapping, adjusting and reconciling, mostly in Excel. The consolidated KPI pack goes to the investment committee looking precise — and resting on hundreds of manual mapping decisions nobody else can see.

## Why standard tools don't fully solve it

Consolidation software handles the accounting side well: currency, intercompany eliminations, statutory reporting. What it handles less well is the **semantic** side — making sure "churn" or "recurring revenue" means the same thing in company A and company F. That logic usually lives in someone's head.

## What good looks like

From what I've seen, the groups that do this well:

1. **Publish a group metric standard on day one of each acquisition**, with clear definitions and edge cases.
2. **Map each portco to the standard explicitly**, and keep that mapping documented and versioned — not hidden in formulas.
3. **Separate local and group views.** The portco keeps its operational metrics; the group gets standardised ones. Both exist, with a visible bridge between them.
4. **Automate anomaly checks.** A sudden jump in a portco's retention is more often a mapping change than a business change. Flag it before it reaches the board.
5. **Meet finance teams where they work.** Small portco teams live in Excel and their ledger. A solution that requires them to learn a new platform will be adopted slowly, if at all.

## The contrarian view

Some operating partners argue that perfect standardisation isn't worth it: what matters is cash, EBITDA and a handful of directional KPIs, and over-engineering the data layer distracts from integration work that actually creates value. They have a point — especially in the first year after an acquisition, when the priority is stabilising the business.

My counter: the cost of inconsistent metrics compounds. By the time you prepare an exit, buyers will rebuild your numbers themselves. You'd rather they find the same answer you did.

---

*I'm exploring ideas in this space — particularly lightweight, Excel-native ways to standardise and sanity-check portco data. If you work in PE operations or group finance, I'd like to hear how you handle it.*
