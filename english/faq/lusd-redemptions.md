# Redemptions and LUSD Price Stability

### How does LUSD closely follow the price of USD?&#x20;

The ability to redeem LUSD for ETH at face value (i.e. 1 LUSD for $1 of ETH) and the minimum collateral ratio of `110%` create a price floor and price ceiling (respectively) through arbitrage opportunities. We call these "hard peg mechanisms" since they are based on direct processes.&#x20;

LUSD also benefits from less direct mechanisms for USD parity — called "soft peg mechanisms". One of these mechanisms is parity as a Schelling point. Since Liquity treats LUSD as being equal to USD, parity between the two is an implied equilibrium state of the protocol. Another of these mechanisms is the borrowing fee on new debts. As redemptions increase (implying LUSD is below $1), so too does the `baseRate` — making borrowing less attractive which keeps new LUSD from hitting the market and driving the price below $1.&#x20;

Read more about the price stability of LUSD [here](https://www.liquity.org/blog/on-price-stability-of-liquity).&#x20;

### What are redemptions?

A redemption is the process of exchanging LUSD for ETH at face value, as if 1 LUSD is exactly worth $1. That is, for x LUSD you get x Dollars worth of ETH in return.

Users can redeem their LUSD for ETH at any time without limitations. However, a redemption fee might be charged on the redeemed amount.

For example, if the current redemption fee is 1%, the price of ETH is $500 and you redeem 100 LUSD, you would get 0.198 ETH (0.2 ETH minus a redemption fee of 0.002 ETH).

Note that the redeemed amount is taken into account for calculating the base rate and might have an impact on the redemption fee, especially if the amount is large.

Read more about redemptions [here](https://www.liquity.org/blog/understanding-liquitys-redemption-mechanism).

### Is a redemption the same as paying back my debt?&#x20;

No, redemptions are a completely separate mechanism. All one has to do to pay back their debt is adjust their Trove's debt and collateral.&#x20;

### How is the redemption fee calculated?

Under normal operation, the redemption fee is given by the formula `(baseRate + 0.5%) * ETHdrawn`

### How is the `baseRate` calculated?

Redemption fees are based on the `baseRate` state variable in Liquity, which is dynamically updated. The `baseRate` increases with each redemption, and decays to 0 over time with a 12 hour half life.

Upon each redemption:

* `baseRate` is decayed based on time passed since the last fee event
* `baseRate` is incremented by an amount proportional to the fraction of the total LUSD supply that was redeemed
* The redemption fee is given by `(baseRate  + 0.5%) * ETHdrawn`

`baseRateNew = baseRateOld + redeemedLUSD / (2 * totalLUSD)`

Where `baseRateOld` is the value just prior to this redemption, and `baseRateNew` is the new value (and gets applied to this redemption).

### As a borrower, do I lose money if I'm redeemed against?&#x20;

If your Trove is redeemed against, you _do not_ incur a net loss. However, you will lose some of your ETH exposure. Your Trove's collateral ratio will also improve after a redemption.&#x20;

### How can I avoid being redeemed against?&#x20;

The best way to avoid being redeemed against is by maintaining a high collateral ratio relative to the rest of the Trove's in the system. Remember: The riskiest Troves (i.e. lowest collateralized Troves) are first in line when a redemption takes place.&#x20;
