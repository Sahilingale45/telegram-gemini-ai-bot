# telegram-gemini-ai-bot
A real-time Make.com automation blueprint that watches Telegram bot updates, processes incoming messages using the Gemini 2.5 Flash API via HTTP, and replies instantly.
# Real-Time Telegram AI Bot (via Gemini 2.5 Flash)

This repository contains a Make.com (formerly Integromat) scenario blueprint that turns a standard Telegram bot into an AI-powered conversational assistant using the Gemini API.

## 🚀 How It Works
1. **Trigger (Telegram Bot - Watch Updates):** Instantly catches any new incoming chat messages or user requests sent directly to the bot using a webhooks framework.
2. **AI Processing (HTTP - POST):** Sends a raw POST request containing the user's text message to the `gemini-2.5-flash` API endpoint for natural language processing and text generation.
3. **Response Delivery (Telegram Bot - Send a Text Message or a Reply):** Takes the structured text response from the LLM and streams it straight back to the user's open chat window.

## 📦 What's Included
* `/blueprints/telegram-gemini-ai-bot.json`: The complete exported Make.com scenario blueprint configuration file.

## 🔧 Setup Instructions
1. Open your **Make.com** dashboard.
2. Create a new scenario, click the three dots (`...`) located on the bottom navigation control bar, and choose **Import Blueprint**.
3. Upload the `.json` blueprint file from this repository.
4. Establish your account and API credentials:
   * **Telegram Modules (1 & 8):** Generate an API Token by messaging Telegram's official `@BotFather`. Open the **Watch Updates** module configuration and create a new connection using your token to initialize the webhook. Ensure module 8 uses this same exact connection.
   * **HTTP Module (6):** Set up your API headers and add your Gemini API Key as a query parameter or authentication header (`X-Goog-Api-Key`).
5. Map the fields correctly: Ensure the final Telegram module maps its `Chat ID` from the initial trigger, and its text content from the parsed JSON response of the HTTP module.
6. Save the configuration and flip the main scheduling toggle switch to **ON**.
