---
icon: '0'
---

# Morpho

## Product

Morpho认为Aave和compound模式（pool to pool）的出现是早期crypto流动性匮乏的结果，当前市场状态下有更多的碎片流动性，更高的资金效率需要点对点式池的结构性改变和协议创新

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Mathematical Formulation

## Loan Interest Formula

$$Interest = TotalBorrowAssets \times BorrowRate.TaylorCompounded(TimeElapsed)$$

Where:

* BorrowRate is obtained from the Interest Rate Model (IRM)
* TaylorCompounded applies compound interest using Taylor series approximation
* TimeElapsed is the time since last interest accrual



## Deposit Interest Calculation Logic

$$Interest = TotalBorrowAssets \times BorrowRate.TaylorCompounded(TimeElapsed)$$

$$FeeAmount = Interest \times FeeRate$$$$FeeShares = FeeAmount.toSharesDown(TotalSupplyAssets - FeeAmount, TotalSupplyShares)$$

Depositors receive interest implicitly through share value appreciation:$$ShareValue_{new} = \frac{TotalSupplyAssets_{new}}{TotalSupplyShares_{new}} > ShareValue_{old}$$



## Maximum Borrowing Capacity Formula

$$MaxBorrow = Collateral \times \frac{CollateralPrice}{ORACLE\_PRICE\_SCALE} \times LLTV$$

A position is considered healthy when:$$MaxBorrow \geq Borrowed$$



## Liquidation Formulas$$LiquidationIncentiveFactor = \min(MAX\_LIQUIDATION\_INCENTIVE\_FACTOR, \frac{1}{1 - LIQUIDATION\_CURSOR \times (1 - LLTV)})$$

### Liquidation Calculations

When specifying seized collateral amount:$$SeizedAssetsQuoted = SeizedAssets \times \frac{CollateralPrice}{ORACLE\_PRICE\_SCALE}$$$$RepaidShares = \frac{SeizedAssetsQuoted}{LiquidationIncentiveFactor}$$

When specifying repaid debt shares:$$SeizedAssets = RepaidAssets \times LiquidationIncentiveFactor \times \frac{ORACLE\_PRICE\_SCALE}{CollateralPrice}$$

Where RepaidAssets is converted from RepaidShares using:$$RepaidAssets = RepaidShares.toAssets(TotalBorrowAssets, TotalBorrowShares)$$





## Technical Architect And Details

### Back End



### Smart Contracts







## Interesting Questions

为什么morpho选择collateral设计为不能被取出且没有凭证token？



## Best Practice

Build a Morpho Vault



Build a Morpho Fix Rate IRM



Run the Morpho liquidation Bot



