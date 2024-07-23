---
description: Collection of technical resources about the Liquity protocol.
---

# Technical Resources

A technical system summary including contract descriptions, function descriptions, and more is available in the [**Liquity developer README**](https://github.com/liquity/dev#readme).&#x20;

## Technical papers

#### [Whitepaper](https://docsend.com/view/mk99y5abnr8yqxws)

[**Scalable Reward Distribution with Compounding Stakes**](https://github.com/liquity/liquity/blob/master/papers/Scalable\_Reward\_Distribution\_with\_Compounding\_Stakes.pdf) (see this [article](https://medium.com/liquity/scaling-liquitys-stability-pool-c4c6572cf275) for a simpler introduction)

#### [Efficient Order-Preserving Redistribution of Troves](https://github.com/liquity/liquity/blob/master/papers/Efficient\_Order-Preserving\_Redistribution\_of\_Troves.pdf)

## Economic modelling and simulation

#### [Liquity Market Risk Assessment by Gauntlet Networks](https://liquity-report.gauntlet.network/)

#### [Macroeconomic Model of Liquity by Prof. Yulin Liu](https://colab.research.google.com/drive/1AyhFfE\_EKCcMO6HeG04Se3hbraTxODWU?usp=sharing) &#x20;

## Security audits

[**Trail of Bits Security Assessment**](https://github.com/trailofbits/publications/blob/master/reviews/Liquity.pdf) January 2021

[**Audit by Coinspect**](https://www.coinspect.com/liquity-audit/) March 2021

[**Trail of Bits Liquity Protocol and Stability Pool Final Report**](https://github.com/trailofbits/publications/blob/master/reviews/LiquityProtocolandStabilityPoolFinalReport.pdf) March 2021

[**Trail of Bits Liquity Proxy Contracts Report**](https://github.com/trailofbits/publications/blob/master/reviews/LiquityProxyContracts.pdf) March 2021

## Matrix of audit applicability

<table><thead><tr><th width="171.00000000000003">Auditor</th><th width="147">Date</th><th></th><th>Commit(s) provided</th></tr></thead><tbody><tr><td><a href="https://github.com/trailofbits/publications/blob/master/reviews/Liquity.pdf">Trail of Bits</a></td><td>January 2021</td><td>All core system contracts except the PriceFeed</td><td><a href="https://github.com/liquity/dev/commit/f0df3ef">f0df3ef</a></td></tr><tr><td><a href="https://www.coinspect.com/liquity-audit/">Coinspect</a></td><td>March 2021</td><td>All core system contracts and peripheral LQTY lockup contracts</td><td><a href="https://github.com/liquity/dev/commit/dd7f59b9">dd7f59b9</a></td></tr><tr><td><a href="https://github.com/trailofbits/publications/blob/master/reviews/LiquityProtocolandStabilityPoolFinalReport.pdf">Trail of Bits</a></td><td>March 2021</td><td>All core system contracts, peripheral LQTY lockup contracts, and peripheral Unipool LP staking contract</td><td><a href="https://github.com/liquity/dev/commit/8cec3fd">8cec3fd</a>, <a href="https://github.com/liquity/dev/commit/dce38b7">dce38b7</a></td></tr><tr><td><a href="https://github.com/trailofbits/publications/blob/master/reviews/LiquityProxyContracts.pdf">Trail of Bits</a></td><td>March 2021</td><td>Peripheral DSProxy and bundled actions contracts</td><td><a href="https://github.com/liquity/dev/commit/b90440d">b90440d</a></td></tr></tbody></table>

## Risk assertions

[**On the Price Stability of LUSD**](https://medium.com/liquity/on-price-stability-of-liquity-64ce8420f753)

[**Addressing Concerns about Liquity**](https://medium.com/liquity/addressing-concerns-about-liquity-2af3e1d0a946)

## Code base

#### [Github Repository](https://github.com/liquity/dev)

## Contract Addresses

| **Mainnet**           | **Address**                                                        |
| --------------------- | ------------------------------------------------------------------ |
| activePool            | 0xDf9Eb223bAFBE5c5271415C75aeCD68C21fE3D7F                         |
| borrowerOperations    | 0x24179CD81c9e782A4096035f7eC97fB8B783e007                         |
| troveManager          | 0xA39739EF8b0231DbFA0DcdA07d7e29faAbCf4bb2                         |
| collSurplusPool       | 0x3D32e8b97Ed5881324241Cf03b2DA5E2EBcE5521                         |
| communityIssuance     | 0xD8c9D9071123a059C6E0A945cF0e0c82b508d816                         |
| defaultPool           | 0x896a3F03176f05CFbb4f006BfCd8723F2B0D741C                         |
| hintHelpers           | 0xE84251b93D9524E0d2e621Ba7dc7cb3579F997C0                         |
| lockupContractFactory | 0x2eBeF24dA09489218Ba2BECb01867F6DaAeDcD4B                         |
| lqtyStaking           | 0x4f9Fbb3f1E99B56e0Fe2892e623Ed36A76Fc605d                         |
| priceFeed             | 0x4c517D4e2C851CA76d7eC94B805269Df0f2201De                         |
| sortedTroves          | 0x8FdD3fbFEb32b28fb73555518f8b361bCeA741A6                         |
| stabilityPool         | 0x66017D22b0f8556afDd19FC67041899Eb65a21bb                         |
| gasPool               | 0x9555b042F969E561855e5F28cB1230819149A8d9                         |
| unipool               | 0xd37a77E71ddF3373a79BE2eBB76B6c4808bDF0d5                         |
| lusdToken             | 0x5f98805A4E8be255a32880FDeC7F6728C6568bA0                         |
| lqtyToken             | 0x6DEA81C8171D0bA574754EF6F8b412F2Ed88c54D                         |
| multiTroveGetter      | 0xFc92d0E9Fa35df17E3A6d9F40716ca2cE749922B                         |
| uniToken              | 0xF20EF17b889b437C151eB5bA15A47bFc62bfF469                         |
| Chanlink LUSD feed    | 0x3D7aE7E594f2f2091Ad8798313450130d0Aba3a0                         |
| **Optimism**          | **Address**                                                        |
| LUSD                  | 0xc40F949F8a4e094D1b49a23ea9241D289B7b2819                         |
| **Arbitrum**          | **Address**                                                        |
| LUSD                  | 0x93b346b6BC2548dA6A1E7d98E9a421B42541425b                         |
| LQTY                  | 0xfb9E5D956D889D91a82737B9bFCDaC1DCE3e1449                         |
| **zkSync ERA**        | **Address**                                                        |
| LUSD                  | 0x503234F203fC7Eb888EEC8513210612a43Cf6115                         |
| **Polygon zkEVM**     | **Address**                                                        |
| LUSD                  | 0x01E9A866c361eAd20Ab4e838287DD464dc67A50e                         |
| LQTY                  | 0xAa26786c9b62Afa8fFe3Db8d08ea40D56Fd3aC25                         |
| **Starknet**          | **Address**                                                        |
| LUSD                  | 0x070a76fd48ca0ef910631754d77dd822147fe98a569b826ec85e3c33fde586ac |
| **Base**              | **Address**                                                        |
| LUSD                  | 0x368181499736d0c0CC614DBB145E2EC1AC86b8c6                         |
| **Mantle**            | **Address**                                                        |
| LUSD                  | 0xf93a85d53e4af0d62bdf3a83ccfc1ecf3eaf9f32                         |
| **Linea**             | **Address**                                                        |
| LUSD                  | 0x63bA74893621d3d12F13CEc1e86517eC3d329837                         |

