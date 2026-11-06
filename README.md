# Apricus

**Apricus** is an all-in-one Discord bot: moderation, XP leveling, economy, starboard,
trivia, polls, autoroles, reminders and one-tap server setup — in a single invite.

> **Feature showcase, command reference and a guided tour:**
> **[https://apricus.mingalabs.com/](https://apricus.mingalabs.com/)**

---

## Add Apricus to your server

**[https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=564496410471639&scope=bot%20applications.commands](https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=564496410471639&scope=bot%20applications.commands)**

**What you get in the first 30 seconds:**

- One invite, one bot: moderation, XP, economy, starboard, trivia, polls, autoroles, reminders
- `/quicksetup` in any channel creates the log channel and enables the modules you pick
- Everything is opt-in per server — a module you never enable never posts anything
- Slash commands register within a minute; type `/` to see them

> **Not a source repository.** Apricus is a **closed-source, hosted service**.
> This repo is a public information page only. There is no source code here to read,
> download, fork, or self-host, and no source repository exists. Everything Apricus
> does runs on our hosted infrastructure - you add it to your server with the invite
> link at the top of this page.
>
> **License:** Proprietary. All rights reserved. No source license is granted.

## Table of contents

- [Add Apricus to your server](#add-apricus-to-your-server)
- [Why Apricus](#why-apricus)
- [Features](#features)
- [Quick start](#quick-start)
- [Slash commands](#slash-command-reference)
- [Permissions](#permissions)
- [Privacy & data](#privacy--data)
- [Hosting model](#hosting-model)
- [Showcase & tour](#showcase--tour)
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
| **Economy** | Apricots currency: daily claim, pay, beg, shop, buy, inventory, betting, duels and slots | `/balance`, `/daily`, `/pay`, `/beg`, `/shop`, `/buy`, `/inventory`, `/bet`, `/duel`, `/slots` |
| **Starboard** | Auto-mirrors posts that cross a reaction threshold into a channel you choose | `/starboard` group |
| **Trivia** | On-demand rounds plus a scheduled daily trivia channel | `/dailytrivia`, plus the `dailycontent` group |
| **Daily word game** | Semantle: everyone in the server works the same target word each day. Apricus ranks each guess by how close it is in **meaning** to the target — a rank out of roughly 21,000 words plus a hot/warm/cold band. It pays no Apricots and no currency | `/semantle`, `/semantlestats`, `/semantlehelp` |
| **Polls & voting** | Create polls, run them to a deadline, view results | `/newpoll`, `/poll`, `/vote`, `/votestat` |
| **Suggestions** | A suggestion board with feedback status tracking | `/suggest`, `/suggestions`, `/feedback` |
| **Autoroles & welcomes** | Role-on-join, configurable welcome and goodbye messages | `/autorole`, `/welcome`, `/goodbye` |
| **Reminders** | "Remind me in 3 hours" with persistent, restart-safe scheduling | `/remind`, `/reminders`, `/remind_cancel` |
| **Utility** | Server info, bot info, help, invite link, ping/latency check | `/serverinfo`, `/botinfo`, `/help`, `/invite`, `/ping` |
| **Fun** | Coin flip, dice, 8-ball, jokes, rock-paper-scissors | `/flip`, `/roll`, `/8ball`, `/joke`, `/rps` |

Every module is independent. Disabling one never breaks the others.

## MEE6 alternative (and why not Carl-bot either)

One install instead of three bots: Apricus covers moderation, leveling, economy,
starboard and trivia together, and configures itself in about 30 seconds with
`/quicksetup` - no dashboard, no config file, no premium paywall for the basics.
See the side-by-side comparison: https://apricus.mingalabs.com/mee6-alternative.html

---

## Quick start

1. **Add the bot** — use the link below and pick a server you manage.
2. **Run the wizard** — type `/quicksetup` in any channel. Apricus will ask what
   you want (moderation, leveling, starboard, trivia, autoroles) and create the
   channels it needs.
3. **Add the bot role** — give Apricus a role and drag it above the roles it
   should be able to assign. Discord blocks role assignment below the bot's own
   role, and this is the single most common setup mistake.
4. **Optional tuning** — `/starboard`, `/starboard threshold`, `/levelup`, `/welcome set` and
   `/goodbye set` let you adjust each module without re-running setup.

### Install link (same as above)

The full authorization URL, repeated here for convenience:

**[https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=564496410471639&scope=bot%20applications.commands](https://discord.com/oauth2/authorize?client_id=1565375148717121616&permissions=564496410471639&scope=bot%20applications.commands)**

The invite requests permissions mask `564496410471639`. You can uncheck anything
you do not want during authorization — the bot degrades gracefully and will
tell you which permission a given command is missing instead of failing silently.

---

## Slash command reference

Apricus is slash-command first. All of the following are real, registered
commands — type `/` in Discord to see the ones available in your server.

**Setup & config**
`/quicksetup` · `/setup` · `/setup_status` · `/config` · `/autorole set` · `/onboard` · `/tour`

**Moderation**
`/ban` · `/kick` · `/mute` · `/unmute` · `/purge` · `/warn` · `/warnings` · `/clearwarnings`

**Leveling**
`/rank` · `/leaderboard` · `/xpstats` · `/levelup` · `/addxp`

**Economy**
`/balance` · `/daily` · `/pay` · `/beg` · `/shop` · `/buy` · `/inventory` · `/bet` · `/duel` · `/slots`

**Starboard**
`/starboard` (subcommands) · `/starboard view` · `/starboard threshold` · `/starboard remove`

**Content & engagement**
`/dailytrivia` · `/dailycontent` (group) · `/newpoll` · `/poll` · `/vote` · `/votestat`

**Daily word game (Semantle)**
`/semantle word:<word>` (guess) · `/semantle` (today's status) · `/semantlestats` (standings) · `/semantlehelp` (how scoring works)

**Suggestions & feedback**
`/suggest` · `/suggestions` · `/feedback` · `/feedbackboard` · `/feedbackstatus`

**Welcome & roles**
`/autorole` (group) · `/welcome` (group) · `/goodbye` (group)

**Reminders**
`/remind` · `/reminders` · `/remind_cancel`

**Utility & fun**
`/serverinfo` · `/botinfo` · `/help` · `/invite` · `/ping` · `/flip` · `/roll` · `/8ball` · `/joke` · `/rps`

Admin/ops commands (`/broadcast`, `/admin_status`, `/usage`
tools) are restricted to the bot owner and are not available to server admins.

---

## Permissions

The invite URL above requests a single fixed permissions mask:

```
564496410471639
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
- The bot embeds no analytics or advertising scripts and the website sets no
  cookies. The website does carry one privacy-minimal page counter
  ([Abacus](https://abacus.jasoncameron.dev)) that increments once per page load,
  so we can tell whether anyone arrives at all. It is a single counter, not an
  analytics platform: no cross-site tracking, fingerprinting or profiling.
- Member-level data is scoped to the server that generated it. Removing the bot
  from a server stops all further collection for that server.

---

## Hosting model

Apricus is a **closed-source, hosted service**. There is no source code to download
or run yourself: you use the live bot directly via the invite link above, and
configuration happens entirely through slash commands.

---

## Showcase & tour

Want to see it working before you invite it? The interactive showcase walks
through moderation, leveling, starboard and the setup wizard with real
command output and the exact setup flow:

**[https://apricus.mingalabs.com/](https://apricus.mingalabs.com/)**

The showcase also contains the same invite link used in this README, so you can
go from "reading about it" to "it is in my server" in one click.

Pages on the site, if you want to go straight to one:

- [Main showcase](https://apricus.mingalabs.com/index.html) - full feature list and command reference
- [MEE6 alternative](https://apricus.mingalabs.com/mee6-alternative.html) - how Apricus compares, module by module
- [Moderation bot guide](https://apricus.mingalabs.com/discord-moderation-bot.html) - moderation, autorole and audit-log features
- [Permissions calculator](https://apricus.mingalabs.com/discord-permissions-calculator.html) - build an install link with exactly the flags you want

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

**Is Apricus open-source?**
No. Apricus is a closed-source hosted service. You do not need to run any code — just invite the bot and run `/quicksetup`. See the
[showcase](https://apricus.mingalabs.com/) for a guided tour.

---

## License

Apricus is a closed-source hosted product. This repository holds public
documentation and landing-page assets only — it does not contain the bot’s
source code.

---

*Built with [discord.py](https://discordpy.readthedocs.io/).*
