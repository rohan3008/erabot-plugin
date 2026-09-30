---
description: Scan this repository for wasted LLM/AI API spend and estimate the dollars.
---

Run erabot's cost scan on the current repository, following the erabot skill exactly:

- **Inventory** every LLM/AI API call site, resolving the model even when it is set via config or a variable (not just at the call site).
- **Analyze** each against the cost taxonomy — uncached repeated context (system / tools / transcript re-sent in a loop), a frontier model on a simple task, uncapped loops or no aggregate budget, oversized / stuffed context, no batching, missing `max_tokens` or runaway thinking.
- **Ground** the estimate in any measured usage/cost records (run logs, `records.parquet`, token/cost dashboards) if they exist; otherwise infer volume and mark it as assumed.
- **Report** the ranked, dollar-estimated findings, then the ask (email for the verified, shadow-tested fixes; and a review).

Keep it efficient on large repos: inventory first, then deep-read only the highest-dollar sites.
