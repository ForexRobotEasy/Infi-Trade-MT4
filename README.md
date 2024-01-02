# Infi Trade MT4

This code is an Expert Advisor (EA) for MetaTrader 4 (MT4) developed by the Forex Robot Easy Team. For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/infi-trade-mt4-review-unleashing-forex-trading-efficiency/).

## Product Description

Infi Trade MT4 is an EA designed to automate trading on the MT4 platform. It uses a grid trading strategy to open and close positions based on predefined parameters. The EA is capable of opening both buy and sell positions, and it can automatically close positions when a certain number of positions is reached.

The key features of Infi Trade MT4 include:
- **Lot Size:** The initial lot size for trading can be set using the `LotSize` input parameter.
- **Grid Spacing:** The distance between grid levels in pips can be adjusted using the `GridSpacing` input parameter.
- **Maximum Positions:** The maximum number of positions that can be open at any given time can be set using the `MaxPositions` input parameter.
- **Stop Loss:** The stop loss level in pips can be defined using the `StopLoss` input parameter.
- **Take Profit:** The take profit level in pips can be specified using the `TakeProfit` input parameter.

The EA will automatically calculate the grid levels based on the current market price and open positions accordingly. If the number of open positions reaches the maximum allowed, the EA will close all positions before opening new ones.

Please note that Forex Robot Easy is not the official developer of this product. We only provide a code sample that can potentially work as described in the product. For the official developer and more information about this product, please refer to MQL5.

## How It Works

The EA works based on the `OnTick()` function, which is called on every tick of the price. Here's a step-by-step overview of how it works:

1. The EA checks the total number of open positions (`totalPositions`) to determine if the maximum allowed positions have been reached. If so, it calls the `CloseAllPositions()` function to close all open positions.
2. The EA calculates the grid level by adding the grid spacing (`GridSpacing`) to the current ask price. The calculated grid level is then stored in the `gridLevel` variable.
3. The EA checks if the calculated grid level is below the current ask price. If it is, it calls the `OpenPosition()` function with the grid level and the order type set to buy (`ORDER_TYPE_BUY`).
4. The EA checks if the calculated grid level is above the current ask price. If it is, it calls the `OpenPosition()` function with the grid level and the order type set to sell (`ORDER_TYPE_SELL`).
5. The `OpenPosition()` function sends an order to open a new position with the specified price, lot size (`LotSize`), stop loss (`StopLoss`), and take profit (`TakeProfit`). If the order is successfully executed, the position is opened, and the `totalPositions` variable is incremented. If the order fails, an error message is printed.
6. The `CloseAllPositions()` function iterates through all open orders and closes the ones that match the symbol and magic number of the EA. The `totalPositions` variable is decremented for each closed position.
7. The `OnInit()` function is called during EA initialization. It sets the magic number (`MagicNumber`) to identify the positions opened by the EA. It also enables dynamic lot size calculation and sets an automatic trailing stop for the initial order.
8. The `OnDeinit()` function is called when the EA is removed from the chart. It closes all open positions before deinitialization.

Please note that this is a simplified explanation of how the EA works. It's recommended to thoroughly review the code and test it in a demo account before using it in a live trading environment.

For more information, please refer to the official developer of this product using MQL5.
