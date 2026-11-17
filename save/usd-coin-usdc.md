---
description: Smart growth for your stablecoins
---

# 🔵 USD Coin (USDC)

## What is the USDC Account?

The Mamo USDC Account gives your stablecoins a clear purpose. You deposit USDC, and Mamo puts your USDC to work in lending markets. Earnings come from borrower interest and market rewards, and flow back into your balance as more USDC. The process runs continuously, with no manual actions or ongoing decisions from you.

{% hint style="info" %}
**About USDC.** [USDC](https://www.circle.com/usdc) (USD Coin) is a regulated stablecoin issued by [Circle](https://www.circle.com/usdc). Each USDC maintains a 1:1 value with the US dollar and is fully backed by cash or cash equivalents. That makes USDC easy to hold, easy to move and predictable in value.
{% endhint %}

## How your money grows

When you deposit USDC, Mamo allocates your funds across two trusted destinations on [Base](https://www.base.org/): [Moonwell](https://moonwell.fi/) and [Morpho](https://morpho.org/). Both are lending platforms. Borrowers take USDC from them and pay interest in return, and that interest becomes your earnings.

| **Destination** | **Where your USDC goes**                                                               |
| --------------- | -------------------------------------------------------------------------------------- |
| Moonwell        | [Moonwell USDC Core Market](https://moonwell.fi/markets/supply/base/usdc) on Base      |
| Morpho          | [Moonwell USDC Flagship Vault](https://moonwell.fi/vaults/deposit/base/mwusdc) on Base |

Mamo monitors both destinations continuously and shifts your USDC toward the one paying more. Allocation follows changes in rates, not a fixed schedule. You do not manage positions or compare rates yourself. Mamo handles that for you, automatically.

<figure><img src="../.gitbook/assets/Twitter post - 23.png" alt=""><figcaption><p>Mamo USDC Account</p></figcaption></figure>

## What you earn

Your USDC balance grows in two ways.

* **Borrower interest.** Interest accrues directly to your USDC balance for as long as your funds remain deposited. The rate is tied to borrowing demand, so the rate moves over time.
* **Reward tokens.** The underlying market and vault also distribute WELL and MORPHO rewards. Once your rewards reach about $5 in value, Mamo converts them into USDC and adds the USDC to your balance. Rewards never need claiming. Everything becomes more USDC.

## How compounding works

Interest and converted rewards are reinvested into your USDC balance automatically. Each addition then earns alongside your original deposit, so growth builds on earlier growth without any input from you.

Mamo tracks real-time rates across the market and the vault and reallocates when rates change. This keeps your USDC positioned where earnings are higher, without constant movement or tuning.

## How reward conversions are handled

WELL and MORPHO rewards are converted into USDC through [CoW Swap](https://swap.cow.fi/), with prices verified against [Chainlink](https://chain.link/) price feeds. These checks keep each conversion in line with fair market value. Waiting until rewards reach about $5 also avoids small, inefficient swaps.

If market conditions are not right, Mamo waits before converting. Converted USDC goes straight back into your balance and keeps earning.

## Security and control

Your USDC stays under your control from start to finish. Mamo never takes custody. Your funds move into a personal smart contract vault controlled by you, and only you can withdraw from that vault.

You decide when to add funds, pause deposits or withdraw. No lockups apply.

## Access anytime

You can request a withdrawal of your USDC at any time. Mamo applies no lockups, no waiting periods and no penalties, and you can pause or resume deposits on your own schedule. Withdrawals do depend on the liquidity available in the underlying markets, which the next section explains.

## Available liquidity

Withdrawals depend on the liquidity available in the underlying yield sources. Your USDC is lent to borrowers through Moonwell and Morpho, so the amount that can be withdrawn at any moment is the portion that is not currently borrowed. This is called available liquidity.

When a market is heavily borrowed, available liquidity can run short. A withdrawal for more than the available liquidity will not go through.

#### If your withdrawal does not go through

A failed withdrawal moves nothing. Your USDC stays in your account. Come back and try again later. Liquidity returns as borrowers repay their loans and as lenders supply more USDC to the market.

#### Checking available liquidity

You can see how much liquidity a market has before you withdraw. On Moonwell, open the [Moonwell USDC Core Market](https://moonwell.fi/markets/supply/base/usdc) and review the market information, then compare the amount you want to withdraw with the liquidity shown. Your balance may be split between the Moonwell market and the Morpho vault, so treat the market figure as a guide, not an exact limit.

Moonwell's documentation covers [checking available liquidity](https://docs.moonwell.fi/moonwell/moonwell-overview/lend/withdraw#checking-available-liquidity) and [market utilization and liquidity](https://docs.moonwell.fi/moonwell/moonwell-overview/lend/lend-faq#market-utilization-and-liquidity) in more detail.

## USDC from the Mamo Drop

If you also hold MAMO in a [MAMO Account](https://docs.mamo.bot/grow/mamo-mamo) with the Reinvest setting, USDC rewards from the weekly Mamo Drop are sent to your USDC Account, where they join your balance.

## Things to know

* **Rates vary.** Interest rates change with borrower demand, so the rate you see today can be different tomorrow.
* **Liquidity.** Withdrawals depend on the liquidity available in the underlying markets. If a market is heavily borrowed, a withdrawal may have to wait until liquidity returns.
* **Smart contract risk.** Independent audits and a bug bounty reduce the chance of vulnerabilities, but no code is perfect.
* **Protocol risk.** Your funds are lent through Moonwell and Morpho on Base. These platforms have strong track records and multiple audits, but they are not backed by government insurance.

[Security and Risk](https://docs.mamo.bot/behind-the-scenes/how-mamo-keeps-you-safe) covers these in more detail.

## At a glance

* Deposit USDC.
* Mamo allocates your funds to where they earn the most.
* Interest and rewards increase your balance.
* Rewards convert into USDC automatically.
* Control stays with you.

Your USDC, earning steadily in the background.
