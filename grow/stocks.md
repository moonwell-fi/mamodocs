---
description: A basket of tokenized stocks, kept on target for you
---

# 📈 Stocks

<!-- TODO (Chris): add Stocks Account hero image here, e.g. <figure><img src="../.gitbook/assets/stocks-account.png" alt=""><figcaption></figcaption></figure> -->

## What is the Stocks Account?

The Mamo Stocks Account lets you hold a basket of tokenized stocks on Base. You choose the stocks and the weights, deposit USDC, and Mamo keeps the basket on target. When a stock drifts away from the weight you set, Mamo trades it back. You do not place orders, watch prices, or rebalance by hand.

Unlike the USDC, Bitcoin, and Ethereum Accounts, the Stocks Account does not earn interest. There is no APY. Its value rises and falls with the prices of the stocks it holds, so it is a way to hold stocks with discipline, not a yield product.

{% hint style="info" %}
The stocks in your account are tokenized stocks issued by [**Coinbase**](https://www.coinbase.com) and native to [**Base**](https://www.base.org/). Each token, such as **AAPLc** or **NVDAc**, is backed by real shares held by a custodian. The tokens trade onchain around the clock, including weekends.
{% endhint %}

## How it works

You start by building a basket. Pick up to ten stocks from the supported list, give each a target weight of at least 5%, and decide how much to keep in USDC as cash. The weights add up to 100%. Then deposit USDC and Mamo buys the stocks to match your targets.

From there, Mamo watches the basket continuously. Stock prices move, so the weights drift. When a position drifts more than 5 percentage points from its target, Mamo trades it back toward target. This tends to trim what has risen and add to what has fallen. New deposits are invested the same way. You can change your basket at any time, and Mamo will trade toward the new targets.

| Mamo Stocks Account                                                                 |
| ----------------------------------------------------------------------------------- |
| **Supported stocks:** AAPLc, AMZNc, GOOGLc, METAc, MSFTc, MSTRc, MUc, NVDAc, PLTRc, SNDKc, SPCXc, TSLAc |
| **Trading:** rebalances through [**CoW Protocol**](https://cow.fi/), sales on [**Aerodrome**](https://aerodrome.finance/) **(**[**Base**](https://www.base.org/)**)** |

The supported list is set by Mamo and can grow or shrink over time. The app always shows the current list.

## How your account changes in value

Your account is valued in USDC at all times. Its value is the sum of your stock holdings at current prices, plus the USDC you keep as cash.

Growth comes only from the stocks going up. If they go down, your balance goes down. Mamo does not add interest or rewards to this account, and there is no reward conversion step. What you hold is what you chose.

## How trades are protected

Mamo can only propose trades. Your account checks every one before it settles, and rejects any trade that fails the rules.

Each rebalance must fill at no worse than 1% below a reference price. That reference is the stock's recent average price in its onchain Aerodrome pool, not a single quote, which makes it harder to move. After the trade, both sides must sit within 5 percentage points of their targets. Mamo never buys a stock that is not in your basket.

When the US stock market is closed, Mamo does not buy stocks. Deposits wait in USDC until the market opens, and Mamo only sells a stock back toward its target when its onchain price is above the last market price. MUc and PLTRc do not trade at all while the market is closed. This keeps your account from buying into thin, off-hours prices.

## Fees and limits

The Stocks Account charges a management fee of 1% per year on the account's value. The fee accrues continuously and is paid as the account trades and whenever you deposit or withdraw. There is no deposit fee and no withdrawal fee.

| Limit                                 | Value       |
| ------------------------------------- | ----------- |
| Minimum account value after a deposit | 100 USDC    |
| Maximum net deposits per account      | 25,000 USDC |
| Stocks per basket                     | Up to 10    |
| Minimum weight per stock              | 5%          |

Net deposits means USDC deposited minus USDC withdrawn. Gains do not count toward the cap.

## Security and control

Your stocks stay yours from start to finish. Mamo never takes custody. Deposits move into a personal smart contract account owned by you. Only you can withdraw, change the basket, or approve an upgrade.

Mamo's role is limited to proposing trades that pass your account's checks. It can never withdraw your funds. If you prefer, you can switch Mamo's trading off for your account at any time. Withdrawals keep working either way.

## Access anytime

Withdraw whenever you want. No lockups, no waiting periods, and no market-hours restrictions, because the pools trade 24/7.

You can withdraw in two ways:

* **As USDC.** Your account sells the stocks needed on Aerodrome inside your own withdrawal transaction. You set a price tolerance of up to 5%, and the whole withdrawal reverts if any sale would fill below your floor.
* **In kind.** Nothing is sold. The stock tokens and USDC go straight to your wallet as they are. This always works, even when a stock cannot be priced, and it is the recommended path for large exits.

## Things to know

* **Not a yield product.** Your return is the price change of your stocks, minus the 1% fee and the cost of trading.
* **Issuer and custody.** The stock tokens are issued by Coinbase and backed by shares held by a custodian. Coinbase can pause a token or freeze a specific address's balance. One frozen token does not trap the others, since in-kind withdrawals still work for the rest.
* **Onchain liquidity.** The stock pools on Aerodrome are small. Their prices can drift from the real market price, especially while the US market is closed. Large USDC withdrawals may get worse prices or fail their floor. In-kind withdrawals always work.
* **Eligibility.** Tokenized stocks are not available in every jurisdiction. Availability of the Stocks Account depends on where you live. See the [**Terms of Service**](../legal/terms-of-service.md) for details.
* **Base outages.** If Base's sequencer goes down, stocks cannot be priced until one hour after it recovers. In that window Mamo does not trade, USDC withdrawals pay out only the idle USDC, and in-kind withdrawals keep working.

***

## At a glance

* Build a basket of up to ten tokenized stocks plus USDC cash.
* Deposit USDC. Mamo buys to match your targets.
* Mamo rebalances when a stock drifts more than 5 points off target.
* No interest, no rewards, no APY. Value follows the stocks.
* 1% yearly management fee. No deposit or withdrawal fees.
* Withdraw as USDC or in kind, any time. Control stays with you.

Your stocks, kept on target in the background.
