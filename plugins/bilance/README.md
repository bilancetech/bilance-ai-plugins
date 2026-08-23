# Bilance plugins for AI coding agents

Connect your own Bilance finances to Claude Code or Codex, and ask questions
like *"what did I spend on groceries last month?"* or *"which subscriptions
renew this week?"*.

You sign in with your Bilance account in the browser. The AI app never sees your
password, and you can disconnect at any time in the Bilance app under
**Settings → Connected AI apps**.

## Claude Code

```bash
claude plugin marketplace add bilancetech/bilance-ai-plugins
claude plugin install bilance@bilance
```

Then start `claude`, run `/mcp`, choose **bilance** → **Authenticate**, and sign in.

## Codex

```bash
codex plugin marketplace add bilancetech/bilance-ai-plugins
codex plugin add bilance@bilance
codex mcp login bilance
```

## What you get

| Tool | What it does |
| :--- | :--- |
| Get finance context | Accounts, balances, budgets, data freshness, and how the numbers are defined. Start here. |
| Query transactions | Search and paginate transactions; CSV export for bulk. |
| Summarize finances | Totals by period or category, in your default currency. |
| Get recurring payments | Subscriptions and recurring bills, with what's next and what's overdue. |
| Sync bank data | Refresh from your bank. At most once a day, and only if you allow it. |

Everything except the bank refresh is read-only. Usage is capped per day, and
every call is recorded in your account so you can see which app read what and
when.

## Requirements

A Bilance account with the app installed: [bilanceapp.com](https://bilanceapp.com).

## Support

[support@bilanceapp.com](mailto:support@bilanceapp.com) ·
[Privacy policy](https://bilanceapp.com/privacy) ·
[Terms](https://bilanceapp.com/terms)
