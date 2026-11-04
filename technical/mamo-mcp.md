---
description: Let your AI agent run your Mamo Accounts
---

# 🔌 Mamo MCP

## What it is

Mamo MCP connects the AI agent you already use (ChatGPT, Muse, Grok Bot, Claude, or any app that speaks the Model Context Protocol) to your Mamo Accounts. Ask it what your USDC Account has earned, how your stocks portfolio sits against its targets, or to add $200 to it, and it answers from live data on Base.

Your keys stay with you. The server holds no keys and never signs. When money should move, the agent checks the move first, then hands your wallet an unsigned transaction to review. Nothing happens until you sign it, and your Accounts stay exactly as they are in the Mamo app.

The server lives at `https://mcp.mamo.bot/mcp`: MCP over Streamable HTTP (spec 2026-07-28, earlier revisions accepted), stateless, with no API key and no sign-in to read or preview. A full stocks portfolio cycle, from opening to a full exit, has been tested on mainnet through it.

{% hint style="info" %}
Mamo MCP covers all five Accounts: the **USDC Account**, **Bitcoin Account**, **Ethereum Account**, **MAMO Account** and **Stocks Account**, all on Base. Tokenized stocks are not available in every jurisdiction. See the [Stocks](../grow/stocks.md) page and the [Terms of Service](../legal/terms-of-service.md).
{% endhint %}

## Connect your agent

Where a client supports it, the button opens the app with Mamo already filled in. You still confirm the install inside the app. If a button does not work in your setup, the manual steps under it do the same thing.

### ChatGPT

Turn on developer mode in settings, then create a connector with the URL `https://mcp.mamo.bot/mcp` and no authentication. This is still changing; check the client's current docs.

### Muse

Meta's Muse has no settings screen for MCP servers. You ask it in conversation and it builds the connection itself and saves it as a skill. Paste this into any Muse chat:

```
Build a custom integration to Mamo. Its MCP server is https://mcp.mamo.bot/mcp, a public HTTPS endpoint over streamable HTTP with no authentication. Connect to it, list every tool it gives you, and save it as a reusable skill called "Mamo".
```

Meta does not review custom connectors, so the usual rule applies: Muse only ever receives unsigned transactions from Mamo MCP, and your wallet still signs each one.

### Grok Bot

<a href="https://grok.com/connectors" class="button secondary">Open Grok connectors</a>

Grok Bot has no pre-filled link, so the button only opens the connectors page. There, click **New Connector**, choose **Custom**, and enter `https://mcp.mamo.bot/mcp` with no authentication. Custom connectors are a paid-plan feature, and on Grok Business and Enterprise a team admin has to provision the connector first.

### Claude

<a href="https://claude.ai/customize/connectors?modal=add-custom-connector&#x26;connectorName=Mamo&#x26;connectorUrl=https%3A%2F%2Fmcp.mamo.bot%2Fmcp" class="button secondary">Add Mamo to Claude</a>

The link pre-fills the custom connector form on claude.ai; click **Add** to finish. The same connector then appears in Claude Desktop. Free plans allow one custom connector. On Team and Enterprise plans, only Owners can add one.

Manual: **Settings → Connectors → Add custom connector**, URL `https://mcp.mamo.bot/mcp`, no authentication.

### Claude Code

```bash
claude mcp add --transport http mamo https://mcp.mamo.bot/mcp
```

### Cursor

<a href="https://cursor.com/install-mcp?name=mamo&#x26;config=eyJ1cmwiOiJodHRwczovL21jcC5tYW1vLmJvdC9tY3AifQ%3D%3D" class="button secondary">Add Mamo to Cursor</a>

