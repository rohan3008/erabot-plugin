# erabot — find what your code is overpaying for LLM APIs

A Claude Code plugin. Run **`/erabot:scan`** in any repo and it finds where your code wastes money on LLM/AI APIs — the wrong model for the job, prompts and tool schemas re-sent uncached in a loop, uncapped agent loops, oversized context — and gives you an honest dollar estimate and the fix for each.

It runs on **your own agent**, so it's free — and it reads your code *deeply*: resolving the model even when it's set via config, and reading the loop, which is where the real cost hides (and where static scanners lowball by 100×).

## Install

```bash
claude plugin marketplace add rohan3008/erabot-plugin
claude plugin install erabot@erabot-marketplace
```

Then run **`/erabot:scan`** in any repository. It also triggers automatically when you ask about LLM cost or a high API bill.

## What you get

- Every LLM/AI call site, ranked by estimated **$/month of waste**
- The cause and the fix for each — caching, cheaper-model candidates, caps, trimming
- **Honest by design:** assumptions are marked, and a model swap is a *candidate* until it's shadow-tested — never claimed as "proven" from static code alone

Want the *verified* fixes — proof each swap holds quality on your real traffic, plus apply-ready diffs and cost-regression alerts on your repo? That's `deep_audit`, below.

## Also installed: the hosted erabot tools

Installing the plugin also registers erabot's hosted MCP server — no extra setup, no `claude mcp add`. These tools show up in Claude Code right away:

- **`scan_code`** / **`scan_public_repo`** — *free*: estimate a pasted snippet or a public GitHub repo's LLM spend, server-side.
- **`deep_audit`** — the *verified* paid audit: proof each fix holds quality on your real traffic (shadow-tested) plus apply-ready diffs. Needs an erabot key — get one at [erabot.ai](https://erabot.ai).

The `/erabot:scan` skill above runs **locally on your own agent** (free); these run on **erabot's server**. One install gives you both — diagnose free, then upgrade to the verified fixes in the same tool.

## Proof

erabot found an invisible **$116/day** leak in a real LLM agent — a frontier-model loop re-sending its whole transcript uncached — and one change cut the input-token cost **54%**, measured, with zero change to the agent's decisions.

**[Read the case study →](https://claude.ai/artifact/MdWxyYtNSSKppYJkRCKF1k)**

---

Built by [erabot](https://erabot.ai) · MIT
