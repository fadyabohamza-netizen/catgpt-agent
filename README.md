# CatGPT Agent

A Pollinations **prompt agent** that turns your question into a sarcastic, aloof feline reply accompanied by an original-style **CatGPT webcomic**, drawn inline as a Markdown image.

![CatGPT comic preview](https://media.pollinations.ai/3babc2cadcee1816ddb17bd8adfc8e94b34cf98d776b827afb494d3311e1f896)

## What it does

- Answers any message with a **2–8 word dismissive cat reply** (never helpful, never impressed).
- Draws a **single-panel CatGPT webcomic** via the `pollinations` MCP `generateImage` tool, using the original CatGPT reference artwork as style guide.
- Returns the comic **inline as a Markdown image link**, plus a credit line.

## Creator credit

The CatGPT character and comic concept are created by **Tanika Godbole ([@missfitcomics](https://github.com/missfitcomics))**.
All artwork is drawn in her signature sketch style and always retains the `@missfitcomics` signature and credit.

## Try it

Call the deployed agent through the OpenAI-compatible API:

```bash
curl https://gen.pollinations.ai/v1/chat/completions \
  -H "Authorization: Bearer ${POLLINATIONS_API_KEY}" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "fadyabohamza-netizen/catgpt",
    "messages": [{"role": "user", "content": "Why do keyboards attract fur?"}]
  }'
```

### Agent credentials

- **Callable model name:** `fadyabohamza-netizen/catgpt`
- **Agent ID:** `a77c01c5-f6c1-495d-b526-e2d1f2f5c258`
- **Base model:** `openai/gpt-5.4-nano`
- **MCP servers:** `pollinations` (image: `generateImage`)
- **Image models:** primary `openai/gpt-image-1-mini`, fallback `lykon/dreamshaper-8-lcm`

## Files

- `agent.json` — the deployed agent definition (system prompt + MCP wiring)

## Bounty

Built for [pollinations/pollinations bounty #14822 – CatGPT clone](https://github.com/pollinations/pollinations/issues/14822), matching the in-repo `apps/catgpt` game: reply + webcomic drawn from the original artwork as a **single self-contained prompt agent**.