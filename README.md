PYTHON BOT

ETH Day Trading Bot with Telegram Alerts
This Python-based bot automatically monitors and trades ETH/USD on the Capital.com platform, using a simple trading strategy. It also sends real-time notifications to your Telegram account when buy or sell orders are executed.

Features
24/7 market monitoring: Trades ETH/USD based on predefined thresholds.
Telegram Alerts: Get instant notifications when a trade is executed.
User-friendly UI: Simple Tkinter-based graphical interface to start and stop the bot.
Table of Contents
Requirements
Setup
Running the Bot
Configuration
Usage
License
Requirements
Dependencies:
Python 3.x
Capital.com API Key
Telegram Bot Token (for sending alerts)
Python Libraries:
requests
tkinter
time
Install these dependencies via pip:

bash
Copy code
pip install requests
Setup
1. Create a Capital.com Account & API Key
To trade using this bot, you need a Capital.com API key:

Go to Capital.com and sign up.
Access your API key from the Capital.com dashboard. This will be used in the bot to place buy/sell orders.
2. Set Up a Telegram Bot
To receive alerts on Telegram:

Open Telegram and search for the @BotFather bot.
Start a conversation with @BotFather and type /start.
Type /newbot and follow the instructions to create a bot.
After creating the bot, you’ll receive a bot token (used in the bot).
Start a chat with your bot by searching for it in Telegram and sending a message (e.g., "Hello").
Retrieve your chat ID:
Open the following URL in your browser (replace <TOKEN> with your bot token):
bash
Copy code
https://api.telegram.org/bot<TOKEN>/getUpdates
Find the chat section in the JSON response, and note your chat_id.
3. Clone the Repository
Clone the repository to your local machine:

bash
Copy code
git clone https://github.com/yourusername/eth-trading-bot.git
cd eth-trading-bot
4. Configure the Bot
Before running the bot, you’ll need to configure the API keys:

Open the eth_trading_bot.py file in your preferred text editor.
Replace the placeholders with your Capital.com API key, Telegram Bot Token, and Telegram Chat ID.
Example:

python
Copy code
# Capital.com API Key
API_KEY = 'your_capital_com_api_key'

# Telegram Bot Token and Chat ID
TELEGRAM_TOKEN = 'your_telegram_bot_token'
CHAT_ID = 'your_chat_id'
Running the Bot
Once everything is configured, you can run the bot:

bash
Copy code
python eth_trading_bot.py
This will launch the user interface (UI) where you can start and stop the trading bot.

How the Bot Works:
Start Trading: Click the "Start Trading" button in the UI to start monitoring the ETH market.
The bot automatically buys if the ETH price drops by 2% below the current price and sells if it rises by 2% above the current price.
Stop Trading: Click the "Stop Trading" button to stop the bot.
You will receive Telegram alerts whenever a trade is executed (e.g., buy or sell orders).

Configuration
You can adjust the thresholds for buying and selling ETH within the start_trading() function:

python
Copy code
# Example thresholds: Buy if ETH drops by 2%, Sell if it rises by 2%
buy_price = current_price * 0.98
sell_price = current_price * 1.02
You can also modify the amount of ETH to buy/sell:

python
Copy code
place_order('BUY', symbol, 0.01)  # Adjust the amount here
Usage
Start Trading: Use the UI to start monitoring the market.
Telegram Notifications: You will receive a notification to your Telegram when a trade is placed.
Adjust Thresholds: Modify the buy/sell thresholds and trade amount in the code as per your strategy.
License
"This project is made by Quang Huynh! Chedit my work if you are going to use it!

Notes:
Make sure to test the bot using a demo account on Capital.com before using it with real funds.
Ensure that your API keys and tokens are kept private and secure.
Feel free to contribute or open issues if you encounter any problems!
