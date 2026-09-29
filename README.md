# Ask Picapool

A skill that lets your AI assistant ask Picapool to find someone near you
who wants the same thing — a badminton partner tonight, a flatmate, someone
to split the airport cab with, three more people so the bulk order ships.

It works by writing the message for you and handing you a WhatsApp link.
You read it, you press send. **The skill never sends anything itself and
never talks to Picapool.**

## Install

**Claude Code**

```bash
/plugin marketplace add picapool-tech/ask-picapool
```

```bash
/plugin install ask-picapool@picapool
```

**Any assistant that reads skills**

```bash
npx skills add picapool-tech/ask-picapool
```

**claude.ai** — download `skills/ask-picapool/`, zip it, and upload it
under Settings → Capabilities → Skills.

**Anything else** — paste this into the chat:

```
https://raw.githubusercontent.com/picapool-tech/ask-picapool/main/skills/ask-picapool/SKILL.md
```

## What it does

1. Notices when the thing you need is a person nearby, and offers.
2. Builds the ask from what it already knows — what, where, when, and the
   one or two extra facts that kind of ask needs (skill level for a game,
   budget for a room).
3. Writes it as a normal WhatsApp message and shows it to you in full.
4. Gives you a `wa.me` link that opens WhatsApp with it already typed.

From there it is an ordinary Picapool conversation. Picapool searches, and
the result arrives as its own message. Nobody's contact details are handed
out; both sides opt in before an introduction.

## Before you publish this

The repo must be **public** for the marketplace and `npx skills add`
routes to work. The WhatsApp number is already set to the live Picapool
Business number (`+91 72240 52216`).

## Why a skill and not a connector

A skill is a markdown file. There is no server to run, no OAuth, no API
keys, no rate limits, and it works on every assistant that can read one.

It also means the message reaches Picapool through the same signed WhatsApp
webhook as every other message, from a real phone number — so identity,
location and consent all work exactly as they already do. No new trust
surface, no new way in.

MIT licensed.
