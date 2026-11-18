---
name: valkiria-ads-ops
description: Run paid-growth operations through the Valkiria MCP server - audit ad spend, draft paused campaigns, review optimisation recommendations, prepare SMM drafts and pull market reports. Use when the user mentions ad accounts, campaigns, budgets, Google/Meta/TikTok Ads, SMM posts or Valkiria.
---

# Valkiria ads ops

All tools come from the `valkiria` MCP server. Nothing you do here goes live: every change is a draft or
proposal the account owner approves in the Valkiria dashboard (https://valkiria.pro).

## Always

1. Start with `get_started` - it tells you which cabinets, scopes and data this key can see.
2. Reply in the user's language. Keep money in the cabinet's native currency; never total across currencies.
3. Never invent numbers. `null` means "not measured", not zero. Say so.
4. On `PLAN_LIMIT_REACHED`, tell the user to open the pricing page in their dashboard. Do not sell.
5. End every task with "confirm in the dashboard" and the path the tool result gives you.

## Playbooks

**Audit spend** - `get_account_overview` -> `get_spend_summary` (period) -> `get_account_health` ->
`list_campaign_findings` per cabinet. Report the top 3 money leaks with the metric that proves each.

**Draft a paused campaign** - `generate_campaign_idea` (product, goal, budget) -> `create_campaign`
(lands as a local draft, never published) -> show the draft id and tell the user where to approve.

**Review recommendations** - `list_campaign_recommendations` -> `preview_campaign_recommendation` on each
candidate -> `validate_campaign_recommendation` -> only on explicit user "approve": `decide_campaign_recommendation`.

**SMM drafts** - `smm_accounts_list` -> `smm_posts_list` / `smm_posts_performance` for context. `smm_publish`
returns the dashboard path for the publish confirmation; it does not post.

**Market / provider report** - `get_provider_analytics_report` (explicit date range) or `generate_report`;
quote source dates and coverage gaps from the result.
