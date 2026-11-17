# 🛠️ How It Works

## How Mamo works

Mamo is built to feel simple. That simplicity is intentional. Behind the simple surface, smart, automated systems work quietly to keep your money safe, productive and always within your control.

Whether you are growing stablecoins in the USDC Account, building your Bitcoin stack with cbBTC, putting ETH to work, depositing MAMO or holding a portfolio of stocks, Mamo takes care of the complexity so you can focus on the bigger picture. This page follows your money from the moment you open an account.

### The accounts at a glance

<table data-header-hidden><thead><tr><th width="220.93463134765625"></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Account</strong></td><td><strong>What Mamo does with your deposit</strong></td><td><strong>What you earn</strong></td></tr><tr><td><a href="../save/usd-coin-usdc.md">USDC</a>, <a href="../save/bitcoin-cbbtc.md">Bitcoin</a>, <a href="../save/ethereum-eth.md">Ethereum</a></td><td>Lends your deposit through Moonwell or Morpho, choosing the market or vault with the highest available rate</td><td>Borrower interest, plus WELL and MORPHO rewards converted into your deposited asset</td></tr><tr><td><a href="../earn/mamo-account.md">MAMO</a></td><td>Keeps your MAMO deposited so your balance counts toward each weekly drop</td><td>A weekly share of the fees Mamo collects, paid through the Mamo Drop</td></tr><tr><td><a href="../invest/stocks.md">Stocks</a></td><td>Buys the stocks you chose and rebalances them toward your target weights</td><td>No interest or rewards. The value follows the prices of the stocks you hold</td></tr></tbody></table>

## Step by step

### 1. Account creation

When you open a Mamo account (USDC, Bitcoin, Ethereum, MAMO or Stocks), Mamo deploys dedicated smart contracts linked directly to your wallet. You keep full control of your funds. Mamo never takes custody, and only you can move them.

### 2. Funds put to work

What happens next depends on the account.

* **USDC, Bitcoin and Ethereum.** Mamo allocates your deposit to Moonwell or Morpho, automatically selecting the market or vault with the highest available rate.
* **MAMO.** Your balance earns a share of the fees Mamo collects each week. The drop lands every Wednesday at 0:00 UTC.
* **Stocks.** Mamo buys the stocks you chose and rebalances them back toward your target weights when they drift.

### 3. Earning begins

In the USDC, Bitcoin and Ethereum accounts, you earn interest from borrowers, plus extra rewards in WELL and MORPHO tokens. Mamo quietly collects all of this for you.

In the MAMO Account, rewards arrive through the Mamo Drop and can include MAMO, Bitcoin, Ethereum, USDC and stocks.

Stocks work differently. A stock portfolio earns no interest or rewards, and its value follows the prices of the stocks you hold.

### 4. Smart conversion

In the USDC, Bitcoin and Ethereum accounts, when rewards reach about $5, Mamo converts them into more of your deposited asset using CoW Swap, with prices verified by Chainlink oracles. This keeps pricing fair and avoids small, inefficient swaps.

The MAMO Account follows your reward setting instead. Once your rewards are worth more than $1, Mamo either compounds them into MAMO or reinvests each one into the matching account.

### 5. Auto-compounding

Interest and converted rewards are folded back into your balance automatically. Your earnings generate more earnings, with no manual steps and no spreadsheets.

### 6. Always accessible

Withdraw at any time. Your funds go straight to your wallet, even if Mamo is offline. You can add, pause or withdraw without lockups or waiting periods. Stock portfolios offer two ways to withdraw, which the [Stocks](../invest/stocks.md) page explains.

### 7. Updates with permission

If Mamo ships an upgrade, you get a clear prompt and must approve any change before the change happens. There are no surprise migrations. You stay in control.

## What stays the same in every account

* **Your wallet owns your account.** Funds sit in smart contracts linked to your wallet, and Mamo never takes custody.
* **Only you can withdraw.** Mamo can guide where your funds work, but cannot move them out.
* **No lockups.** You can add, pause or withdraw on your own terms.
* **Upgrades need your approval.** Nothing changes unless you agree.
* **Everything runs on Base.** Your accounts are transparent smart contracts on the Base network.

## Mamo's infrastructure, visualized

<figure><img src="../.gitbook/assets/mamo-contracts.drawio (1).png" alt=""><figcaption></figcaption></figure>

## Further reading

* [Security and Risk](https://docs.mamo.bot/behind-the-scenes/how-mamo-keeps-you-safe) explains how your funds are protected and what can go wrong.
* [Audits](https://docs.mamo.bot/behind-the-scenes/audits) lists the independent reviews of Mamo's contracts.
* [Contract Addresses](https://docs.mamo.bot/technical/contract-addresses) lists the contracts and tokens Mamo uses on Base.
