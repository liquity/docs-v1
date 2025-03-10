# General

### **What is Liquity?**

Liquity is a decentralized borrowing protocol that allows you to draw [interest-free loans](borrowing.md) against Ether used as [collateral](borrowing.md#what-do-you-mean-by-collateral). Loans are paid out in LUSD (a USD pegged stablecoin) and need to maintain a [minimum collateral ratio](borrowing.md#what-is-the-minimum-collateral-ratio-mcr-and-the-recommended-collateral-ratio) of `110%`.

In addition to the collateral, the loans are secured by a [Stability Pool](stability-pool-and-liquidations.md#what-is-the-stability-pool) containing LUSD and by fellow borrowers collectively acting as guarantors of last resort. Learn more about these mechanisms under [Liquidation](stability-pool-and-liquidations.md#what-are-liquidations).

Liquity as a protocol is non-custodial, immutable, and governance-free.

### **What’s the motivation behind Liquity?**

Stable-value assets are an essential building block for Ethereum applications and have grown to represent tens of billions of dollars in value.&#x20;

However, the vast majority of this value is in the form of fiat-collateralized stablecoins like Tether and USDC. Decentralized stablecoins like DAI and sUSD make up only a small portion of the total stablecoin supply, meaning the vast majority of stablecoins are centralized.

Liquity addresses this by creating a more capital efficient and user-friendly way to borrow stablecoins. Furthermore, Liquity is governance-free, ensuring that the protocol remains decentralized.

### **What are the key benefits of Liquity?**

Liquity’s key benefits include:

* [0% interest rate](borrowing.md#how-can-you-offer-borrowing-at-a-0-interest-rate) — as a borrower, there’s no need to worry about constantly accruing debt
* [Minimum collateral ratio](borrowing.md#what-is-the-minimum-collateral-ratio-mcr-and-the-recommended-collateral-ratio) of `110%` — more efficient usage of deposited ETH
* Governance free — all operations are algorithmic and fully automated, and protocol parameters are set at time of contract deployment
* Directly [redeemable](lusd-redemptions.md#what-are-redemptions) —  LUSD can be redeemed at face value for the underlying collateral at any time
* Fully decentralized — Liquity contracts have no admin keys and will be accessible via multiple interfaces hosted by different [Frontend Operators](frontend-operators.md), making it censorship resistant

### **Can Liquity be upgraded or changed?**

No. Liquity has no admin key, and nobody can alter the rules of the system in any way. The smart contract code is completely immutable.

### **How can I use Liquity?**

You first need to choose a web interface (aka [frontend](frontend-operators.md)) to access the system. The core team building the protocol **will not** operate a frontend. Liquity is instead accessed by third-party frontend applications and integration services.

You can find a list of frontends [here](https://www.liquity.org/frontend).&#x20;

### What are the main use cases of Liquity?

1. Borrow LUSD against ETH by opening a [Trove](borrowing.md#what-is-a-trove)
2. Secure Liquity by providing LUSD to the [Stability Pool](stability-pool-and-liquidations.md#what-is-the-stability-pool) in exchange for rewards
3. Stake LQTY to earn the fee revenue paid for borrowing or redeeming LUSD
4. Redeem `1 LUSD` for `1 USD` worth of ETH when the LUSD peg falls below `$1`

### What are LUSD and LQTY?

LUSD is the USD-pegged stablecoin used to pay out loans on the Liquity protocol. At any time it can be redeemed against the underlying [collateral](borrowing.md#what-do-you-mean-by-collateral) at face value. Learn more about the [stability mechanism](https://docs.liquity.org/faq/lusd-redemptions).

LQTY is the secondary token issued by Liquity. It captures the fee revenue that is generated by the system and incentivizes early adopters and frontends. The total LQTY supply is capped at `100,000,000 tokens`. For more information on how the tokens are allocated and released over time, please refer to [LQTY Rewards and Distribution](https://docs.liquity.org/faq/lqty-distribution-and-rewards).

### What do I need in order to use Liquity?

To borrow LUSD, all you need is a wallet (e.g. MetaMask) and sufficient Ether to open a [Trove](borrowing.md#what-is-a-trove) and pay the gas fees.&#x20;

To become a [Stability Pool](stability-pool-and-liquidations.md#what-is-the-stability-pool) depositor or LQTY staker, you need to have LUSD and/or LQTY tokens. LUSD can be borrowed by opening a Trove while LQTY can be earned as a Stability Pool depositor. You can also use Uniswap or another (decentralized) exchange to buy the tokens on the open market.

### Does Liquity charge any fees?

There is a one-off fee whenever LUSD is borrowed, and when LUSD is redeemed:

* For borrowers, there is a borrowing fee on loans as a percentage of the drawn amount (in LUSD).
* For redeemers, there is a redemption fee on the amount paid to users by the system (in ETH) when exchanging LUSD for ETH. Note that redemption is separate from repaying your loan as a borrower, which is free of charge.

Both fees depend on the redemption volumes, i.e. they increase upon every redemption in function of the redeemed amount, and decay over time as long as no redemptions take place. The intent is to throttle large redemptions with higher fees, and to throttle borrowing directly after large redemption volumes. The fee decay over time ensures that the fee for both borrowers and redeemers will “cool down”, while redemptions volumes are low.

The fees cannot become smaller than `0.5%` (except in [Recovery Mode](https://docs.liquity.org/faq/recovery-mode#what-are-the-fees-during-recovery-mode)), which protects the redemption facility from being misused by arbitrageurs front-running the price feed. The borrowing fee is capped at `5%`, keeping the system (somewhat) attractive for borrowers even in phases where the monetary is contracting due to redemptions. Other than that, the two fees are identical and are depicted as "Fee" in the following exemplary chart:

![](<../.gitbook/assets/Screenshot 2021-03-27 at 18.36.44.png>)

### How can I earn money using Liquity?

There are two different ways to generate revenue using Liquity:

* Deposit LUSD to the [Stability Pool](stability-pool-and-liquidations.md#what-is-the-stability-pool) and earn liquidation gains (in ETH) and LQTY rewards.&#x20;
* [Stake](staking.md) LQTY and earn LUSD and ETH revenue from borrowing and redemption fees.

### Can I lose my funds?

As a non-custodial system, all the tokens sent to the protocol will be held and managed algorithmically without the interference of any person or legal entity. That means your funds will only be subject to the rules set forth in the smart contract code, which has been audited twice by Trail of Bits and once by Coinspect (find their reports [here](https://docs.liquity.org/documentation/resources)).

There are two scenarios under which you may lose a part of your funds:

* You are a borrower (Trove owner) and your collateral in ETH is [liquidated](stability-pool-and-liquidations.md#what-are-liquidations). You will still keep your borrowed LUSD, but your Trove will be closed and your collateral will be used to compensate [Stability Pool](stability-pool-and-liquidations.md#what-is-the-stability-pool) depositors.
* You are a Stability Pool depositor and your deposited LUSD is used to repay debt from liquidated borrowers. Since liquidations are triggered any time borrowers’ collateral drops below `110%`, you will receive more ETH in return with a very high probability. However, if ETH decreases in price and you maintain exposure, you may lose value in your total pool deposits.

Please note that LUSD isn't perfectly pegged to the USD, and can deviate slightly in both directions under certain market conditions. See [On Price Stability of LUSD](https://www.liquity.org/blog/on-price-stability-of-liquity) for more details.

Although the system is diligently audited, a hack or a bug that results in losses for the users can never be fully excluded (see [disclaimer](https://liquity.org/disclaimer)).
