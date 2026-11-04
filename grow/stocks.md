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

Stock prices change every day, so your portfolio slowly moves away from your targets. A stock that goes up takes up more of your portfolio. A stock that goes down takes up less.

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

### **5. Change your portfolio whenever you like**

You can add a stock, remove one or change your targets at any time. Mamo then trades toward your new targets the same way. If you remove a stock, Mamo sells it and puts the money into the stocks you’re keeping.

#### **Why a stock can sit slightly off target**

Mamo skips trades that are too small to be worth making. In a small portfolio, especially one close to the 100 USDC minimum, a stock can sit a few points outside its range for a while. You’ll see this most often right after adding a new stock, or when your cash is a little above target.

This is normal and nothing is lost. It sorts itself out when prices move further, when you deposit again, or when you change your portfolio.

#### **Which stocks are available**

Mamo sets the list of stocks you can choose from, and it can change over time. The app always shows the current list.

| Mamo Stocks                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Supported stocks:** AAPLc, AMZNc, GOOGLc, METAc, MSFTc, MSTRc, MUc, NVDAc, PLTRc, SNDKc, SPCXc, TSLAc                                                                    |
| **Trading:** rebalances through [**CoW Protocol**](https://cow.fi/), sales on [**Aero**](https://app.aero.xyz/liquidity/pools) **(**[**Base**](https://www.base.org/)**)** |

## How your portfolio changes in value

Your portfolio is valued in USDC (US dollars). Its value is the sum of your stock holdings at current prices, plus the USDC you keep as cash.

Growth comes only from the stocks going up. If they go down, your balance goes down. There’s no interest and no rewards on Mamo Stocks. What you hold is what you chose.

## How trades are protected

Mamo can suggest trades, but your portfolio checks every one before it goes through. Any trade that breaks the rules is rejected.

* **Fair prices.** Every trade must get have a price no more than 1% worse than the stock’s recent average price. Mamo uses an average, not a single quote, so one sudden swing can’t push a bad trade through.
* **Stays on target.** After each trade, both sides must be within 5 points of their targets.
* **Only your picks.** Mamo never buys a stock you didn’t choose.



Mamo can only propose trades. Checks are carried out before any trade it settled, rejecting any trade that breaks the defined rules.

Each rebalance must fill at no worse than 1% below a reference price. That reference is the stock's recent average price on [**Aero**](https://app.aero.xyz/liquidity/pools), not a single quote, which makes it harder to move.&#x20;

After the trade, both sides must sit within 5 percentage points of their targets. Mamo never buys a stock that is not in your portfolio.

When the US stock market is closed, Mamo won't buy stocks. New deposits wait as USDC until it opens. Mamo will only sell a stock back toward its target if the price is higher than when the market last closed. This keeps Mamo from buying in quiet hours, when there are fewer traders and prices can be less reliable.

## Fees and limits

Mamo Stocks has a 1% yearly fee, based on the value of your portfolio. It’s spread evenly across the year, not charged per trade. No deposit fees. No withdrawal fees.

| Limit                                 | Value        |
| ------------------------------------- | ------------ |
| Minimum account value after a deposit | 100 USDC     |
| Maximum net deposits per account      | 100,000 USDC |
| Stocks per portfolio                  | Up to 10     |
| Minimum weight per stock              | 5%           |

Net deposits are the USDC you’ve put in minus what you’ve taken out.&#x20;

Gains don’t count toward the cap.

## Security and control

Your stocks stay yours from start to finish. Mamo never takes custody. Deposits move into a personal account owned by you. Only you can withdraw, change the portfolio, or approve an upgrade.

Mamo's role is limited to proposing trades that pass your account's checks. Mamo can never withdraw your funds. You can turn off Mamo’s trading for your portfolio whenever you like. Withdrawals work either way.

## Access anytime

Withdraw whenever you want. No lockups, no waiting periods, and no market-hours restrictions, because stocks are able to trade 24/7.

You can withdraw in two ways:

* **As USDC.** Mamo sells the stocks you need as part of your withdrawal.
* **In kind.** Nothing is sold. Nothing is sold. Your stock tokens and any USDC go straight to your wallet as they are. This always works, even when a stock can’t be priced, and it’s the best option for large withdrawals.

## Things to know

* **No savings rate.** Your return is how your stocks perform, minus the 1% yearly fee and small trading costs.
* **Issuer and custody.** [Coinbase](https://www.coinbase.com/en-gb) issues the stock tokens, and real shares back each one. Coinbase can pause a token or freeze it for a specific wallet. If that happens to one stock, the rest aren’t affected. You can still withdraw them as stocks.
* **Prices outside market hours.** Fewer people trade these stocks than on the stock market, so prices can move away from the real market price, especially when the US market is closed. Large withdrawals as USDC may get a worse price or be cancelled. Withdrawing as stocks always works.
* **Eligibility.** Stocks are only available in eligible jurisdictions outside of the U.S. See the [**Terms of Service**](../legal/terms-of-service.md) for details.
* **Small portfolios drift more.** Mamo skips trades that are too small to be worth placing, so a position in a small portfolio can stay a few points outside the 5-point band for a while. It catches up when prices move, when you deposit, or when you change the portfolio.
* **Base outages.** If the Base network goes down, stock prices can’t be checked until an hour after it’s back. During that time Mamo won’t trade, USDC withdrawals pay out only the cash in your portfolio, and withdrawing as stocks still works.

***

## At a glance

* Own a portfolio of up to ten stocks, plus cash if you want it.
* Deposit USDC and Mamo buys to match your targets.
* Mamo rebalances when a stock drifts more than 5 points off target.
* No interest or rewards. Your portfolio follows your stocks.
* 1% yearly fee. No deposit or withdrawal fees.
* Withdraw as USDC or as stocks, any time.

Your stocks, kept on target in the background.
