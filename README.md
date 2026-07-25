<div align="center">

# 🤙 /bro

**When the answer made you go "bro what" — type `/bro` and get it in plain language.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Format: Agent Skills](https://img.shields.io/badge/format-Agent%20Skills-blue)](https://agentskills.io)
[![Works with](https://img.shields.io/badge/works%20with-Hermes%20%C2%B7%20Claude%20Code%20%C2%B7%20Codex%20%C2%B7%20opencode-blueviolet)](#compatibility)

</div>

---

## What is this?

`/bro` is a tiny [Agent Skills](https://agentskills.io)-format skill with one job: when the assistant's last reply was too dense, too jargon-heavy, or too formal, you type `/bro` and it re-explains **its own previous message** like a smart friend over a beer.

No new information. No new answers. Just the same thing, said in a way that's impossible to misunderstand.

It's one markdown file. The whole skill is [`SKILL.md`](SKILL.md).

## Compatibility

Works with any agent that reads the Agent Skills format — and ships thin slash-command wrappers where a skill alone doesn't give you a typed `/bro`:

| Tool | Skill location | Typed `/bro` via |
|---|---|---|
| **Hermes Agent** | `~/.hermes/skills/bro/SKILL.md` | skill (auto) |
| **Claude Code** | `~/.claude/skills/bro/SKILL.md` | `~/.claude/commands/bro.md` |
| **OpenAI Codex** | `~/.codex/skills/bro/SKILL.md` | `~/.codex/prompts/bro.md` |
| **opencode** | `~/.config/opencode/skills/bro/SKILL.md` | `~/.config/opencode/command(s)/bro.md` |

## Install

**One-liner** — detects which tools you have and installs into each:

```bash
bash <(curl -fsSL https://raw.githubusercontent.com/luchasarie/bro-skill/main/install.sh)
```

**Or from a clone** (better if you want to pull updates later):

```bash
git clone https://github.com/luchasarie/bro-skill.git
cd bro-skill
./install.sh          # installs into every detected tool
./install.sh --all    # or force-install into all four
```

Then restart your agent session and type `/bro` after any reply that made your eyes glaze over.

## Update

```bash
cd bro-skill && git pull && ./install.sh
```

(Or just re-run the one-liner — it's idempotent.)

## Example

**Assistant:**

> The refactor introduces an idempotent reconciliation layer atop the event-sourced aggregate, thereby mitigating dual-write anomalies during the migration window while preserving backward compatibility with the legacy projection contract.

**You:** `/bro`

**Assistant:**

> Ok so basically: we added a safety layer that makes sure old and new data don't get out of sync while we're switching systems. Nothing breaks for anything still using the old system. That's it.

## The rules baked in

| Rule | What it means |
|---|---|
| 🔄 **Re-explain, don't re-answer** | Never answers a new question, never adds info, never calls tools |
| 📏 **Simpler, not shorter** | Clarity over word count — take the space real clarity needs |
| 📌 **Facts survive verbatim** | Every path, command, filename, number, URL stays *exactly* the same |
| 🤙 **Light bro flavor** | Casual and direct, not a meme |
| 🌐 **Same language** | PT-BR in → PT-BR out. English stays English |
| 🧹 **Flatten structure** | Headers and tables become plain sentences |

## File layout

```
bro-skill/
├── SKILL.md     # the entire skill — one file, that's the beauty
├── install.sh   # detects your agent CLIs and drops /bro into each
├── README.md    # you are here
└── LICENSE      # MIT
```

## Contributing

It's a 30-line prompt file. If you have a genuinely better phrasing, open a PR — keep the facts-verbatim rule sacred.

## License

[MIT](LICENSE)
