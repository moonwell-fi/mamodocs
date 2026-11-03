---
description: Stocks, managed for you
---

# 📈 Stocks

<figure><img src="../.gitbook/assets/mamo-stocks-1y-x-header-2x1 (2).png" alt=""><figcaption></figcaption></figure>

## What is Mamo Stocks?

Mamo Stocks lets you own a portfolio of [tokenized stocks](https://www.coinbase.com/en-au/tokenize) on [Base](https://www.base.org/), managed for you. You choose the stocks and how much of each you want, deposit USDC, and Mamo keeps your portfolio on target. When a stock moves too far from where you set it, Mamo buys or sells to bring it back. You don’t place orders, watch prices or rebalance by hand.

Mamo Stocks doesn’t earn a savings rate like your USDC, Bitcoin and Ethereum do. Your portfolio rises and falls with the prices of the stocks you hold. It’s a calm, steady way to own stocks. It isn’t a way to earn interest.

{% hint style="info" %}
Each stock you hold with Mamo is a token issued by [Coinbase](https://www.coinbase.com) on Base, like AAPLc for Apple or NVDAc for Nvidia. Every token is backed 1-to-1 by a real share, held by a regulated custodian. They can be bought and sold any time, weekends included.
{% endhint %}

## How it works

### **1. Build your portfolio**

Start by choosing the stocks you want to own. You can pick up to ten from the list in the app.

Then decide how much of your portfolio goes into each one. These are your targets. Each stock needs at least 5%. You can also keep part of your portfolio in USDC as cash. Cash is optional and works like any other target. Everything adds up to 100%.

For example:

* Apple: 40%
* Nvidia: 40%
* Cash: 20%

### **2. Deposit USDC**

The minimum deposit is 100 USDC. Once your USDC arrives, Mamo buys your stocks to match your targets. With 1,000 USDC and the example above, that’s 400 USDC of Apple, 400 USDC of Nvidia and 200 USDC kept as cash.

### **3. Mamo keeps your portfolio on target**

Stock prices change every day, so your portfolio will inevitably move away from your targets. A stock that goes up takes up more of your portfolio. A stock that goes down takes up less.

Mamo checks your portfolio all the time. Every stock has a range of 5 points either side of its target. With a 40% target, that range is 35% to 45%. As long as everything stays inside its range, Mamo leaves it alone. Once a stock moves outside its range, Mamo trades to bring it back.

#### **What a rebalance looks like**

Say Nvidia rises 30%. Your portfolio is now:

* Apple: 400 USDC (35.7%)
* Nvidia: 520 USDC (46.4%)
* Cash: 200 USDC (17.9%)

Nvidia is now 6.4 points above its target, which is outside its range. Mamo finds the stock that’s furthest over target and the one that’s furthest under. Here that’s Nvidia and Apple. Mamo then sells about 48 USDC of Nvidia and uses it to buy 48 USDC of Apple.

After the trade:

* Apple: 448 USDC (40%)
* Nvidia: 472 USDC (42.1%)
* Cash: 200 USDC (17.9%)

Everything is back inside its range. Mamo trimmed the stock that had grown and added to the one that had fallen behind, without you doing anything.

Mamo trades one pair at a time. When more than one stock is off target, Mamo repeats this until everything is back in range. Your cash is part of this too. If your cash grows too large, Mamo puts it to work in your stocks. If it drops too low, Mamo tops it back up.

### **4. Add more any time**

Each new deposit goes toward your targets. Mamo buys more of whatever is furthest below target, so new money helps bring your portfolio back into shape.

You start by building a portfolio. Pick up to ten stocks from the supported list, give each a target weight of at least 5%, and decide how much to keep in USDC as cash. The weights add up to 100%. Then deposit USDC and Mamo buys the stocks to match your targets.

From there, Mamo watches the portfolio continuously. Stock prices move, so the weights drift. When a position drifts more than 5 percentage points from its target, Mamo trades it back toward target. This tends to trim what has risen and add to what has fallen. New deposits are invested the same way. You can change your portfolio at any time, and Mamo will trade toward the new targets.

Each pass, Mamo pairs the most overweight position, cash included, with the most underweight one and trades the smaller of the two gaps. It skips trades that are too small to be worth placing. In a small portfolio, especially one near the 100 USDC minimum, a position can therefore sit a few points outside the band for a while, most often right after you add a stock or when cash is slightly above target. This is expected. It clears on its own when prices move further, when you deposit again, or when a portfolio change makes the gap large enough to trade. Nothing is lost. The weights are just further from target until then.

| Mamo Stocks                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Supported stocks:** AAPLc, AMZNc, GOOGLc, METAc, MSFTc, MSTRc, MUc, NVDAc, PLTRc, SNDKc, SPCXc, TSLAc                                                                    |
| **Trading:** rebalances through [**CoW Protocol**](https://cow.fi/), sales on [**Aero**](https://app.aero.xyz/liquidity/pools) **(**[**Base**](https://www.base.org/)**)** |

The supported list is set by Mamo and can grow or shrink over time. The app always shows the current list.

## How your portfolio changes in value

Your portfolio is valued in USDC (US dollars). Its value is the sum of your stock holdings at current prices, plus the USDC you keep as cash.

Growth comes only from the stocks going up. If they go down, your balance goes down. Mamo does not add interest or rewards to this account, and there is no reward conversion step. What you hold is what you chose.

## How trades are protected

Mamo can only propose trades. Your account checks every one before it settles, and rejects any trade that fails the rules.

Each rebalance must fill at no worse than 1% below a reference price. That reference is the stock's recent average price in its onchain Aerodrome pool, not a single quote, which makes it harder to move. After the trade, both sides must sit within 5 percentage points of their targets. Mamo never buys a stock that is not in your portfolio.

When the US stock market is closed, Mamo does not buy stocks. Deposits wait in USDC until the market opens, and Mamo only sells a stock back toward its target when its onchain price is above the last market price. MUc and PLTRc do not trade at all while the market is closed. This keeps your account from buying into thin, off-hours prices.

## Fees and limits

The Stocks Account charges a management fee of 1% per year on the account's value. The fee accrues continuously and is paid as the account trades and whenever you deposit or withdraw. There is no deposit fee and no withdrawal fee.

| Limit                                 | Value        |
| ------------------------------------- | ------------ |
| Minimum account value after a deposit | 100 USDC     |
| Maximum net deposits per account      | 100,000 USDC |
| Stocks per portfolio                  | Up to 10     |
| Minimum weight per stock              | 5%           |

Net deposits means USDC deposited minus USDC withdrawn. Gains do not count toward the cap.

## Security and control

Your stocks stay yours from start to finish. Mamo never takes custody. Deposits move into a personal smart contract account owned by you. Only you can withdraw, change the portfolio, or approve an upgrade.

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
* **Small portfolios drift more.** Mamo skips trades that are too small to be worth placing, so a position in a small portfolio can stay a few points outside the 5-point band for a while. It catches up when prices move, when you deposit, or when you change the portfolio.
* **Base outages.** If Base's sequencer goes down, stocks cannot be priced until one hour after it recovers. In that window Mamo does not trade, USDC withdrawals pay out only the idle USDC, and in-kind withdrawals keep working.

***

## At a glance

* Build a portfolio of up to ten tokenized stocks plus USDC cash.
* Deposit USDC. Mamo buys to match your targets.
* Mamo rebalances when a stock drifts more than 5 points off target and the trade is large enough to place.
* No interest, no rewards, no APY. Value follows the stocks.
* 1% yearly management fee. No deposit or withdrawal fees.
* Withdraw as USDC or in kind, any time. Control stays with you.

Your stocks, kept on target in the background.
