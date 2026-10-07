# Bilance plugins for AI apps

Connect your own Bilance finances to Claude Code, Codex or the Gemini CLI, and ask
questions like *"what did I spend on groceries last month?"* or *"which
subscriptions renew this week?"*. When you ask, the AI app can also tidy up your
records, for example recategorize transactions or create a budget.

You sign in with your Bilance account in the browser. The AI app never sees your
password or bank login. Bilance never moves money: no payments or transfers
from your bank. You can switch off changes or disconnect at any time in the
Bilance app under **Settings → Connected AI apps**.

Full guide, including Claude on the web and ChatGPT:
[bilanceapp.com/help/connect-ai-apps](https://bilanceapp.com/help/connect-ai-apps).

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

## Gemini CLI

```bash
gemini extensions install https://github.com/bilancetech/bilance-ai-plugins
```

Then, inside `gemini`, run `/mcp auth bilance`.

## What the AI app can read

| Tool | What it does |
| :--- | :--- |
| Get finance context | Accounts, balances, categories, tags, budgets, data freshness, and how the numbers are defined. Start here. |
| Query transactions | Search and paginate transactions; CSV export for bulk. |
| Summarize finances | Totals by period, category, merchant or tag, in your default currency. |
| Get finance report | The same monthly and period reports as the app's AI chat. |
| Get year in review | Yearly trends, budget performance, recurring payments and merchant patterns. |
| Get budget progress | Limits, spending and progress for a chosen financial month. |
| Get recurring payments | Subscriptions and recurring bills, with what's next and what's overdue. |
| Get net worth | What you own and what you owe, by category. |
| Get asset history | Recorded values of one asset over time, with buys and sales for unit-based assets. |
| Find similar transaction titles | Likely merchant spellings before filtering. |
| Get edit outcome | Whether an earlier change went through. |

## What it can change

Only when you ask, and only while **Allow changes to your data** is on for that
app (it is on by default):

- transactions: edit, recategorize, tag, split, add, convert and delete
- categories, tags, budgets and recurring payments: create, edit and delete
- accounts: add manual accounts, rename, hide or adjust accounts
- assets: create, edit and delete
- the household filter saved in the app

**Sync bank data** refreshes from your bank, at most once a day, while **Allow
bank data refresh** is on.

## Shared finances

Read tools follow the household filter saved in the Bilance app. Each read call
can pick another filter without changing the saved one. Accounts and
transactions a partner shares with you are included while sharing is on. They
are read-only, except that a shared partner transaction can be recategorized
(single or split), excluded, starred or marked seen, as in the app. Transactions
on hidden accounts are left out; account balances can still appear.

## Limits

300 tool calls per user per day across all connected apps (resets at midnight
UTC), 60 per minute and one bank refresh per day. CSV pages default to 500
rows; pages over 500 rows count against 3 large pages per day. An active
Bilance subscription, trial or complimentary access is required.

Disconnecting stops future access but does not erase what the AI app has
already received.

## Requirements

A Bilance account with the app installed: [bilanceapp.com](https://bilanceapp.com).

## Support

[help@bilanceapp.com](mailto:help@bilanceapp.com) ·
[Guide](https://bilanceapp.com/help/connect-ai-apps) ·
[Privacy policy](https://bilanceapp.com/privacy) ·
[Terms](https://bilanceapp.com/terms)
