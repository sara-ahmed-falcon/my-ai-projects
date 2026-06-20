
# AI Cognitive System: Web-to-Telegram Bridge 🌉🤖## Overview
A robust, real-time bidirectional bridge connecting a modern web interface to an AI-powered Telegram Bot (powered by OpenClaw). This system utilizes Flask and Telethon to route user requests from a browser directly to a Telegram bot, extracts the AI's response (including rich text formatting), and streams it back to the web interface via Server-Sent Events (SSE). 

The ecosystem is also integrated with an external **Monitoring Platform** to track interactions, monitor node health, and log system activity.## System Architecture* **Frontend (Web UI):** A sleek, modern HTML/CSS/JS interface featuring a dynamic animated background, smooth scrolling, and SSE handling for real-time text rendering.* **Backend Bridge (Flask + Python):** Serves as the middleware. It receives HTTP POST requests from the UI and manages asynchronous queues.* **MTProto Integration (Telethon):** Operates in a background thread using `asyncio`. It securely connects to Telegram, sends the user's prompt to the designated AI Bot, and listens for the generated response.* **Message Parser:** A custom extraction module that accurately parses Telegram's raw MTProto nodes (e.g., Bold, Italic, Lists) into clean text.* **AI & Monitoring Node:** The final stage where the Telegram bot processes the query using OpenClaw, supervised by a connected monitoring platform for analytics and stability tracking.## Key Features* **Real-Time Streaming:** Utilizes Flask's `stream_with_context` to provide a "typing" effect on the frontend.* **Rich-Text Extraction:** Deep parsing of Telegram's message objects.* **Threaded Event Loop:** Seamlessly runs Telethon's async event loop alongside Flask's synchronous server.* **Secure & Extensible:** Ready for deployment with isolated environments and external monitoring hooks.## Prerequisites* Python 3.8+* A Telegram API ID and API Hash (from my.telegram.org)* An active Telegram Bot username to interact with.## Installation & Setup1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YourUsername/YourRepositoryName.git](https://github.com/YourUsername/YourRepositoryName.git)
   cd YourRepositoryName
Install dependencies:

Bash

pip install flask flask-cors telethon
Configure the Environment:
Open the python backend file and replace the placeholder credentials with your actual data:

Python

API_ID = 1234567 # Your API ID
API_HASH = 'Your_API_Hash'
PHONE_NUMBER = '+1234567890'
BOT_USERNAME = '@YourAIBotUsername'
(Note: Never commit your actual API credentials to a public repository. Use environment variables in production).
Run the Backend:

Bash

python chatbot.py
On the first run, Telethon will prompt you to enter the login code sent to your Telegram account to create the session file.
Launch the UI:
Open index.html in any modern web browser to start interacting with the AI Cognitive System.
License
Distributed under the MIT License.
