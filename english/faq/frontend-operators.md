# Frontend Operators

### **Why should I become a Frontend Operator?**

Frontend Operators provide a web interface to the end-user enabling them to interact with the Liquity protocol. For that service, they will be rewarded with a share of the LQTY tokens their users generate.

LQTY rewards are being awarded to Stability Pool depositors and then proportionally shared between the users themselves and the Frontend Operator. How much each party gets is determined by the Kickback Rate which is set by the Frontend Operator and can range between 0% and 100%.

Setting a _high_ Kickback Rate will make the Frontend Operator attractive to users**,** but offering a nice interface and additional functionalities might allow for a lower kickback rate while still garnering user interest.

Check the [Liquity Runs on Decentralized Frontends](https://youtu.be/ipbNQMiIy1M) video for more details.&#x20;

### How can I run a frontend?

You can either install our [front end launch kit](https://github.com/liquity/liquity) or integrate our protocol in your environment using our [Frontend SDK](https://docs.liquity.org/documentation/sdk).

### What type of rewards do I receive as a frontend?&#x20;

Frontend rewards are paid out in LQTY. Learn more about LQTY [here](general.md#what-are-lusd-and-lqty).

### How is a frontend’s reward share calculated?

Rewards are calculated based on the total deposits tagged by the frontend. In a LQTY reward event generating `LQTY_d` for a deposit `d` made through a frontend with kickback rate`k`, the frontend receives`(1-k)*LQTY_d` and the user receives`k * LQTY_d`.

### Where do frontend rewards come from?&#x20;

Frontend rewards come from the same pool as user rewards. Frontends earn a share of the 32,000,000 LQTY being distributed to users based on the frontend's kickback rate and the total rewards accrued by its users.&#x20;

### How are frontend rewards paid out?&#x20;

Each [Stability Pool ](stability-pool-and-liquidations.md#what-is-the-stability-pool)deposit is tagged by the Ethereum address of the front end through which the deposit was made. This address is where the frontend’s LQTY rewards accrue.&#x20;

### How do frontend tags work?&#x20;

A frontend tag is applied to a Stability Pool deposit when a user calls `provideToSP(uint _amount, address _frontEndTag)`. This tag will remain attached to a user's deposit _even if they use another frontend_. The tag can also be a 0 address, meaning the user will receive 100% of their accrued LQTY rewards.&#x20;

In order to add a new frontend tag and benefit from a different kickback rate, a user will have to completely withdraw their Stability Pool deposit, and redeposit using the new frontend and new tag. As a Frontend Operator, keeping this dynamic in mind is important.&#x20;

### Do frontends have to be pre-approved?&#x20;

No, registering with Liquity's smart contracts as a frontend is a trustless process. This is done by calling the `registerFrontEnd(uint _kickbackRate)` function on the Stability Pool smart contract. The kickback rate is a value between \[0,1] (e.g. 0.8 = 80% kickback rate).&#x20;

### How does a frontend get added to the liquity.org registry?&#x20;

Frontends can view the registry listing process [here](https://github.com/liquity/frontend-registry).&#x20;

### What is the kickback rate?

In order to ensure that the Liquity protocol is decentralized from day 1, the Liquity team will not host or run a frontend to interact with the Liquity contracts. As such, it is incumbent upon Liquity community members to act as Frontend Operators and run interfaces for users.&#x20;

In order to incentivize this behavior,  each Frontend Operator may set a rate between 0 and 100% that determines the fraction of LQTY that will be paid out as a kickback to the Stability Providers using the frontend. If a frontend set the kickback rate to 60%, their users would receive 60% of their earned rewards while the frontend receives the remaining 40%.

### Can a Frontend Operator change their kickback rate?&#x20;

Yes and no. Once an address is registered as a frontend with the Stability Pool and has a specified kickback rate, _it cannot be changed_.&#x20;

However, if a Frontend Operator wishes to change their kickback rate, they must register a _new frontend address_ with a new kickback rate. For user's to take advantage of the new kickback rate, they will have to withdraw their deposit and deposit again with the new frontend tag.&#x20;

### Why doesn’t the Liquity team run a frontend?&#x20;

Not running our own frontend increases censorship resistance and decentralization, but also helps us bootstrap a distributed ecosystem.&#x20;
