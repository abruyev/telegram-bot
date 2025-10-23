# 🧠 MarketMetrics
MarketMetrics is a Telegram bot that collects and analyzes data from online marketplaces. It allows users to track product categories, prices, and performance metrics — all directly inside Telegram.

--- 

🚀 Features 🤖 Aiogram — powerful Telegram bot framework 
🌐 Selenium — browser automation and data scraping 
💾 JSON — local data storage 
📊 Analytics — category and product metrics 
🧱 Modular architecture — easily extendable and scalable

---

📂 Project Structure MarketMetrics/ 
```
├── bot.py # Entry point — runs the Telegram bot
├── config.py # Loads environment variables
├── handlers/ # Message and command handlers
 ├── start.py
 ├── help.py
 └── market.py
├── keyboards/ # Inline buttons
 │
 └── inline.py
├── scrapers/ # Marketplace scrapers
 │
 ├── uzum_scraper.py
 │
 └── yandex_scraper.py
├── products.json # Stored product data
├── categories.json # Stored category data
├── .env # Environment configuration
├── requirements.txt # Dependencies list
└── README.md
```
---
# ⚙️ Installation & Setup
1️⃣ Install dependencies Make sure Python is above 3.11+ (3.11.0-3.13.0) is installed.
Then create and activate a virtual environment:
```
python -m venv .venv 
```
Windows:
```
.venv\Scripts\activate 
``` 
macOS / Linux:
```
source .venv/bin/activate 
```
## Error Handling
```
.venv\Scripts\activate : File C:\dev\telegram-bot\.venv\Scripts\Activate.ps1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1 + .venv\Scripts\activate + ~~~~~~~~~~~~~~~~~~~~~~ + CategoryInfo : SecurityError: (:) [], PSSecurityException + FullyQualifiedErrorId : UnauthorizedAccess
```
Run this in PowerShell as Administrator. Enter in integrated Terminal:
```
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```
Then activate your virtual environment again:
```
.venv\Scripts\activate
```
.venv\Scripts\activate
✅ This only changes the policy for your current PowerShell session, so it’s safe and temporary.

---
# Install the required packages:
```
pip install aiogram
pip install selenium
pip install asyncio
pip install python-dotenv
``` 
2️⃣ Configure environment variables Create a .env file in the project root if it doesn’t exist:
```
TOKEN=your_telegram_bot_token CHROME_PATH=path_to_chromedriver.exe 
🔹 TOKEN — Telegram bot token from @BotFather
🔹 CHROME_PATH — Full path to your chromedriver.exe (used by Selenium)
``` 
3️⃣ Install ChromeDriver Ensure Google Chrome is installed.
Download ChromeDriver matching your Chrome version. Unzip it and set the correct path in .env.
Example:
```
CHROME_PATH=D:\dev\python\telegram_bots\market-metrics\chromedriver.exe 
``` 
4️⃣ Run the bot Start the bot with:
```
python bot.py
``` 
You should see:
```
INFO:aiogram:Bot polling has started 
``` 
Then open your Telegram bot (e.g., @PriceInsiderBot ) and send /start.
---
# 🌐 Marketplace Scraping MarketMetrics uses Selenium to automatically scrape product data.
You can manually refresh categories or products:
```
python scrapers/uzum_scraper.py python scrapers/yandex_scraper.py 
``` 
Scraped data will be saved to:
```
categories.json — marketplace categories products.json — products and prices 
``` 
# 🧩 Common Errors Error Cause Solution
```
ValueError: The path is not a valid file Invalid ChromeDriver path Check CHROME_PATH in .env 
telegram.error.Unauthorized Invalid bot token Get a new one from @BotFather
SessionNotCreatedException Chrome and ChromeDriver version mismatch Install matching ChromeDriver
``` 
---
# 💡 Useful Commands Command Description
```
/start Start the bot /help Show available commands /market Display marketplace analytics 
``` 
---
# 🧠 Tech Stack Technology Purpose
```
Python 3.11+ -> Core language Aiogram -> Telegram bot framework Selenium -> Web automation and scraping Asyncio -> Asynchronous operations python-dotenv -> Environment configuration JSON -> Local data storage 
```

