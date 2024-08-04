# ChatGPT Telegram Bot: **GPT-4o with no daily limits, custom agents y save convo en DB. Special chat modes**

<div align="center">
<img src="https://raw.githubusercontent.com/karfly/chatgpt_telegram_bot/main/static/header.png" align="center" style="width: 100%" />
</div>

## Setup
1. Get your [OpenAI API](https://openai.com/api/) key
2. Get your Telegram bot token from [@BotFather](https://t.me/BotFather)
3. Edit `[config/config.example.yml](https://github.com/janos1111/pyton.chatgpt_telegram_bot/blob/main/config/config.example.yml)` to set your tokens and run 2 commands below (*if you're advanced user, you can also edit* `config/config.example.env`):
telegram_token: ""
openai_api_key: ""
openai_api_base: null  # leave null to use default api base or you can put your own base url here
allowed_telegram_usernames: [] 

>Models - https://github.com/janos1111/pyton.chatgpt_telegram_bot/blob/main/config/models.yml:
Available_text_models: ["gpt-3.5-turbo", "gpt-3.5-turbo-16k", "gpt-4-1106-preview", "gpt-4-vision-preview", "gpt-4", "text-davinci-003", "gpt-4o"]


>Easily create your own chat modes by editing `config/chat_modes.yml`: 
https://github.com/janos1111/pyton.chatgpt_telegram_bot/blob/main/config/chat_modes.yml

>MongoDB (para sync conv);
https://github.com/janos1111/pyton.chatgpt_telegram_bot/blob/main/config/config.example.env

```bash
    mv config/config.example.yml config/config.yml
    mv config/config.example.env config/config.env
```
   4.  And now **run**:
```bash
    docker-compose --env-file config/config.env up --build
```


<br>

<p align="center">
<a href="https://t.me/chatgpt_karfly_bot?start=source=github" alt="Run Telegram Bot shield"><img src="https://img.shields.io/badge/RUN-Telegram%20Bot-blue?logo=data:image/svg+xml;base64,PHN2ZyBpZD0iTGl2ZWxsb18xIiBkYXRhLW5hbWU9IkxpdmVsbG8gMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgdmlld0JveD0iMCAwIDI0MCAyNDAiPjxkZWZzPjxsaW5lYXJHcmFkaWVudCBpZD0ibGluZWFyLWdyYWRpZW50IiB4MT0iMTIwIiB5MT0iMjQwIiB4Mj0iMTIwIiBncmFkaWVudFVuaXRzPSJ1c2VyU3BhY2VPblVzZSI+PHN0b3Agb2Zmc2V0PSIwIiBzdG9wLWNvbG9yPSIjMWQ5M2QyIi8+PHN0b3Agb2Zmc2V0PSIxIiBzdG9wLWNvbG9yPSIjMzhiMGUzIi8+PC9saW5lYXJHcmFkaWVudD48L2RlZnM+PHRpdGxlPlRlbGVncmFtX2xvZ288L3RpdGxlPjxjaXJjbGUgY3g9IjEyMCIgY3k9IjEyMCIgcj0iMTIwIiBmaWxsPSJ1cmwoI2xpbmVhci1ncmFkaWVudCkiLz48cGF0aCBkPSJNODEuMjI5LDEyOC43NzJsMTQuMjM3LDM5LjQwNnMxLjc4LDMuNjg3LDMuNjg2LDMuNjg3LDMwLjI1NS0yOS40OTIsMzAuMjU1LTI5LjQ5MmwzMS41MjUtNjAuODlMODEuNzM3LDExOC42WiIgZmlsbD0iI2M4ZGFlYSIvPjxwYXRoIGQ9Ik0xMDAuMTA2LDEzOC44NzhsLTIuNzMzLDI5LjA0NnMtMS4xNDQsOC45LDcuNzU0LDAsMTcuNDE1LTE1Ljc2MywxNy40MTUtMTUuNzYzIiBmaWxsPSIjYTljNmQ4Ii8+PHBhdGggZD0iTTgxLjQ4NiwxMzAuMTc4LDUyLjIsMTIwLjYzNnMtMy41LTEuNDItMi4zNzMtNC42NGMuMjMyLS42NjQuNy0xLjIyOSwyLjEtMi4yLDYuNDg5LTQuNTIzLDEyMC4xMDYtNDUuMzYsMTIwLjEwNi00NS4zNnMzLjIwOC0xLjA4MSw1LjEtLjM2MmEyLjc2NiwyLjc2NiwwLDAsMSwxLjg4NSwyLjA1NSw5LjM1Nyw5LjM1NywwLDAsMSwuMjU0LDIuNTg1Yy0uMDA5Ljc1Mi0uMSwxLjQ0OS0uMTY5LDIuNTQyLS42OTIsMTEuMTY1LTIxLjQsOTQuNDkzLTIxLjQsOTQuNDkzcy0xLjIzOSw0Ljg3Ni01LjY3OCw1LjA0M0E4LjEzLDguMTMsMCwwLDEsMTQ2LjEsMTcyLjVjLTguNzExLTcuNDkzLTM4LjgxOS0yNy43MjctNDUuNDcyLTMyLjE3N2ExLjI3LDEuMjcsMCwwLDEtLjU0Ni0uOWMtLjA5My0uNDY5LjQxNy0xLjA1LjQxNy0xLjA1czUyLjQyNi00Ni42LDUzLjgyMS01MS40OTJjLjEwOC0uMzc5LS4zLS41NjYtLjg0OC0uNC0zLjQ4MiwxLjI4MS02My44NDQsMzkuNC03MC41MDYsNDMuNjA3QTMuMjEsMy4yMSwwLDAsMSw4MS40ODYsMTMwLjE3OFoiIGZpbGw9IiNmZmYiLz48L3N2Zz4=" width="230"/></a>
</p>


We all love [chat.openai.com](https://chat.openai.com), but... It's TERRIBLY laggy, has daily limits, and is only accessible through an archaic web interface.

This repo is ChatGPT re-created as Telegram Bot. **And it works great.**

Demo @chatgpt_karfly_bot

## Features
- Low latency replies (it usually takes about 3-5 seconds)
- No request limits
- Message streaming.
- GPT-4 and GPT-4 Turbo y GPT-4 Vision support
- Group Chat support (/help_group_chat to get instructions)
- DALLE 2 (choose 👩‍🎨 Artist mode to generate images)
- Voice message recognition
- Code highlighting
- 15 special chat modes: 👩🏼‍🎓 Assistant, 👩🏼‍💻 Code Assistant, 👩‍🎨 Artist, 🧠 Psychologist, 🚀 Elon Musk and other. 
- Support of [ChatGPT API](https://platform.openai.com/docs/guides/chat/introduction)
- Allow only your user for protection.
- Track $ balance spent on OpenAI API.
- Dummy API key + proxy URl.


<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYmM2ZWVjY2M4NWQ3ZThkYmQ3MDhmMTEzZGUwOGFmOThlMDIzZGM4YiZjdD1n/unx907h7GSiLAugzVX/giphy.gif" />
</p>
support of [GPT-4 Turbo](https://help.openai.com/en/articles/8555510-gpt-4-turbo) + [GPT-4 Vision](https://platform.openai.com/docs/guides/vision) support

## Bot commands
- `/retry` – Regenerate last bot answer
- `/new` – Start new dialog
- `/mode` – Select chat mode
- `/balance` – Show balance
- `/settings` – Show settings
- `/help` – Show help




