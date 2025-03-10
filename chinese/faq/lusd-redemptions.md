# 赎回和 LUSD 价格稳定

### **LUSD 是怎么锚定美元的？**

稳定币Lusd的上下区间是由两个机制保证的：1）LUSD 刚兑 ETH 的能力（即 1 LUSD 兑换 价值1 美元的 ETH）。2）110% 的最低抵押率保证。他们都由用户主导的套利机制来实现，我们称这些为“硬挂钩机制”。

LUSD 还受益于间接的的美元平价机制——称为“软挂钩机制”。将LUSD美元平价作为谢林点是其中之一，由于 Liquity 将 LUSD 视为等同于美元，因此两者之间的平价是协议的隐含均衡状态。另一机制，则是动态调整铸造稳定币（新增债务）所需要的费用。当LUSD低于1USD的时候，这时候用户可以进行赎回套利，用低于1USD的LUSD（面值为1USD）去兑换价值1USD的ETH，这时候赎回量会增加。与此同时，铸造稳定币（新增债务）的基本费率也会增加，这会降低借贷的吸引力，从而阻止新的 LUSD 进入市场，避免LUSD继续贬值。

关于LUSD 价格稳定机制，[此处](https://medium.com/liquity/on-price-stability-of-liquity-64ce8420f753)可以了解更多信息。

### **什么是赎回？**

赎回是将 LUSD 以面值兑换 ETH 的过程，就好像 1 LUSD 正好值 1 美元。也就是说，如果您支付x LUSD，您将获得价值 x 美元的 ETH 作为回报。

用户可以随时自由地将 LUSD 兑换为 ETH。但是，Liquity可能会对赎回的金额收取赎回费。

例如，如果当前赎回费为 1%，ETH 的价格为 500 美元，您赎回 100 LUSD，则您将获得 0.198 ETH（0.2 ETH 减去 0.002 ETH 的赎回费）。

请注意，Liquity在计算基本费率时也会考虑当前操作的赎回金额。在金额较大的情况下，赎回金额本身也可能会对赎回费用产生影响。

### **赎回与偿还债务相同吗？**

不，赎回是一种完全独立的机制。偿还债务所需要做的就是调整他们的 Trove 的债务和抵押品。

### **赎回费是如何计算的？**

正常操作下，赎回费用由公式 基本费率 \* 赎回的ETH 给出。

### **基准利率是如何计算的？**

赎回费用基于 Liquity 中基本费率这一状态变量。该变量是动态更新的，随着每次赎回而增加，并随着距上次费用事件（即最后一次赎回或 LUSD 发行）的时间增加而衰减。

每次兑换时：

基本费率根据自上次费用事件以来经过的时间衰减。

基本费率增加的幅度与赎回的LUSD占总供应量的比例成正比。

赎回费用由 基本费率 \* 取出的ETH 给出。

### **作为借款人，如果我被赎回，我会赔钱吗？**

如果您的 Trove 被赎回，您不会遭受净损失。但是，您将失去部分ETH的头寸。赎回后，您的 Trove 的抵押率也会提高。

### **我怎样才能避免被赎回？**

避免被赎回的最佳方法是保持相对于系统中其余金库而言较高的抵押率。请记住：当赎回发生时，风险最高的金库（即最低抵押的金库）排在第一位。\
