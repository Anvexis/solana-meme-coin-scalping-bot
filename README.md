# SOLMEME BOT 🟢
### Solana Meme Coin Scalping Bot — Single HTML File, No Backend

![Strategy](https://img.shields.io/badge/Strategy-Scalp%20Machine-00e5a0?style=flat-square)
![Chain](https://img.shields.io/badge/Chain-Solana-9945FF?style=flat-square)
![DEX](https://img.shields.io/badge/DEX-Jupiter%20V6-FF6B00?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## What is this?

<img width="1910" height="938" alt="{9DB35F25-7EF7-4F48-A5CD-6A1B2C318B70}" src="https://github.com/user-attachments/assets/405a09a4-dca5-409f-ac68-e942da0d1a91" />

---

** Available to Purchase - link : https://narcisse51.gumroad.com/l/wstfrk **

A fully self-contained **Solana meme coin scalping bot** that runs entirely in your browser — no server, no backend, no installation required beyond Python or Node.js for a local HTTP server.

**Strategy: Scalp Machine** — catches micro-moves of 1–3% on high-liquidity meme coins using rapid open/close cycles with tight TP and SL. Based on live testing, the bot becomes consistently profitable with a **minimum deposit of 4–6 SOL (~$300–$500 at current prices)**.

---


** Available to Purchase - link : https://narcisse51.gumroad.com/l/wstfrk **


---

## Features

- **Zero popups** — uses a Hot Wallet (private key in memory) for fully automatic transaction signing
- **Real Jupiter swaps** — BUY/SELL via `lite-api.jup.ag` (no API key needed, CORS enabled)
- **Auto RPC selection** — tests Ankr, Alchemy, Helius, PublicNode and picks the fastest
- **Real PnL tracking** — computed from actual SOL received vs SOL spent, not from price simulation
- **Fee transparency** — priority fee + swap fee tracked separately, real net profit shown
- **Tradability check** — verifies each token on Jupiter at startup, skips non-tradable ones
- **Cooldown system** — prevents re-entering same token immediately after close
- **Paper / Live mode** — test safely before going live

---

## Tokens traded

| Token | Symbol | Liquidity |
|-------|--------|-----------|
| Bonk | BONK | High |
| dogwifhat | WIF | High |
| Popcat | POPCAT | High |
| Book of Meme | BOME | High |
| cat in a dogs world | MEW | Medium |
| TRUMP | TRUMP | High |
| Fartcoin | FARTCOIN | Medium |
| Samoyed Coin | SAMO | Medium |
| Jupiter | JUP | High |
| Orca | ORCA | Medium |

---

## Recommended settings (based on live testing)

| Parameter | Recommended |
|-----------|-------------|
| Risk per trade | 2–10% |
| Take Profit | 3–6% |
| Stop Loss | 2–3% |
| Max positions | 2–3 |
| Cooldown | 60–90s |
| Slippage BPS | 50 |
| Swap route | Direct 1-hop |
| Priority Fee | 1,000 lamports |

> Tested on real Solana mainnet. With a 1–2 SOL deposit and the settings above, the bot shows positive PnL after fees in live conditions.

---

## ⚠️ Risk Warning

- **Never use your main wallet.** Always use a dedicated bot wallet with only the funds you can afford to lose.
- Crypto trading carries significant risk. The bot can lose money.
- Past test results do not guarantee future performance.

---

## Requirements (Linux)

- A modern browser (Chrome or Brave recommended)
- Python 3 **or** Node.js (for local HTTP server)
- A Solana wallet with some SOL (Phantom to export the private key)

---

### Step 1 — Start a local HTTP server

**Option A — Python 3** (recommended, available on almost all Linux systems):

```bash
python3 -m http.server 3000
```

**Option B — Node.js:**

```bash
npx serve . --port 3000
```

**Option C — PHP (if installed):**

```bash
php -S localhost:3000
```

### Step 3 — Open the bot in your browser

```
http://localhost:3000/solmeme-bot.html
```

> ⚠️ Do **not** open the file directly with `file://` — Hot Wallet signing does not work without a local server.

---

## Step 4 — Connect your Hot Wallet

1. Open **Phantom Wallet** in your browser
2. Go to **Settings → Manage Accounts → (select your bot account) → Show Private Key**
3. Copy the base58 private key
4. Click the **🔑 HOT KEY** button in the top-right corner of the bot
5. Paste the key and click **Load key**

Your wallet address and SOL balance will appear in the left panel.

> The key is stored **only in page memory** — it is never sent to any server and is cleared when you close the tab.

---

## Step 5 — Configure and start

1. **Switch to PAPER mode** first (blue button at the top) — test with no real money
2. Adjust Risk, TP, SL, and Cooldown sliders
3. Click **▶ START BOT**
4. Watch the Trade Log and Session Stats on the right
5. Once you're satisfied with paper results, switch to **⚡ LIVE** and confirm

---

## RPC Endpoint

The bot auto-selects the fastest free RPC at startup. For best performance you can register a **free personal API key** at:

- [helius.dev](https://helius.dev) — 100k requests/day free
- [alchemy.com](https://alchemy.com) — 300M compute units/month free

Paste your custom RPC URL in the **RPC Endpoint** field in the left panel.

---

## File structure

```
solmeme-bot/
├── solmeme-bot.html   # Main bot file (English, Scalp Machine only)
└── README.md             # This file
```

---

## How the Scalp Machine works

```
Every 2 seconds:
  → Check price history (last 3 candles)
  → If |price change| > 1% → signal detected
  → Execute BUY via Jupiter (SOL → token)
  → Watch price every tick
  → If profit >= TP% → close immediately
  → If loss >= SL% → close immediately
  → Cooldown: skip this token for 60s
```

All swaps go through **Jupiter aggregator** which finds the best available pool. For meme coins, it typically routes through Raydium CLMM (0.01–0.04% pool fee) or Orca Whirlpool (0.01–0.05%).

---

## Profitability notes

From live testing sessions:

- With **4 SOL deposit (~$320)** — break-even to slightly positive after fees
- With **6+ SOL deposit (~480$)** — consistently positive session PnL

The bot is a **scalper** — it makes many small trades. More capital = more positions open simultaneously = more profit per session.


** Available to Purchase - link : https://narcisse51.gumroad.com/l/wstfrk **

---

## License

MIT — free to use, modify, and distribute.

---

*Built with Solana Web3.js · Jupiter V6 API · Chart.js*
