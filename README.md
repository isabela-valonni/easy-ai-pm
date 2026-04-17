# easy-ai-pm

**AI for PMs, without the overwhelm.** The 20% that's essential, easy, and delivers 80% of the results.

---

## Why this exists

You're a Product Manager. You've seen 200 LinkedIn posts about AI this week. You've bookmarked 12 newsletters, watched half a YouTube video, and you still don't know where to actually start.

Same. That's why this repo exists.

It's built on the **Pareto Principle**: roughly 80% of the results come from 20% of the causes. Applied to AI: a small set of well-chosen prompts, used consistently, will give you most of the productivity gains — without the rabbit hole.

You don't need to master AI. You need the 20% that matters.

Think of it as a PM friend who waded through all the noise and came back with a short list of "here's what actually matters, and here's how to use it today."

---

## The rules of this repo

- **5 minutes or it doesn't count.** Every prompt should be usable immediately, no setup.
- **No technical background needed.** If it requires code, it doesn't belong here.
- **One thing at a time.** Pick one, use it for a week, then come back for the next.

Everything here is part of the 20% — the handful of things that punch above their weight.

---

## Getting started

**No setup. No account. No configuration required.** All you need is access to Claude (or any other LLM).

### Using a prompt

1. **Pick one prompt** from the `prompts/` folder — start with the Prompt Evaluator if you're not sure where to begin
2. **Open the file** and copy the system prompt inside it
3. **Paste it into your AI assistant's system instructions**
   - Claude: Settings → Custom Instructions
   - ChatGPT: Settings → Custom Instructions
   - Gemini: Settings → System instructions
4. **Start a new conversation** — the instructions run silently in the background

That's it. You don't need to do anything else. Use your AI as you normally would.

### Installing a skill (Claude Cowork only)

If you want to go further and install a full automation from the `skills/` folder:

1. **Open the skill file** you want to install from `skills/`
2. **Follow the setup guide** inside — every skill includes step-by-step instructions
3. **Trigger it** with a single command in Claude Cowork

See [`skills/README.md`](./skills/README.md) for the full installation guide.

---

## Start here

### 1. The Prompt Evaluator
A prompt that quietly scores and improves *every prompt you write*. You don't need to study prompt engineering — it teaches you as you go, in the background.

→ [prompts/prompt-evaluator.md](./prompts/prompt-evaluator.md)

### 2. The Skill Builder
Want Claude to automate something for you, but don't know how to build a "skill"? Just describe what you want in plain English. This prompt walks you through the rest.

→ [prompts/skill-builder.md](./prompts/skill-builder.md)

---

## What's inside

```
easy-ai-pm/
├── prompts/     # Copy-paste prompts (start here)
├── skills/      # Claude skills you can install
└── agents/      # Ready-made agent setups
```

---

## The method

Three ideas, one method.

**Pareto:** 80% of your results come from 20% of what you do.
**Essentialism:** the hard part isn't working more, it's choosing less — but better.
**Easy-first:** of that essential 20%, start with what takes 5 minutes to learn.

Most AI content tries to turn you into an AI expert. This repo does the opposite: it gives you the smallest possible set of things that are both high-leverage *and* easy to adopt.

Pick one. Use it until it's a habit. Move on.

---

## Contributing

Found something simple that changed how you work? Open a PR. The bar is: *would a busy PM actually use this on a Tuesday morning?*

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for guidelines on what qualifies, how to structure your submission, and naming conventions.

---

Built by a PM, for PMs.