Cursor opens with the Mamo server filled in; click **Install**. Manual: add this to `~/.cursor/mcp.json` (every project) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "mamo": { "url": "https://mcp.mamo.bot/mcp" }
  }
}
```

### VS Code

<a href="https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522mamo%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fmcp.mamo.bot%252Fmcp%2522%257D" class="button secondary">Add Mamo to VS Code</a>

VS Code asks you to confirm the server. Manual: run the command below, or add the same entry to your `mcp.json`.

```bash
code --add-mcp '{"name":"mamo","type":"http","url":"https://mcp.mamo.bot/mcp"}'
```

### Anything else

Any Streamable HTTP client works with the same URL. The [server card](https://mcp.mamo.bot/) lists the endpoint, protocol versions and every tool. The server's name on the card is `bot.mamo/mcp`.

## What an agent can do

**Knowledge** and **reads** only look. **Previews** check a move and dry-run it on Base. **Prepares** return the unsigned calls your wallet signs. Opening an Account has its own three steps. The [server card](https://mcp.mamo.bot/) always has the live tool list.

### Knowledge

| Tool             | What it does                                                                                                                    |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `get_started`    | Read this first: what Mamo is, the five Accounts, every tool and the order to call them in.                                     |
| `get_mamo_guide` | How Mamo works, in six topics (accounts, deposits, withdrawals, rewards, safety, fees), each with its docs page as `sourceUrl`. |
| `get_mamo_news`  | Recent posts from Mamo's X account (or Moonwell's), newest first.                                                               |

### Reads

| Tool                     | What it does                                                                                                           |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| `get_accounts`           | Every Mamo Account side by side, with current APY and status. No wallet needed.                                        |
| `get_account_details`    | How one Account works: where the money goes, contracts, audits; for the Stocks Account, listed stocks, limits and fee. |
| `get_user_accounts`      | Everything one wallet holds across Mamo, with USD totals.                                                              |
| `get_user_account`       | One Account in full. For the Stocks Account: NAV, cash, positions against targets and fee due.                         |
| `get_user_activity`      | A wallet's deposits, withdrawals, compounding and Stocks rebalances, newest first.                                     |
| `get_balance_history`    | How a USDC, Bitcoin, Ethereum or MAMO Account balance moved over 1 to 60 days.                                         |
| `get_wallet_balances`    | What the wallet holds outside Mamo on Base, and how much each Account is approved to pull.                             |
| `get_transaction_status` | Whether a transaction confirmed and what it did, including rebalances (`rebalanced`) and Aerodrome sales (`sold`).     |

### Previews and prepares

| Tools                                           | What they do                                                                                                          |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `preview_deposit` → `prepare_deposit`           | Check a deposit (ownership, balance, gas, approval, pauses, Stocks limits, a dry run), then build its unsigned calls. |
| `preview_withdraw` → `prepare_withdraw`         | The same for a withdrawal. A Stocks Account pays out in cash, selling on Aerodrome, or in kind.                       |
| `preview_stock_basket` → `prepare_stock_basket` | Check proposed stock targets, then build the calls that open the Stocks Account with them or replace them.            |
| `prepare_claim_rewards`                         | Build the call that claims a MAMO Account's rewards.                                                                  |

### Opening an Account

| Tool                          | What it does                                                                                  |
| ----------------------------- | --------------------------------------------------------------------------------------------- |
| `prepare_sign_in`             | The exact text a wallet signs so Mamo opens a USDC, Bitcoin, Ethereum or MAMO Account for it. |
| `create_account`              | Passes that signature to Mamo, which deploys the Account and pays the gas.                    |
| `get_account_creation_status` | Whether the new Account is live on Base yet. It usually takes a minute or two.                |

A Stocks Account opens differently: with a transaction your own wallet sends, through `preview_stock_basket`.

## Safety

* **No key, ever.** The server holds no private key, never signs and never broadcasts. Never give any assistant your private key or seed phrase. Mamo MCP will never ask for one.
* **What you sign.** The unsigned calls a `prepare_*` tool returns, shown by your wallet first: as one batch where it supports EIP-5792 `wallet_sendCalls`, otherwise one at a time. And once, to open a USDC, Bitcoin, Ethereum or MAMO Account, a Sign-In with Ethereum message. It moves nothing, but today that signature does not expire and cannot be revoked: give it only to `create_account`, and treat your agent's chat history as holding it.
* **Previews before prepares.** Every move starts with a preview: ownership, balances, pauses, limits and a dry run on Base. Prepare re-runs every check live and returns no calls if one fails.
* **Warnings have codes.** Every response carries `data`, `warnings` and `next_actions`; each warning has a code and a severity. `error`: do not sign (no calls come with one). `warning`: read to you before you sign. `info`: context. A figure that could not be read comes back empty with a warning, never a guessed zero.
* **Check where it goes.** Before you sign, check each call's `to` address. `get_account_details` lists the contracts each Account uses, and they match [Contract Addresses](contract-addresses.md).
* **Rate limits.** Per IP address: 60 requests a minute in total, 20 a minute for previews and prepares, 5 a minute for opening Accounts. Over a limit the server answers HTTP 429 with a `Retry-After` time.

### What Mamo MCP does not do

* **It does not hold your money.** Your Accounts are contracts your wallet owns, and withdrawals only ever go to the owner.
* **It does not act on its own.** Nothing is sent without your signature. (Stocks Account rebalancing is Mamo's own, as in the app.)
* **It does not promise prices or returns.** An APY is today's rate, not a promise. The Stocks Account has no APY; its value moves with the stocks it holds.

## Try it

**"Open a big-tech portfolio with $500."**\
The agent asks which stocks and weights you want, plus a share kept in USDC, and checks those targets with `preview_stock_basket`. Your wallet signs the transaction that opens the Stocks Account; then the agent previews a 500 USDC deposit, reads you its warnings and hands it over to sign. Until Mamo picks the new Account up, the deposit waits in USDC.

**"What did my rebalancer do this week?"**\
The agent reads `get_user_activity` filtered to rebalances, back to last week. Each CoW Protocol trade is its own row, sold and bought, and `get_transaction_status` opens any one. Then `get_user_account` shows how close the portfolio sits to its targets now.

**"Move my rewards into my stocks portfolio."**\
The agent finds your MAMO Account's unclaimed rewards and builds the claim with `prepare_claim_rewards`; they land in your wallet as cbBTC and MAMO. The Stocks Account only takes USDC or a listed stock, and Mamo MCP does not swap, so the agent says so plainly. Once you have converted them to USDC in your wallet, it previews and prepares the deposit.

## Links

* [Server card](https://mcp.mamo.bot/): the endpoint, supported versions and the live tool list
* [skill.md](https://mcp.mamo.bot/skill.md): a ready-made skill for Claude Code and Cursor
* [llms.txt](https://mcp.mamo.bot/llms.txt): this server, described for language models
* [How It Works](../behind-the-scenes/how-mamo-works.md) and [Security and Risk](../behind-the-scenes/how-mamo-keeps-you-safe.md)
* [Stocks](../grow/stocks.md): the Stocks Account, its targets, limits and fee

***

## At a glance

* Connect any MCP client to `https://mcp.mamo.bot/mcp`. No API key, no sign-in to read.
* Your agent reads, checks and prepares. Your wallet signs.
* Every move is previewed, dry-run and re-checked. An `error` warning means do not sign.
* No custody, no autopilot, no promised returns.
