# epicsevenbot

#  ⏰EpicSeven Clock Bot

![epicsevenbot](https://github.com/user-attachments/assets/8728ed62-2c00-45cd-a17e-6a40c950d1ef)

A Discord bot that tracks Epic Seven daily resets, weekly resets, Guild War phases, and custom event pings — all updated live every 5 seconds.

Discord Invite Link:
https://discord.com/oauth2/authorize?client_id=1490310472220672000&permissions=406679792656&integration_type=0&scope=bot

---

## 🆓 Free Features (all servers)

- Live embed showing **Server Time**, **Daily Reset**, **Weekly Reset**, and **Guild War** phase + countdown
- Category channel name updates every 10 minutes with compact reset times
- All 3 **automatic Guild War role pings** (war start, 12h left, 2h left)
- Auto-repost if the embed is deleted
- **Countdown Timers** — multiple named countdown timers with expiry pings
- **Custom Pings** — daily or weekly scheduled role pings with custom messages

> All new servers receive a **30-day free trial** with full premium access.

---

## ⚙️ Getting Started

### 1. Run `/setup`

Requires **Manage Server** permission. This is a 4-step wizard:

| Step | What it does |
|---|---|
| 1 — Region | Select your server's Epic Seven region. If Europe, you'll be prompted for a UTC offset. |
| 2 — Category channel | Select the category the bot will update with live timer info. |
| 3 — Embed channel | Select the text channel where the live embed will be posted. |
| 4 — Role | Select the role the bot will ping for all notifications. |

After confirming, the bot posts the live embed and starts tracking immediately.

> Re-running `/setup` on a configured server will show a warning before resetting all data.

---

## 🌍 Regions & Reset Times

| Region | Daily Reset (UTC) | Display timezone |
|---|---|---|
| 🇰🇷 Korea | 18:00 UTC | UTC+9 (KST) |
| 🌏 Asia | 18:00 UTC | UTC+8 (CST) |
| 🇯🇵 Japan | 18:00 UTC | UTC+9 (JST) |
| 🇪🇺 Europe | 03:00 UTC + custom offset | Your UTC offset |
| 🌍 Global | 10:00 UTC | UTC |

Weekly reset occurs every **Monday** at the same UTC hour as the daily reset for your region.

---

## 📋 All Commands

### Free commands

| Command | Description |
|---|---|
| `/setup` | Run the 4-step setup wizard (requires Manage Server) |
| `/daily` | Show the next Daily Reset countdown |
| `/weekly` | Show the next Weekly Reset countdown |
| `/guildwar` | Show the current Guild War phase and countdown |
| `/help` | Show all commands and your current access status |
| `/premium` | View upgrade options and pricing |
| `/payment-status` | Check your trial or payment status |

### Premium commands

| Command | Description |
|---|---|
| `/countdowntimer create` | Create a named countdown timer with a custom expiry ping |
| `/countdowntimer clear <number>` | Remove a countdown timer by number |
| `/countdowntimer check` | List all active countdown timers |
| `/countdowntimer hide` | Hide countdown timers from the embed |
| `/countdowntimer show` | Show countdown timers in the embed |
| `/customping create` | Create a custom daily or weekly ping |
| `/customping list` | View all your custom pings |
| `/customping delete <ping-number>` | Delete a custom ping by its number |

### Settings commands

| Command | Description |
|---|---|
| `/settings look_new` | Switch to new-style embed (separator lines, lowercase units) |
| `/settings look_old` | Switch to classic embed layout (default) |
| `/settings dash_on` | Enable dashes in countdown strings |
| `/settings dash_off` | Disable dashes in countdown strings (default) |

---

## 🕒 Live Embed

The embed updates every **5 seconds** and shows:

- 🕒 Current server time (HH:MM format)
- 🌍 Daily Reset countdown
- 🔁 Weekly Reset countdown
- ⚔️ Guild War phase and countdown
- ⏱️ Custom Countdown Timers *(premium)*

The **category channel** updates every 10 minutes with compact times:
```
🕒18:42 | D 21h 13m | W 21h 13m | GW 14h 13m
🕒03:01 | 🔥RESET NOW | D 00h 08m | W 1d 00h | GW 01h 58m
🕒22:15 | 🔥RESET SOON | D 00h 44m | W 3d 22h | GW 05h 22m
```

---

## ⚔️ Guild War Schedule

Guild War runs on a fixed UTC schedule regardless of region:

| Day | Phase |
|---|---|
| Monday | ⚔️ Battle Phase (starts 03:00 UTC) |
| Tuesday | 📋 Preparation Phase |
| Wednesday | ⚔️ Battle Phase (starts 03:00 UTC) |
| Thursday | 📋 Preparation Phase |
| Friday | ⚔️ Battle Phase (starts 03:00 UTC) |
| Saturday | 🏅 Standby / Rewards |
| Sunday | 📋 Preparation Phase |

Each war lasts **24 hours** from 03:00 UTC. The `/guildwar` command and embed always show the current phase and a countdown to the next transition.

---

## 🔔 Automatic Guild War Pings (Free — all servers)

The bot automatically pings the configured role three times per war. All ping messages are deleted 2 minutes after sending.

| Time (UTC) | Message |
|---|---|
| Mon / Wed / Fri at 03:00 | ⚔️ Guild War has started! The attack phase is now open. You have 24 hours — good luck, Heroes! |
| Mon / Wed / Fri at 15:00 | ⚠️ 12 hours left in Guild War! Don't forget to use all your attacks! |
| Tue / Thu / Sat at 01:00 | 🚨 2 hours remaining in Guild War! Last chance to use your attacks before time runs out! |

---

## ⏳ Countdown Timers (`/countdowntimer create`)

Countdown timers display a live countdown in the embed and ping when they expire.

1. Run `/countdowntimer create`
2. Enter a **title** (e.g. `Moonlight Covenant Event`)
3. Enter the duration in **days**, **hours**, and **minutes**
4. Enter the **ping message** to send when the timer expires (e.g. `Event is over! Check rewards!`)

You can create multiple timers at once. Use `/countdowntimer check` to see all active timers and `/countdowntimer clear <number>` to remove one.

---

## 🗓️ Custom Pings (`/customping create`)

Custom pings let you schedule any recurring message with a role or user mention.

1. Run `/customping create`
2. Choose **Daily** (fires every day) or **Weekly** (fires on a specific day)
3. Enter the **time** (HH:MM in UTC) and your **message**
4. For weekly pings, select the **day of the week**
5. Choose **who to ping** — default role, custom role, or a specific user

Use `/customping list` to see all active pings and their assigned numbers.
Use `/customping delete <number>` to remove one.

---

## 💳 Pricing

| Plan | Price | Coverage |
|---|---|---|
| Subscription | $2.50 / month | Premium on all bots, unlimited servers |
| Lifetime | $25 one-time | This bot only, 1 server (transferable) |

Run `/premium` to see payment links. Run `/payment-status` to check your current status.

---

## 🆘 Support

Contact **tinustk** on Discord for any questions, bugs, or support.
