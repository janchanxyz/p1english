# 小一英文拼字 · p1english

Cute, colourful **Primary 1 English spelling game** for Hong Kong kids — mobile & iPad friendly.

**Live:** https://p1english.chanplanet.workers.dev/

## Features

- **每日 10 個字** — same words for everyone on the same Hong Kong calendar day (`Asia/Hong_Kong`)
- Each word hides **2–5 letters** (short words keep at least one letter visible)
- **8 hearts** · **繁體中文（香港）** · QWERTY · examples + exampleZh
- Gradient answer reveal · report-image (3/IP/day) · share card
- **Edge TTS** — word + example audio pre-generated with Microsoft `edge-tts` (`en-GB-SoniaNeural`) under `/audio/w/` and `/audio/e/` (no Cloudflare Workers AI at runtime)

## Vocabulary source (EDB honesty)

Hong Kong’s Education Bureau does **not** publish a separate Primary 1–only English wordlist. Official indicative targets are about **1,000 words by end of KS1** and **2,000 by end of primary (KS2)**. This app uses a **curated P1-appropriate pool** (~400 short spelling words, length 3–7) aligned with EDB KS1 themes (animals, food, school, body, colours, family, home, weather, transport). **Not an official EDB dump**.

References: [EDB primary vocabulary](https://www.edb.gov.hk/en/curriculum-development/kla/eng-edu/references-resources/resource%20pri_vocab.html) · [Enhancing Eng Vocab at Pri Level](https://www.edb.gov.hk/en/curriculum-development/kla/eng-edu/references-resources/Enhancing%20Eng%20Vocab%20at%20Pri%20Level.html)

## Develop / Deploy

```bash
npm install
python3 -m venv .venv && .venv/bin/pip install edge-tts
.venv/bin/python scripts/generate_static_tts.py
npm run build && npx wrangler deploy
```

Daily seed key: `p1english-daily-YYYY-MM-DD`.
