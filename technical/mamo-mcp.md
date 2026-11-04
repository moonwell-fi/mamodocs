---
description: Let your AI agent run your Mamo Accounts
---

# 🔌 Mamo MCP

## Mamo MCP

### What is Mamo MCP?

Mamo MCP connects compatible AI assistants, including [ChatGPT](https://chatgpt.com/), [Muse](https://ai.meta.com/muse/), [Grok Bot](https://x.ai/bot), and [Claude](https://claude.ai/), to your Mamo Accounts and stocks portfolio through the [Model Context Protocol (MCP)](https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro).

Once connected, you can ask your assistant to check balances, review earnings, compare your stocks portfolio with its target allocations, or prepare a deposit or withdrawal using live data from [Base](https://www.base.org/).

Your wallet remains in control. Mamo MCP holds no private keys and does not sign or broadcast transactions. When an action requires funds to move, the assistant checks it and prepares an unsigned transaction for your wallet to review. The transaction only proceeds when you sign.

Mamo MCP works with the same accounts and portfolio you use in the Mamo app. It supports all five products on Base:

* USDC Account
* Bitcoin Account
* Ethereum Account
* MAMO Account
* Stocks

_Stocks are available only in eligible jurisdictions outside the United States._

### Server details

| **Endpoint**          | `https://mcp.mamo.bot/mcp`                            |
| --------------------- | ----------------------------------------------------- |
| **Transport**         | MCP over Streamable HTTP                              |
| **Protocol version**  | 2026-07-28, with earlier revisions accepted           |
| **Server identifier** | `bot.mamo/mcp`                                        |
| **Authentication**    | No API key or sign-in required for reads and previews |
| **Session handling**  | Stateless                                             |
| **Network**           | Base                                                  |

A complete stocks portfolio lifecycle, from creation through a full exit, has been tested on Base mainnet through Mamo MCP.

### Connect your assistant

Use the setup instructions for your preferred client below. Where an installation button is available, it opens the client with the Mamo server details prefilled. You must still confirm the connection inside the client.

Client interfaces, plan requirements, and administrator permissions may change. Refer to your client’s current documentation if its settings differ from these instructions.

#### ChatGPT

Enable developer mode in settings, then create a connector using:

* **Server URL:** `https://mcp.mamo.bot/mcp`
* **Authentication:** None

#### Muse

Muse can create a custom integration through a conversation and save it as a reusable skill. Paste the following into a Muse chat:

> Build a custom integration to Mamo. Its MCP server is [https://mcp.mamo.bot/mcp](https://mcp.mamo.bot/mcp), a public HTTPS endpoint using Streamable HTTP with no authentication. Connect to it, list its available tools, and save the integration as a reusable skill called “Mamo”.

Meta does not review custom connectors. Mamo MCP returns unsigned transactions, and your wallet must still sign each transaction before it can proceed.

#### Grok Bot

Open the connectors page, select **New Connector → Custom**, and enter:

* **Server URL:** `https://mcp.mamo.bot/mcp`
* **Authentication:** None

Custom connectors require a paid plan. On Grok Business and Enterprise, a team administrator must provision the connector first.

The installation button opens the connectors page but does not prefill the server details.

#### Claude

Go to **Settings → Connectors → Add custom connector** and enter:

* **Server URL:** `https://mcp.mamo.bot/mcp`
* **Authentication:** None

If you use the installation link, the form is prefilled. Select **Add** to complete setup. The connector will also appear in Claude Desktop.

Free plans support one custom connector. On Team and Enterprise plans, only Owners can add custom connectors.

#### Claude Code

Run:

```
claude mcp add --transport http mamo https://mcp.mamo.bot/mcp
```

#### Cursor

Use the installation button and select **Install**, or add the following configuration manually.

Use `~/.cursor/mcp.json` to make the server available across projects, or `.cursor/mcp.json` to configure it for a single project.

```
{
  "mcpServers": {
    "mamo": {
      "url": "https://mcp.mamo.bot/mcp"
    }
  }
}
```

If the file already contains other servers, add the `mamo` entry to its existing `mcpServers` object.

#### VS Code

Use the installation button and confirm the server, or run:

```
code --add-mcp '{"name":"mamo","type":"http","url":"https://mcp.mamo.bot/mcp"}'
```

You can also add the server through your MCP configuration file.

#### Other MCP clients

Any client that supports MCP over Streamable HTTP can connect using the same endpoint:

```
https://mcp.mamo.bot/mcp
```

The server card lists supported protocol versions and the current tool list.

### What your assistant can do

Mamo MCP separates information requests from transaction preparation.

| Tool category | Purpose                                                                                               |
| ------------- | ----------------------------------------------------------------------------------------------------- |
| Knowledge     | Provide information about Mamo and how its Accounts and stocks portfolios work.                       |
| Reads         | Retrieve balances, earnings, allocations, activity, and transaction status without changing anything. |
| Previews      | Check a proposed action and simulate it on Base before preparing a transaction.                       |
| Prepares      | Repeat the checks using live data and return unsigned transaction calls for your wallet.              |
| Creation      | Guide you through opening an Account or creating a stocks portfolio.                                  |

The server card provides the complete, current tool list.

Opening a USDC, Bitcoin, Ethereum, or MAMO Account uses a separate three-step process. Creating a stocks portfolio follows a different flow: the assistant uses `preview_stock_basket`, and your wallet signs and sends the portfolio-creation transaction.

### Transaction checks and wallet approval

#### Your keys stay with you

Mamo MCP does not hold private keys, sign transactions, or broadcast them.

Never share your private key or seed phrase with an assistant. Mamo MCP will never request either.

#### Review what you sign

Tools named `prepare_*` return unsigned transaction calls for your wallet to display and approve.

If your wallet supports EIP-5792 `wallet_sendCalls`, it can present the calls as a batch. Otherwise, you approve them individually.

Opening a USDC, Bitcoin, Ethereum, or MAMO Account also requires a Sign-In with Ethereum message. This signature does not move funds.

The account-creation signature currently has no expiry and cannot be revoked. Provide it only to `create_account`, and treat any chat history containing it as sensitive.

#### Preview before preparing

Every transaction workflow starts with a preview. Checks cover ownership, balances, paused operations, applicable limits, and a simulation on Base.

The prepare step repeats these checks using live data. If a check fails, the server returns no transaction calls.

#### Review warnings

Each response includes `data`, `warnings`, and `next_actions`. Warnings include a code and severity:

| Severity  | Meaning                                                   |
| --------- | --------------------------------------------------------- |
| `error`   | Do not sign. The server returns no transaction calls.     |
| `warning` | The assistant should explain the warning before you sign. |
| `info`    | Additional context about the result or proposed action.   |

If a value cannot be retrieved, the server returns an empty value with a warning rather than reporting a guessed zero.

#### Verify destination addresses

Before signing, review the `to` address of each transaction call.

The `get_account_details` tool lists the contracts used by your Accounts and portfolio. You can compare these with the Contract Addresses documentation.

### Rate limits

Rate limits apply per IP address.

| Request category      | Limit         |
| --------------------- | ------------- |
| All requests combined | 60 per minute |
| Previews and prepares | 20 per minute |
| Account creation      | 5 per minute  |

Requests above these limits receive an HTTP `429` response with a `Retry-After` value indicating when to try again.

### What Mamo MCP does not do

#### Hold your funds

Your Accounts and stocks portfolio use smart contracts owned by your wallet. Withdrawals can only be sent to the owner.

#### Execute transactions without your approval

Mamo MCP prepares transactions for you to sign. It does not independently submit transactions or move funds.

Automated stocks rebalancing is a separate Mamo feature and operates according to your portfolio settings, just as it does in the app.

#### Guarantee prices or returns

An APY reflects the current rate and is not a promise of future returns.

Stocks do not earn an APY. Your portfolio’s value changes with the prices of the stocks it holds, less fees and trading costs.

#### Swap assets

Mamo MCP does not convert assets for you. If an action requires a different deposit asset, you must obtain that asset separately before proceeding.

### Example requests

#### Open a big-tech portfolio

> Open a big-tech portfolio with $500.

The assistant asks which stocks you want, their target allocations, and whether you want to hold any USDC as cash.

It checks your choices using `preview_stock_basket`, then provides the portfolio-creation transaction for your wallet to sign. After the portfolio is created, it previews and prepares a 500 USDC deposit, explains any warnings, and asks you to review and sign.

The deposit remains in USDC until Mamo begins managing the new portfolio and stock purchases can execute.

#### Review rebalancing activity

> What did my rebalancer do this week?

The assistant uses `get_user_activity` to retrieve rebalancing activity for the past week.

Each CoW Protocol trade appears as a separate entry showing the assets sold and purchased. The assistant can use `get_transaction_status` to inspect an individual transaction, then `get_user_account` to show how your current allocations compare with their targets.

#### Move rewards into a stocks portfolio

> Move my rewards into my stocks portfolio.

The assistant checks your MAMO Account’s unclaimed rewards and prepares the claim using `prepare_claim_rewards`, following the required preview checks. Once you sign and the claim completes, the rewards arrive in your wallet as cbBTC and MAMO.

A stocks portfolio accepts USDC or supported stock tokens. Because Mamo MCP does not swap assets, the assistant explains that you must first convert the rewards into an accepted asset.

Once you have USDC in your wallet, the assistant can preview and prepare the deposit into your portfolio.

### Further information

* **Server card:** Endpoint details, supported protocol versions, and the current tool list.
* **`skill.md`:** A ready-made skill for Claude Code and Cursor.
* **`llms.txt`:** A description of the server for language models.
* **How It Works:** An overview of Mamo Accounts, stocks portfolios, and their operation.
* **Security and Risk:** Controls, safeguards, and risks.
* **Stocks:** Supported stocks, target allocations, rebalancing, limits, and fees.
* **Contract Addresses:** Published addresses for Mamo’s contracts.

### At a glance

* Connect a compatible MCP client to `https://mcp.mamo.bot/mcp`.
* Read live data and preview actions without an API key or sign-in.
* Ask your assistant to retrieve information, check actions, and prepare transactions.
* Review transaction details and warnings before signing with your wallet.
* Keep control of your keys and funds. Mamo MCP never signs or broadcasts transactions.
