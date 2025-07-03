# -telegram-ai-script-generator
This workflow listens for messages on Telegram, extracts the message text as a topic, fetches related news data from NewsData.io, generates a 60-second video script about that topic using the OpenRouter AI API (Mistral-7B-Instruct model), and then sends the generated script back to a specified Telegram chat.

## ✨ Features
-   **Telegram Integration**: Triggers upon receiving a message in a connected Telegram bot.
-   **Dynamic Topic Selection**: Uses the received Telegram message text as the topic for script generation.
-   **News Data Fetching**: Retrieves relevant news articles based on the topic using NewsData.io.
-   **AI-Powered Script Generation**: Leverages OpenRouter's Mistral-7B-Instruct model to create concise video scripts.
-   **Telegram Notification**: Sends the generated video script back to a specific Telegram chat.

---

## 🚀 How to Get Started

### 🛠️ Installation
1.  **Import the Workflow**: Download the provided JSON and import it into your n8n instance.
2.  **Telegram Bot Setup**:
    * Create a new bot with BotFather on Telegram and obtain your **Bot Token**.
    * In the `Telegram Trigger` node and `SEND SCRIPT TO TELEGRAM` node, set up your **Telegram API credential** using the Bot Token.
    * For the `SEND SCRIPT TO TELEGRAM` node, replace `7490692228` with your target `chatId`. You can get your chat ID by sending a message to your bot and then visiting `https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates` in your browser.
3.  **NewsData.io API Key**:
    * Sign up or log in to [NewsData.io](https://newsdata.io/).
    * Generate an API key.
    * In the `EXTRACT DATA FROM INTERNET` node, update the `url` parameter with your NewsData.io API key: `https://newsdata.io/api/1/news?apikey=YOUR_NEWSDATA_IO_API_KEY&language=en&country=in`.
4.  **OpenRouter AI API Key**:
    * Sign up or log in to [OpenRouter](https://openrouter.ai/).
    * Navigate to your **API Keys** section.
    * Generate a new API key and copy it.
    * In the `MAKE SCRIPT` node, update the `Authorization` header with your **OpenRouter API Key** in the format `Bearer YOUR_API_KEY`.

### ⚙️ Configuration
1.  **Telegram Chat ID**: Ensure the `chatId` in the `SEND SCRIPT TO TELEGRAM` node is set to the correct ID where you want the scripts to be sent.
2.  **News Search Language/Country**: In the `EXTRACT DATA FROM INTERNET` node, you can modify `language=en` and `country=in` in the URL to fetch news in a different language or from a different country.

---

## 🏃‍♀️ Usage
1.  After importing and configuring, activate the workflow in n8n.
2.  Send a message to your configured Telegram bot with the topic you want a video script about (e.g., "latest tech innovations").
3.  The workflow will process the request, fetch news, generate a script, and send it back to your specified Telegram chat.

---\

