⚠️ ALPHA ⚠️

# Trading Bot for prediction markets.

Use the existing arbitrage strategy or create your own. Currently supports Drift and PolyMarket. If you would like to add another connector, please open an issue or message me on X at https://x.com/ashish24rawat.

Currently working on 

## DISCLAIMER

The bot in BETA and will most probably contain bugs. Use at your own discrection. YOU MAY LOSE FUNDS. 

## Prerequisites

- Node.js (v14 or later)
- npm or yarn
- Ethereum wallet with some MATIC for gas fees
- Solana wallet with some SOL for gas fees
- USDC balance on both Polygon and Solana networks

## Repository Structure

- `src/connectors/`: Contains BaseConnector, PolymarketConnector and DriftConnector
- `src/strategies/`: Includes BaseStrategy, ArbStrategy for arbitrage logic
- `config/`: Contains prod.ts which you can modify
- `src/utils/`: Utilities like ConfigService and Logger
- `src/index.ts`: Main execution file

## Setting Up the Environment

1. Copy the .env.example and create a new .env file at the root of the project

2. Fill in the required environment variables in the .env file. Your environment variables never leave your device. Double check the source code to ensure this is the case! (Don't trust, verify)

3. Ensure you have sufficient USDC balance on both Polygon and Solana networks.    

4. Adjusting the strategy:
- Open `config/prod.ts`
- Modify the `params` object in the strategy configuration:
  - `market_id`: Set the market ID for the market you want to trade. It is the slug of the market you want to trade. You can get the slug from the URL of Polymarket/Drift 

  - `polymarket market_id example`
  In the case of PolyMarket, https://polymarket.com/event/will-biden-announce-resignation-by-august-31?tid=1725034578450

  Slug would be will-biden-announce-resignation-by-august-31

  - `drift market_id example`
    In the case of Drift, let's say the URL is https://app.drift.trade/bet/TRUMP-WIN-2024-BET , 
    the slug would be TRUMP-WIN-2024-BET

  - `balance_perc`: Adjust the percentage of your balance to use for trades
  
  - `min_spread`: Set the minimum price difference required for the bot to execute a trade
- Save the file and restart the bot for changes to take effect


5. Install dependencies:
   - run npm install to install the required dependencies

6. Run the bot
   - npx ts-node src/index.ts

7. Monitor the bot's activity:
   - Watch the console output for real-time information on market conditions, arbitrage opportunities, and executed trades.
   - The bot will log important events, including initialization status, balance updates, and trade executions.

## Disclaimer

Use at your own risk. Always be aware of the financial and legal implications of automated trading.

Remember to always monitor your bot's performance and adjust settings as needed to optimize your trading strategy.


This repository is under active development and will most probably contain bugs. USE AT YOUR OWN RISK.


- [✅] Drift & Polymarket connectors 
- [] arb strat (in progress)
- [] test script
- [] cross exchange MM