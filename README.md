[![Banner](https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,30&height=180&section=header&text=Cellyn&fontSize=90&fontAlignY=38&animation=twinkling&fontColor=fff&desc=WhatsApp+Bot+built+on+Baileys&descSize=16&descAlignY=58)](https://github.com/liwirya/cellyn-whatsapp-bot)

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-20+-43A047?style=flat-square&logo=node.js&logoColor=white)
![Baileys](https://img.shields.io/badge/Baileys-Latest-00BCD4?style=flat-square&logo=whatsapp&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-7E57C2?style=flat-square)
![Stars](https://img.shields.io/github/stars/liwirya/cellyn-whatsapp-bot?style=flat-square&color=FFA726)

</div>

<div align="center">

<img src="./assets/thumb.jpg" width="600" alt="Cellyn Preview" />

</div>

---

## ✨ What's Cellyn?

**Cellyn** is your friendly neighborhood WhatsApp bot — built on top of [Baileys](https://github.com/WhiskeySockets/Baileys) and designed to be **modular, extensible, and easy to hack on**.

Whether you want a simple auto-reply bot, a full-blown group manager, or a PPOB integration via Digiflazz, Cellyn's got your back. The plugin system is dead simple: drop a file, and it just works.

> 🏗️ **Architecture Note:** Cellyn's project structure is inspired by [Katsumi](https://github.com/nat9h/Katsumi) by [nat9h](https://github.com/nat9h). All documentation, plugins, and modifications here are original work by the Cellyn team.

---

## 🚀 Getting Started

### Prerequisites

Before we begin, make sure you have:

- **Node.js 20+** — because we're living in the future
- **Git** — for cloning (obviously)
- **FFmpeg** — for all the media magic
- **MongoDB or MySQL** — *optional*, but recommended for production. Don't worry, Local JSON works fine for small setups.

### Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/liwirya/cellyn-whatsapp-bot.git
cd cellyn-whatsapp-bot

# 2. Install dependencies
npm install

# 3. Set up your environment
cp .env.example .env
# Edit .env with your favorite editor
```

### Running the Bot

```bash
# 🛠️ Development mode
npm start

# 🚀 Production mode (with PM2)
npm install -g pm2
pm2 start ecosystem.config.cjs
pm2 save && pm2 startup
```

> 💡 **Pro tip:** PM2 keeps your bot alive even after crashes or reboots. Highly recommended for production!

---

## ⚙️ Configuration

Here's a quick peek at your `.env`:

```env
# === Bot Settings ===
BOT_NAME=Cellyn
OWNER_NUMBER=628xxxxxxxxxx
PREFIX=.

# === Database (pick your poison) ===
MONGODB_URI=mongodb+srv://...
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=password
MYSQL_DATABASE=cellyn_bot

# === API Keys ===
DIGIFLAZZ_USERNAME=your_username
DIGIFLAZZ_API_KEY=your_key
OPENAI_API_KEY=your_key
```

> 🔑 **Heads up:** Never commit your `.env` file! It's already in `.gitignore`, but double-check just to be safe.

---

## 🔌 Plugin System

Plugins live in `src/plugins/[category]/[name].js`. Each one is just a plain JavaScript object — no black magic, no steep learning curve.

### Minimal Example

```js
export default {
    name: "ping",
    description: "Check bot latency",
    command: ["ping"],
    category: "tools",
    permissions: "all",
    cooldown: 3,
    react: true,

    execute: async (m) => {
        await m.reply(`Pong! ${Date.now()}ms`);
    },
};
```

That's it. Save the file, restart the bot, and `.ping` is ready to go.

### Plugin Properties Cheat Sheet

| Property | Type | What it does |
|---|---|---|
| `command` | `string[]` | The triggers that activate this plugin |
| `permissions` | `string` | Who can use it: `all` / `admin` / `owner` |
| `cooldown` | `number` | Anti-spam cooldown in seconds |
| `group` | `boolean` | Only works in group chats |
| `private` | `boolean` | Only works in private chats |
| `owner` | `boolean` | Owner-only command |
| `botAdmin` | `boolean` | Requires bot to be group admin |
| `react` | `boolean` | Auto-reacts with ✅ when executed |
| `wait` | `string\|null` | Shows a "please wait" message before running |
| `dailyLimit` | `number` | Max uses per user per day |

---

## 📁 Project Structure

```
cellyn-whatsapp-bot/
├── src/
│   ├── config/              # Static bot configuration
│   ├── core/
│   │   ├── connect.js       # Baileys connection handler
│   │   └── message.js       # Incoming message processor
│   ├── lib/
│   │   ├── database/        # DB drivers (MongoDB, MySQL, Local)
│   │   │   ├── drivers/
│   │   │   └── models/      # User, Group, Settings, Session
│   │   ├── schema/          # Data validation schemas
│   │   └── serialize.js     # Message serializer
│   ├── plugins/
│   │   ├── ai/              # AI / ChatGPT integrations
│   │   ├── convert/         # Sticker, audio, video converters
│   │   ├── digi/            # PPOB — Digiflazz top-up
│   │   ├── downloader/      # TikTok, IG, YouTube, Spotify, etc.
│   │   ├── group/           # Group management tools
│   │   ├── info/            # Help, menu, ping
│   │   ├── owner/           # Owner-only commands
│   │   └── tools/           # Misc utilities
│   └── utils/               # API helpers, formatters
├── assets/                  # Static assets (preview, etc.)
├── .env.example
├── ecosystem.config.cjs
└── package.json
```

---

## 🤝 Contributing

We love contributions! Check out [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📜 License

MIT — see [LICENSE](./LICENSE) for the full text.

> ⚠️ **Please don't:** Remove copyright notices or claim this as entirely your own work. Open source thrives on attribution! 🙏

---

<div align="center">

### Made with ☕ and late-night debugging by [Liwirya](https://github.com/liwirya)

<br>

[![Footer](https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,30&height=120&section=footer&text=Thank+You!&fontSize=38&fontColor=ffffff&animation=twinkling&fontAlignY=75)](https://github.com/liwirya/cellyn-whatsapp-bot)

</div>
