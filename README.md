# Nifty Credit-Spread Telegram Bot (Paper + Angel One Live)

Telegram bot je Nifty par credit spread trade kare chhe (Supertrend / EMA / RSI-WMA strategy).
Paper mode ane Angel One Live mode support kare chhe.

## Setup
```bash
pip install -r requirements.txt
cp .env.example .env      # ane andar potani value bharo
python user_nifty_bot.py
```

## Environment variables
| Name | Description |
|---|---|
| `TELEGRAM_TOKEN` | BotFather no token |
| `TELEGRAM_CHAT_ID` | Tamaro chat id (fakt aa chat bot vapri shake) |
| `ANGEL_API_KEY`, `ANGEL_CLIENT_ID`, `ANGEL_PIN`, `ANGEL_TOTP_SECRET` | Angel One credentials (live mode mate) |
| `PROXY_URL` | Optional static IP proxy |
| `ADMIN_PASSWORD` | Strategy/Timeframe unlock mate: Telegram ma `/admin <password>` |
| `DATA_DIR` | Optional folder (Railway Volume: `/data`) |

## Telegram commands
`/start /menu /dashboard /run /stop /exit /mode paper|live /pnl /summary /trades /history /settings`

Strategy ane timeframe: pehla `/admin <password>` lakho (10 min unlock), pachi Menu → ⚙️ Settings. `/admin lock` thi turant lock.

## Deploy (Railway)
1. GitHub repo Railway sathe connect karo.
2. Variables ma upar ni env values nakho.
3. Volume mount kari `DATA_DIR=/data` set karo.
4. `Procfile` thi `worker` automatic chalshe.

⚠️ Live mode ma sacho paisa vaparay chhe. Pehla Paper mode ma test karo.
