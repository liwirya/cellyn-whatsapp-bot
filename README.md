[![Banner](https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Cellyn+Bot&fontSize=80&fontAlignY=35&animation=twinkling&fontColor=fff&desc=WhatsApp+Bot+built+on+Baileys&descSize=18&descAlignY=55)](https://github.com/liwirya/cellyn-whatsapp-bot)

![GitHub stars](https://img.shields.io/github/stars/liwirya/cellyn-whatsapp-bot?style=for-the-badge&color=yellow)
![GitHub forks](https://img.shields.io/github/forks/liwirya/cellyn-whatsapp-bot?style=for-the-badge&color=blue)
![Node.js](https://img.shields.io/badge/Node.js-18+-green?style=for-the-badge&logo=node.js&logoColor=white)
![Baileys](https://img.shields.io/badge/Baileys-Latest-blue?style=for-the-badge&logo=whatsapp)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

*🌸 Cellyn*

**Modern WhatsApp Bot built on Baileys with modular plugin architecture**

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *✨ Features*

|  |  |  |
|--|--|--|
| **🤖 AI Integration** ChatGPT powered responses Smart conversation | **📥 Downloader** TikTok, IG, YouTube Spotify, Twitter/X | **🔄 Converter** Sticker creator Audio & video tools |
| **👥 Group Tools** Member management Tag all & admin control | **💳 PPOB / Digi** Digiflazz integration Price & balance check | **🛠️ Owner Tools** Eval & exec commands Dynamic bot settings |

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *⚡ Quick Start*

**Requirements**
- Node.js 18+
- Git
- FFmpeg
- MongoDB / MySQL *(optional, Local JSON tersedia)*

**Installation**

```bash
# Clone repo
git clone https://github.com/liwirya/cellyn-whatsapp-bot.git
cd cellyn-whatsapp-bot

# Install dependencies
npm install

# Setup environment
cp .env.example .env
nano .env

# Run
npm start
```

**Production (PM2)**

```bash
npm install -g pm2
pm2 start ecosystem.config.cjs
pm2 save && pm2 startup
```

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *⚙️ Configuration*

Edit `.env` sesuai kebutuhan:

```env
# Database
MONGODB_URI=mongodb+srv://...
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=password
MYSQL_DATABASE=cellyn_bot

# Bot
BOT_NAME=Cellyn
OWNER_NUMBER=628xxxxxxxxxx
PREFIX=.

# API Keys
DIGIFLAZZ_USERNAME=your_username
DIGIFLAZZ_API_KEY=your_key
OPENAI_API_KEY=your_key
```

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *🔌 Plugin System*

Buat plugin baru di `src/plugins/[category]/[nama].js`:

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
        const start = Date.now();
        await m.reply("⏱️ Checking...");
        await m.reply(`🏓 Pong! ${Date.now() - start}ms`);
    },
};
```

**Plugin Properties**

| Property | Type | Description |
|---|---|---|
| `command` | `string[]` | Trigger commands |
| `permissions` | `string` | `all` / `admin` / `owner` |
| `cooldown` | `number` | Cooldown in seconds |
| `group` | `boolean` | Group only |
| `private` | `boolean` | Private only |
| `owner` | `boolean` | Owner only |
| `react` | `boolean` | Auto react on execute |

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *📁 Structure*

```
cellyn-whatsapp-bot/
├── src/
│   ├── config/          # Bot configuration
│   ├── core/            # Connect & message handler
│   ├── lib/             # Internal libraries
│   │   ├── database/    # DB drivers & models
│   │   └── schema/      # Data schemas
│   ├── plugins/         # All plugin commands
│   │   ├── ai/
│   │   ├── convert/
│   │   ├── downloader/
│   │   ├── group/
│   │   ├── info/
│   │   ├── owner/
│   │   └── tools/
│   └── utils/           # Utilities & API helpers
├── .env.example
├── ecosystem.config.cjs
└── package.json
```

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

## *📄 License*

Licensed under the **MIT License**. See [LICENSE](./LICENSE) for details.

> Removing copyright notices or claiming original authorship is not allowed.

[![](https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif)](https://github.com/liwirya/cellyn-whatsapp-bot)

---

**Maintained by [Liwirya](https://github.com/liwirya)**

[![Footer](https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer&text=Thank%20You!&fontSize=40&fontColor=ffffff&animation=twinkling&fontAlignY=75)](https://github.com/liwirya/cellyn-whatsapp-bot)
