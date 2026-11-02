# Apricus

**Apricus** is an all-in-one Discord bot: moderation, XP leveling, economy, starboard,
trivia, polls, autoroles, reminders and one-tap server setup — in a single invite.

> **Live demo, screenshots and a guided tour:**
> **[https://interlastic.github.io/apricus-showcase/](https://interlastic.github.io/apricus-showcase/)**

---

## Table of contents

- [Why Apricus](#why-apricus)
- [Features](#features)
- [Quick start](#quick-start)
- [Slash commands](#slash-command-reference)
- [Permissions](#permissions)
- [Privacy & data](#privacy--data)
- [Self-hosting](#self-hosting)
- [Showcase & screenshots](#showcase--screenshots)
- [FAQ](#faq)

---

## Why Apricus

Most servers run four or five bots at once — one for moderation, one for XP,
one for economy, one for starboard, one for trivia. Each one adds a duplicate
permission grant, a duplicate config channel, and a duplicate set of commands
to remember.

Apricus collapses that stack into one bot with one coherent command tree and a
single guided setup flow (`/quicksetup`). Every feature is opt-in per server:
if you never touch the economy module, it never posts anything.

---

## Features

| Area | What it does | Enable with |
| --- | --- | --- |
| **One-tap setup** | Guided wizard that creates the log channel, configures roles and turns on the modules you pick | `/quicksetup` |
| **Moderation** | Timeouts, bans, kicks, message purge, and a per-member warning history you can review or clear | `/ban`, `/kick`, `/mute`, `/unmute`, `/purge`, `/warn`, `/warnings`, `/clearwarnings` |
| **XP & leveling** | Passive XP for activity, per-server levels, rank cards and a leaderboard | `/rank`, `/leaderboard`, `/xpstats`, `/levelup` |
| **Economy** | Server-scoped economy module with its own balances and commands | `/economy` group |
| **Starboard** | Auto-mirrors posts that cross a reaction threshold into a channel you choose | `/starboard` group |
| **Trivia** | On-demand rounds plus a scheduled daily trivia channel | `/dailytrivia`, plus the `dailycontent` group |
| **Polls & voting** | Create polls, run them to a deadline, view results | `/newpoll`, `/poll`, `/vote`, `/votestat` |
| **Suggestions** | A suggestion board with feedback status tracking | `/suggest`, `/suggestions`, `/feedback` |
| **Autoroles & welcomes** | Role-on-join, configurable welcome and goodbye messages | `/autorole`, `/welcome`, `/goodbye` |
| **Reminders** | "Remind me in 3 hours" with persistent, restart-safe scheduling | `/remind`, `/reminders`, `/remind_cancel` |
| **Utility** | Server info, bot info, help, invite link, ping/latency check | `/serverinfo`, `/botinfo`, `/help`, `/invite`, `/ping` |
| **Fun** | Coin flip, dice, 8-ball, jokes, rock-paper-scissors | `/flip`, `/roll`, `/8ball`, `/joke`, `/rps` |

Every module is independent. Disabling one never breaks the others.

---

## Quick start

1. **Add the bot** — use the link below and pick a server you manage.
2. **Run the wizard** — type `/quicksetup` in any channel. Apricus will ask what
   you want (moderation, leveling, starboard, trivia, autoroles) and create the
   channels it needs.
3. **Add the bot role** — give Apricus a role and drag it above the roles it
   should be able to assign. Discord blocks role assignment below the bot's own
   role, and this is the single most common setup mistake.
4. **Optional tuning** — `/starboard`, `/threshold`, `/levelup`, `/welcome` and
   `/goodbye` let you adjust each module without re-running setup.

### Add Apricus to your server

**[https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=446945422423&scope=bot%20applications.commands](https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=446945422423&scope=bot%20applications.commands)**

The invite requests permissions mask `446945422423`. You can uncheck anything
you do not want during authorization — the bot degrades gracefully and will
tell you which permission a given command is missing instead of failing silently.

---

## Slash command reference

Apricus is slash-command first. All of the following are real, registered
commands — type `/` in Discord to see the ones available in your server.

**Setup & config**
`/quicksetup` · `/setup` · `/setup_status` · `/config` · `/set` · `/onboard` · `/tour`

**Moderation**
`/ban` · `/kick` · `/mute` · `/unmute` · `/purge` · `/warn` · `/warnings` · `/clearwarnings`

**Leveling**
`/rank` · `/leaderboard` · `/xpstats` · `/levelup` · `/addxp`

**Starboard**
`/starboard` (subcommands) · `/view` · `/threshold` · `/remove`

**Content & engagement**
`/dailytrivia` · `/dailycontent` (group) · `/newpoll` · `/poll` · `/vote` · `/votestat`

**Suggestions & feedback**
`/suggest` · `/suggestions` · `/feedback` · `/feedbackboard` · `/feedbackstatus`

**Welcome & roles**
`/autorole` (group) · `/welcome` (group) · `/goodbye` (group)

**Reminders**
`/remind` · `/reminders` · `/remind_cancel`

**Utility & fun**
`/serverinfo` · `/botinfo` · `/help` · `/invite` · `/ping` · `/flip` · `/roll` · `/8ball` · `/joke` · `/rps`

Admin/ops commands (`/broadcast`, `/admin_status`, `/usage`, `/diagnostics`-style
tools) are restricted to the bot owner and are not available to server admins.

---

## Permissions

The invite URL above requests a single fixed permissions mask:

```
446945422423
```

This covers reading messages and history, sending and embedding messages,
managing roles, moderating members (kick/timeout/ban), managing messages for
purge, and adding reactions for starboard and polls. Apricus does **not**
request Administrator.

If you prefer least-privilege, you can run Apricus with a smaller role set —
the leveling, trivia, poll and suggestion modules work fine with read/send and
manage-messages only.

---

## Privacy & data

- Apricus stores only what its features require to function: per-server
  configuration, XP totals for members who have earned XP, warning records,
  reminders you create, and the content you explicitly submit (suggestions,
  starboard posts).
- It does **not** read the contents of private messages or DMs you have with
  other users, and it does **not** transcribe voice channels.
- No data is sold, shared with third parties, or used for advertising.
- No analytics tracking scripts are embedded anywhere in the bot or its
  documentation.
- Member-level data is scoped to the server that generated it. Removing the bot
  from a server stops all further collection for that server.

---

## Self-hosting

Apricus is built on `discord.py` and runs as a set of independent cogs.

```bash
git clone https://github.com/Interlastic/apricus.git
cd apricus
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
# create bot/.env with DISCORD_TOKEN and your client ID
python -m bot.bot_runner
```

Each feature lives in its own cog under `bot/cogs/`, so you can delete or
disable modules you do not want without touching the runner.

---

## Showcase & screenshots

Want to see it working before you invite it? The interactive showcase walks
through moderation, leveling, starboard and the setup wizard with real
screenshots and command output:

**[https://interlastic.github.io/apricus-showcase/](https://interlastic.github.io/apricus-showcase/)**

The showcase also contains the same invite link used in this README, so you can
go from "reading about it" to "it is in my server" in one click.

---

## FAQ

**Does Apricus have AI chat?**
No. Apricus is a deterministic command bot. Every response comes from a
feature you configured, not from a language model.

**Can I use only one module?**
Yes. Modules are opt-in and independent. Run `/quicksetup` and enable just the
one you want.

**Why are slash commands not showing up?**
Registration is asynchronous and can take a minute after the invite. Re-open
the command bar, or kick and re-invite the bot. Check that the invite included
the `applications.commands` scope.

**Where is the source?**
This repository. See the [self-hosting](#self-hosting) section, and the
[showcase](https://interlastic.github.io/apricus-showcase/) for a visual tour.

---

## License

Source in this repository is provided for reference and self-hosting.

---

*Built with [discord.py](https://discordpy.readthedocs.io/).*
