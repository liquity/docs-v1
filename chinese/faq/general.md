# 概述

### **Liquity是什么？**

Liquity是一种去中心化的借贷协议，允许您用以太币作[抵押](https://docs.liquity.org/faq/borrowing#what-do-you-mean-by-collateral)提取[无息贷款](https://docs.liquity.org/faq/borrowing)。 贷款以LUSD（一种与美元挂钩的稳定币）的形式支付，并要求110%的[最低抵押率](https://docs.liquity.org/faq/borrowing#what-is-the-minimum-collateral-ratio-mcr-and-the-recommended-collateral-ratio)。

除了用户的抵押外，Liquity的贷款还由一个LUSD的[稳定池](https://docs.liquity.org/faq/stability-pool-and-liquidations#what-is-the-stability-pool)和所有借款人集体作为最后担保人提供担保。 您可以在我们关于[清算](https://docs.liquity.org/faq/stability-pool-and-liquidations#what-are-liquidations)的说明文件中了解有关这些机制的更多信息。

作为一个协议，Liquity是非保管性的，不可改变的且无治理的。

### **Liquity背后的动机是什么？**

具有稳定价值的资产是以太坊应用的重要组成部分，并且已经发展成为一个价值数百亿美元的资产类别。

然而，绝大部分的这类资产是以法币作抵押的稳定币形式出现的，如Tether和USDC。 DAI和sUSD等去中心化稳定币仅占稳定币总供应量的一小部分，这意味着绝大多数稳定币都是中心化的。

通过创建一种更具资本效率，更容易使用的借入稳定币的方式，Liquity解决了这个问题。 此外，Liquity是无治理的，可确保协议保持去中心化。

### **Liquity的强项是什么？**

Liquity的主要优势包括：

●  [利率为0％](https://docs.liquity.org/faq/borrowing#how-can-you-offer-borrowing-at-a-0-interest-rate)——作为借款人，您无需担心不断产生新的债务。

●  110％的[最低抵押率](https://docs.liquity.org/faq/borrowing#what-is-the-minimum-collateral-ratio-mcr-and-the-recommended-collateral-ratio)——更有效地利用储蓄的ETH。

●  无治理——所有操作都是算法化的和自动化的，并且在协议部署时就已经设置好了协议参数。

●  [可直接赎回](https://docs.liquity.org/faq/lusd-redemptions#what-are-redemptions)——LUSD可以随时按面值赎回相关抵押品。

●  完全去中心化——Liquity协议没有管理密钥，并且可以通过由不同前端运营商提供的多个接口进行访问，从而使其不受审查。

### **Liquity是否可以升级或更改？**

不可以。Liquity没有管理员密钥。没有人可以以任何方式更改系统规则。 智能合约的代码是完全不变的。

### **如何使用Liquity？**

首先，您需要选择一个Web界面（又名[前端](https://docs.liquity.org/faq/frontend-operators)）来访问系统。 构建该协议的核心团队将不会运行前端。 但是您可以通过第三方前端应用程序和集成服务来访问Liquity。您可以在[此处](https://www.liquity.org/frontend)找到前端列表**。**

### Liquity的主要应用案例有哪些？

1. 通过打开[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)，用ETH作抵押借入LUSD
2. 通过向[稳定池](https://docs.liquity.org/faq/borrowing#what-is-a-trove)提供LUSD来换取奖励，以确保Liquity的安全性
3. 质押LQTY以赚取其他用户借入或赎回LUSD所支付的费用收入
4. 当LUSD价格低于1美元时，用1 LUSD兑换价值1 USD的ETH

### LUSD和LQTY是什么？

LUSD是与美元挂钩的稳定币，可以用于偿还Liquity协议里的贷款。您在任何时候都可以按面值赎回[抵押品](https://docs.liquity.org/faq/borrowing#what-do-you-mean-by-collateral)。在[此处](https://docs.liquity.org/faq/lusd-redemptions)了解有关稳定机制的更多信息。

LQTY是Liquity发行的辅助令牌。它捕获了系统产生的费用收入，并激励早期用户和前端开发商。 LQTY的总供应量上限为100,000,000个代币。有关如何随时间分配和释放令牌的更多信息，请参阅[LQTY奖励和分配](https://docs.liquity.org/faq/lqty-distribution-and-rewards)。

### 使用Liquity有什么条件？

要借入LUSD，您所需要的只是一个钱包（如MetaMask）和足够的以太币以开设[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)并支付交易费。

要想稳定池中存款或者质押LQTY，您需要拥有LUSD和/或LQTY代币。您可以通过开设金库借入LUSD，而LQTY可以通过在稳定池中存款来赚取。您还可以使用Uniswap或其他（去中心化）交易所在公开市场上购买代币。

### Liquity是否收取任何费用？

每当借入LUSD以及赎回LUSD时，都必须支付一笔一次性的费用：

* 对于借款人，贷款的借款费占实际借款的一定比例（以LUSD为单位）。
* 对于赎回者，将LUSD兑换为ETH时，系统会将赎回费（以ETH为单位）分给用户。请注意，赎回与偿还您作为借款人的贷款是分开的，后者是免费的。

两种费用都取决于赎回的数量。它们随每次赎回而增加，但如果没有新的赎回发生就随时间推移而递减。这样做的目的是用较高的费用限制大量的赎回，并在大量赎回后直接限制借入。随着时间的流逝，费用的减少使得在赎回量很低的时候对借款人和赎回者的收费“降温”。费用不得低于0.5％（在[恢复模式](https://docs.liquity.org/faq/recovery-mode#what-are-the-fees-during-recovery-mode)下除外），这可以保护赎回工具免于被套利交易者抢先使用。借款费用的上限为5％，即使在大量赎回导致货币收缩时，该系统（某种程度上）也对借款人保持吸引力。此外，这两个费用是相同的，并在以下例图中被描述为“费用”：

![](<../.gitbook/assets/Screenshot 2021-03-27 at 18.36.44.png>)

### 如何使用Liquity赚钱？

使用Liquity有两种不同的创收方式：

* 将LUSD存入稳定池，并获得清算收益（以ETH为单位）和LQTY奖励。 &#x20;
* 抵押LQTY，并从借入和赎回费中赚取LUSD和ETH收入。

### 我会亏本吗？

作为非保管性的系统，发送给协议的所有令牌都将通过算法进行保存和管理，不会受到任何人或机构的干扰。这意味着您的资金将仅受智能合约代码中规定的规则约束。Liquity的代码由Trail of Bits进行过两次审核，由Coinspect进行过一次审核（点击[此处](https://docs.liquity.org/documentation/resources)查看其报告）。

在以下两种情况下，您可能会损失一部分资金：

* 您是借款人（金库所有者），您的以太坊抵押品已被清算。您将保留您借入的 LUSD，但您的金库已经被关闭，而您的抵押品将用于补偿稳定池的存款者**。**
* 您是稳定池的存款人，您所存的LUSD用于偿还被清算的借款人的债务。通常只要借款人的抵押率跌到110％以下就会触发清算，所以您很有可能获得更多以太坊的回报。但是，如果以太坊价格持续下跌并且您维持仓位，您可能会损失一部分稳定池存款的价值。

请注意，尽管我们对系统进行了非常认真的审核，但我们无法完全排除黑客或系统漏洞导致的用户损失（请参阅[免责声明](https://liquity.org/disclaimer)）。
