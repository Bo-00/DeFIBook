---
icon: '0'
---

# UniSwap V3

## Product

Uniswap v3 is the third iteration of the Uniswap protocol, offering significant improvements over its predecessor, v2. Here are its main selling points:

* **Concentrated Liquidity:** Unlike v2, liquidity providers can now allocate their capital within specific price ranges, enhancing capital efficiency and enabling better fund use.
* **Flexible Fee Structures:** v3 introduces multiple fee tiers, allowing liquidity providers to choose their compensation level depending on the risk associated with various pools.
* **Improved Price Oracles:** Enhanced and more reliable on-chain price oracles incentivize accurate price reporting, benefiting developers and traders alike.
* **Non-fungible Liquidity:** Unlike the fungible LP tokens in v2, each liquidity position in v3 is represented by a unique NFT, accommodating customized strategies.

These innovations address some limitations of v2 by optimizing capital efficiency, offering greater customizability for liquidity providers, and leading to more competitive trading experiences.

### Mathematical Formulation of Uniswap v3 Mechanics

Uniswap v3 introduces a highly efficient mathematical model to facilitate its innovative features. At its core, the Automated Market Maker (AMM) model is now enhanced to handle concentrated liquidity and custom price ranges (CLAMM). Here's a brief overview of the key mathematical components:

#### Constant Product Formula

Uniswap v3 still relies on the fundamental constant product formula found in previous versions:

$$
[ x \cdot y = k ]
$$

where:

* ( x ) and ( y ) are the quantities of the two tokens in the liquidity pool.
* ( k ) is a constant that remains unchanged during swaps.

#### Price Ranges and Liquidity

Liquidity providers can specify a price range for their liquidity provision, allowing them to focus capital within specific bounds. This is represented mathematically by:

$$
[ L = \sqrt{xy} \left( \frac{price_{\text{max}} - price_{\text{min}}}{price - price_{\text{min}}} \right) ]
$$

where:

* ( L ) is the liquidity.
* ( \text{price}_{\text{max\}} ) and ( \text{price}_{\text{min\}} ) define the chosen range.

#### Fee Structures

The flexible fee tiers are calculable with distinct rates, represented as percentage adjustments to transactions within pools:

$$
[
\text{Fee} = \text{Swap Amount} \times \text{Fee Rate}
]
$$



The introduction of these mathematical models allows for tailored liquidity strategies and a more efficient trading environment, enhancing the role of mathematical precision in modern decentralized finance systems.

### Impermanent Loss

#### 虚拟储备计算

资产 Y 的储备量：$$y = y_{\text{virtual}} - L\sqrt{p_a} = L(\sqrt{P} - \sqrt{p_a})$$

资产 X 的储备量：$$x = x_{\text{virtual}} - \frac{L}{\sqrt{p_b}} = L(\frac{1}{\sqrt{P}} - \frac{1}{\sqrt{p_b}})$$

#### 价值计算

初始持有资产的价值：

$$V_0 = y \cdot 1 + x \cdot P$$$$= L(\sqrt{P} - \sqrt{p_a}) + L(\frac{1}{\sqrt{P}} - \frac{1}{\sqrt{p_b}}) \cdot P$$$$= 2L\sqrt{P} - L(\sqrt{p_a} + \frac{P}{\sqrt{p_b}})$$

如保持在外的头寸价值：

$$V_{\text{held}} = y + xP'$$$$= L(\sqrt{P} - \sqrt{p_a}) + L(\frac{1}{\sqrt{P}} - \frac{1}{\sqrt{p_b}}) \cdot P'$$$$= L\sqrt{P}(1 + k) - L(\sqrt{p_a} + \frac{Pk}{\sqrt{p_b}})$$

#### 无常损失计算

$$\text{IL}_{a,b}(k) = \frac{V_1 - V_{\text{held}}}{V_{\text{held}}}$$

$$= \frac{2L\sqrt{Pk} - L\sqrt{P}(1 + k)}{L\sqrt{P}(1 + k) - L(\sqrt{p_a} + \frac{Pk}{\sqrt{p_b}})}$$

$$= \frac{2\sqrt{k} - 1 - k}{1 + k - \sqrt{\frac{p_a}{P}} - k\sqrt{\frac{P}{p_b}}}$$

$$= \text{IL}(k) \cdot \left(\frac{1}{1 - \frac{\sqrt{\frac{p_a}{P}} + k\sqrt{\frac{P}{p_b}}}{1+k}}\right)$$



## Technical Architect And Details

### Backend



### Smart Contracts





## Best Practice

从0到1开发一个uniswap V3

[https://uniswapv3book.com/index.html](https://uniswapv3book.com/index.html)



