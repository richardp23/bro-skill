<div align="center">

# 🤙 /bro

**When the answer made you go "bro what" — type `/bro` and get it in plain language.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Hermes Agent Skill](https://img.shields.io/badge/Hermes-Agent%20Skill-blueviolet)](https://github.com/NousResearch/hermes-agent)
[![Format](https://img.shields.io/badge/format-SKILL.md-informational)](SKILL.md)

</div>

---

## What is this?

`/bro` is a tiny [Hermes Agent](https://github.com/NousResearch/hermes-agent) skill with one job: when the assistant's last reply was too dense, too jargon-heavy, or too formal, you type `/bro` and it re-explains **its own previous message** like a smart friend over a beer.

No new information. No new answers. Just the same thing, said in a way that's impossible to misunderstand.

## Why?

Because "let me rephrase that" shouldn't require typing a whole sentence. One word. Two characters of effort. Zero shame.

## How it works

1. Assistant gives you a dense, consultant-flavored wall of text.
2. You type `/bro`.
3. The skill instructs the assistant to **re-express** its last message — simpler, more casual, same facts.

The full behavior lives in [`SKILL.md`](SKILL.md). The rules baked in:

| Rule | What it means |
|---|---|
| 🔄 **Re-explain, don't re-answer** | Never answers a new question, never adds info, never calls tools |
| 📏 **Simpler, not shorter** | Clarity over word count — take the space real clarity needs |
| 📌 **Facts survive verbatim** | Every path, command, filename, number, URL stays *exactly* the same |
| 🤙 **Light bro flavor** | Casual and direct, not a meme |
| 🌐 **Same language** | PT-BR in → PT-BR out. English stays English |
| 🧹 **Flatten structure** | Headers and tables become plain sentences |

## Example

**Assistant:**

> The refactor introduces an idempotent reconciliation layer atop the event-sourced aggregate, thereby mitigating dual-write anomalies during the migration window while preserving backward compatibility with the legacy projection contract.

**You:** `/bro`

**Assistant:**

> Ok so basically: we added a safety layer that makes sure old and new data don't get out of sync while we're switching systems. Nothing breaks for anything still using the old system. That's it.

## Install

```bash
# Hermes Agent
mkdir -p ~/.hermes/skills/bro
curl -o ~/.hermes/skills/bro/SKILL.md \
  https://raw.githubusercontent.com/luchasarie/bro-skill/main/SKILL.md
```

Or just clone and copy:

```bash
git clone https://github.com/luchasarie/bro-skill.git
cp bro-skill/SKILL.md ~/.hermes/skills/bro/SKILL.md
```

Then restart Hermes (or let it hot-reload skills) and type `/bro` after any reply that made your eyes glaze over.

## File layout

```
bro-skill/
├── SKILL.md   # the entire skill — one file, that's the beauty
├── README.md  # you are here
└── LICENSE    # MIT
```

## Contributing

It's a 30-line prompt file. If you have a genuinely better phrasing, open a PR — keep the facts-verbatim rule sacred.

## License

[MIT](LICENSE) — Hermes Agent + Luka
