# 稳定池和清算

### **什么是稳定池？**

稳定池是维持系统偿付能力的第一道防线。通过提供流动性，稳定池用来偿还被清算的金库的债务，从而确保LUSD的总供应始终获得支持。

当一个[金库](https://docs.liquity.org/v/cn/faq/borrowing#what-is-a-trove)被清算时，对应于金库剩余债务的 LUSD 从稳定池的余额中被烧毁以偿还金库的债务。作为交换，来自金库的全部抵押品都被转移到稳定池中。

&#x20;稳定池中的资金通过用户将 LUSD 存入其中（称为稳定提供者）获得。随着时间的推移，稳定提供者会按比例失去其 LUSD 存款的份额，同时按比例获得清算抵押品的份额。由于 Troves 可能会以略低于 110% 的抵押品比率被清算，稳定提供者将预计获得相对于他们偿还的债务更高的美元价值的抵押品。

### **为什么要把LUSD存入稳定池**

稳定性提供者将获得清算收益（见[下文](https://docs.liquity.org/faq/stability-pool-and-liquidations#how-do-i-benefit-as-a-depositor-from-liquidations)）并以 LQTY 代币的形式获得早期采用者奖励。

### **什么是清算？**

为确保抵押品能够完全支持所有稳定币的供应，低于 110% 最低抵押品比率的[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)将被关闭（清算）。

金库的债务被取消，由稳定池吸收。其抵押品则在稳定提供者之间分配。

金库的所有者仍然保留借入的 LUSD 的全部金额，但总体上将损失约 10% 的价值。因此，始终将抵押率保持在 110% 以上是至关重要的，理想情况下高于 150%。

### **谁可以清算金库？**

一旦金库的抵押率低于 110% 的最低抵押率，任何人都可以清算它。发起人将获得交易费补偿（200 LUSD + Trove 抵押品的 0.5%）作为这项服务的奖励。

### **如何获得清算金库的补偿？**

金库的清算与发起人必须支付的某些交易费用有关。用户可以通过实施最多 95 个 金库的批量清算来降低清算每个金库的成本，但为了确保即使在交易费用飙升时清算仍然有利可图，协议提供了由以下公式给出的交易费补偿：

交易费补偿 = 200 LUSD + Trove 抵押品 (ETH) 的 0.5%200 LUSD 由[清算准备金](https://docs.liquity.org/faq/borrowing#what-is-the-liquidation-reserve)提供资金，而 0.5% 的可变部分（以 ETH 计）来自清算抵押品。这略微降低了稳定性提供商的清算收益。

### **作为稳定提供者，我如何从清算中受益？**

由于清算在金库抵押率小于110%时发生，每当[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)被清算时，您很可能会获得净收益。

假设稳定池中共有 1,000,000 LUSD，而您的存款为 100,000 LUSD。

现在，有一个金库，债务为 200,000 LUSD ，抵押品为 400 ETH ，正以 545 美元的以太币价格被清算。此时抵押率为 109% (= 100% \* (400 \* 545) / 200,000)。由于您的稳定池份额为 10%，您的存款将减少已清算债务 (20,000 LUSD) 的 10%，即从 100,000 到 80,000 LUSD。作为回报，您将获得清算抵押品的 10%，即 40 ETH，目前价值 21,800 美元。所以，您从清算中获得的净收益为 1,800 美元。

请注意，如果用户预计 ETH 的美元价值会下降，他们可以立即提取从清算中收到的抵押品，并将其出售以减少他们的ETH头寸（例外情况参见[我可以随时提取我的存款吗？](https://docs.liquity.org/faq/stability-pool-and-liquidations#can-i-withdraw-my-deposit-whenever-i-want)）。

### **作为稳定提供者，我如何从早期采用者奖励中受益？**

首先，您需要开设一个金库，借入 LUSD，并将其存入稳定池。存款后，您将开始连续累积与存款规模成比例的奖励（以 LQTY 为单位）。奖励是根据奖励时间表和您用于存款的前端的[回扣率](https://docs.liquity.org/faq/frontend-operators#what-is-the-kickback-rate)计算的。对于系统的早期采用者，奖励将是最高的。

您可以随时将待处理的奖励提取到您的以太坊地址。\


### **我可以随时提取存款吗？**

一般来说，您可以随时提取存入稳定池的存款。没有最短锁定时间。但是，如果有抵押率低于 110% 的待清算[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)尚未清算，提款就会暂停。

### **您使用什么预言机来确定 ETH 的价格？**

该协议使用[ Chainlink 的 ETH:USD](https://feeds.chain.link/eth-usd) 价格馈送，但是在以下（极端）条件下回溯到

[Tellor](https://www.tellor.io/) ETH:USD 预言机：

●      Chainlink 价格已超过 4 小时未更新

●      Chainlink 响应调用恢复，回应了无效的价格或无效的时间戳●      两次连续的 Chainlink 价格更新之间的价格变化 > 50%。

### **将资金存入稳定池会赔钱吗？**

虽然大多数时候清算将在远高于 100% 的抵押品比率下发生，但理论上有可能在ETH价格闪电崩盘或由于预言机故障导致[金库](https://docs.liquity.org/faq/borrowing#what-is-a-trove)被清算时抵押率低于100%。在这种情况下，您可能会遭受损失，因为此时抵押品的收益将小于您减少的存款。

如果 LUSD 的交易价格高于 1 美元，即使抵押率高于 100%，清算对稳定提供者来说也可能无利可图。然而，这种损失是假设性的，因为 LUSD 预计将回归锚定价值，因此“损失”只有在您提取存款并以高于 1 美元的价格出售 LUSD 时才会发生。

请注意，尽管系统经过认真审核，但我们仍然无法完全排除可能导致用户损失的黑客攻击或系统错误。

### **如果在清算发生时稳定池是空的，会发生什么？**

如果稳定池为空，系统将使用称为重新分配的二级清算机制。在这种情况下，系统会将已清算的金库中的债务和抵押品重新分配到所有其他现有金库。债务和抵押品的再分配与接收者金库中的抵押品价值成比例。

以下是我们[白皮书](https://docsend.com/view/bwiczmy)中的一个示例：

![](https://lh4.googleusercontent.com/ZxlL3ajOdkvQcd0nIiMVTiMtt0QhBEkCmN08LqMLnYx20sbs6p0Bqci0DJkh4DsM3olIQi2bzj6HuhvJqcQzsKM8t6vhz-W0bY9p4ug95gddJdM4Q0-VXoG5x\_dRJ9mJIw-mUYIa)
