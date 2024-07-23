# Recovery Mode

### What is Recovery Mode?&#x20;

Recovery Mode kicks in when the [Total Collateral Ratio (TCR)](https://docs.liquity.org/faq/recovery-mode#what-is-the-total-collateralization-ratio) of the system falls below `150%`.

During Recovery Mode, Troves with a collateral ratio **below 150%** can be liquidated.&#x20;

Moreover, the system blocks borrower transactions that would further decrease the TCR. New LUSD may only be issued by adjusting existing Troves in a way that improves their collateral ratio, or by opening a new Trove with a collateral ratio`>=150%`. In general, if an existing Trove's adjustment reduces its collateral ratio, the transaction is only executed if the resulting TCR is above `150%`.&#x20;

### What is the Total Collateral Ratio?

The Total Collateral Ratio or TCR is the ratio of the Dollar value of the entire system collateral at the current ETH:USD price, to the entire system debt. In other words, it's the sum of the collateral of all Troves expressed in USD, divided by the debt of all Troves expressed in LUSD.

### What is the purpose of Recovery Mode?&#x20;

The goal of Recovery Mode is to incentivize borrowers to behave in ways that promptly raise the TCR back above 150%, and to incentivize LUSD holders to replenish the Stability Pool.

Economically, Recovery Mode is designed to encourage collateral top-ups and debt repayments, and also itself acts as a self-negating deterrent: the possibility of it occurring actually guides the system away from ever reaching it. Recovery Mode is not a desirable state for the system.&#x20;

### **What are the fees during Recovery Mode?**

While Recovery Mode has no impact on the redemption fee, the borrowing fee is set to `0%` to maximally encourage borrowing (within the limits described [above](https://docs.liquity.org/faq/recovery-mode#what-is-recovery-mode)).

### **How can I make my Trove safe in Recovery Mode?**

By increasing your collateral ratio to `150%` or greater, your Trove will be protected from liquidation. This can be done by adding collateral, repaying debt, or both.

### Can I be liquidated if my collateral ratio is below `150%` in Recovery Mode?&#x20;

Yes, you can be liquidated below `150%` in Recovery Mode if your Trove’s collateral ratio is below that level. In order to avoid liquidation regardless of system mode, a user should keep their collateral ratio above `150%`

### How do liquidations work in Recovery Mode?&#x20;

* ICR = Individual Collateral Ratio&#x20;
* MCR = Minimum Collateral Ratio&#x20;
* TCR = Total Collateral Ratio&#x20;
* SP = Stability Pool&#x20;

| Condition                                               | Liquidation Behavior                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ICR <=100%                                              | Redistribute all debt and collateral (minus ETH gas compensation) to active Troves.                                                                                                                                                                                                                                                                                                               |
| 100% < ICR < MCR & SP LUSD > Trove debt                 | LUSD in the Stability Pool equal to the Trove's debt is offset with the Trove's debt. The Trove's ETH collateral (minus ETH gas compensation) is shared between depositors.                                                                                                                                                                                                                       |
| 100% < ICR < MCR & SP LUSD < Trove debt                 | The total Stability Pool LUSD is offset with an equal amount of debt from the Trove. A fraction of the Trove's collateral (equal to the ratio of its offset debt to its entire debt) is shared between depositors. The remaining debt and collateral (minus ETH gas compensation) is redistributed to active Troves.                                                                              |
| MCR <= ICR < 150% & SP LUSD >= Trove debt               | The Stability Pool LUSD is offset with an equal amount of debt from the Trove. A fraction of ETH collateral with dollar value equal to `1.1 * debt` is shared between depositors. Nothing is redistributed to other active Troves. Since its ICR was `> 1.1`, the Trove has a collateral remainder, which is sent to the `CollSurplusPool` and is claimable by the borrower. The Trove is closed. |
| MCR <= ICR < 150% & SP LUSD < Trove debt                | Do nothing.                                                                                                                                                                                                                                                                                                                                                                                       |
| ICR >= 150%                                             | Do nothing.                                                                                                                                                                                                                                                                                                                                                                                       |

### How much of a Troves collateral can be liquidated in Recovery Mode?&#x20;

In Recovery Mode, liquidation loss is capped at `110%` of a Trove's collateral. Any remainder, i.e. the collateral above `110%` (and below the TCR), can be reclaimed by the liquidated borrower using the standard web interface.

This means that a borrower will face the same liquidation “penalty” (`10%`) in Recovery Mode as in Normal Mode if their Trove gets liquidated.
