# Prompt Evaluator

**Works with:** Claude, ChatGPT, Gemini
**Setup:** 2 minutes

Turn your AI into a quiet prompting coach. It scores your prompts, names one thing to sharpen, and remembers your patterns — so the feedback gets smarter without you studying anything.

---

## Setup

Paste the block below into your AI's **system instructions**:
- Claude (Cowork / Claude Code) → add it to your `CLAUDE.md` file — this scopes it to a project and carries across sessions automatically
- Claude (web/desktop) → Settings → Custom Instructions
- ChatGPT → Personalization → Custom Instructions
- Gemini → Settings → System instructions

```
## Prompting Quality Feedback

Evaluate my prompts at two moments:
1. After my first prompt of every session — evaluate immediately.
2. At a natural milestone (delivery or topic pivot) — ask me first.

Format:
> PROMPTING FEEDBACK
> X/10 — one-line rationale
> What worked: one specific observation
> To sharpen: one concrete suggestion, with an example

After each evaluation, update a memory file called `user_prompting_profile.md`
with my recurring strengths and weak spots, so the feedback gets more targeted
every session instead of starting fresh.
```

Done. New chats will start coaching you automatically.

---

## What you'll see

> **PROMPTING FEEDBACK**
> **6 / 10** — Goal is clear, context is thin.
> **What worked:** Named the audience (engineers) and the format (bullets).
> **To sharpen:** Add *why* it's needed. Try: "…for the weekly eng sync — they know the tech, so focus on business impact."

---

## Why it works

Most people never get feedback on how they prompt. One honest note per session — from something that remembers what you already fixed — compounds fast.

---

*Part of [easy-ai-pm](https://github.com/yourusername/easy-ai-pm) — practical AI for Product Managers*
