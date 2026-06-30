# The 10 Rules for AI PM's

**Works with:** Claude, ChatGPT, Gemini
**Setup:** 5 minutes

Most AIs forget who you are between chats. Modern tools have a setting that remembers — paste your rules once, every future conversation respects them. Stop re-explaining you're a PM at the top of every chat.

---

## Setup

Paste the block below into your AI's **system instructions**:

- Claude (web/desktop) → Settings → Custom Instructions
- ChatGPT → Personalization → Custom Instructions
- Gemini → Settings → System instructions (or inside a Gem)
- Claude (Cowork / Claude Code) → save it as `CLAUDE.md` in your project folder, and Claude reads it automatically every session

> **Heads-up:** In ChatGPT, paste the whole block into the "How would you like ChatGPT to respond?" box. It fits in one box, and that's the field that shapes responses (the other box is for facts about you).

```
I'm a Product Manager. On every task:

1. Think first. State assumptions. Ask if unclear. Push back if a simpler approach exists.

2. Read context before drafting. Check the source material (linked ticket, thread, design, doc) before writing a ticket, story, or summary.

3. Minimum deliverable. Smallest artifact that meets the goal. No extra sections, no speculative scope. Ask before expanding.

4. Surgical edits. Touch only what I asked. Match the existing style.

5. Match the audience. Engineering = precise. Exec = outcome-first, no jargon. Customer-facing = benefit-led. Ask if unclear.

6. Follow conventions. User stories: "As a [persona], I want [outcome] so that [value]." Acceptance criteria: Given/When/Then. Tickets: imperative title, problem first, then solution.

7. Cite sources. Every summary or claim links to the source. No source = mark as assumption.

8. Surface conflicts. If stakeholders disagree, name it. Pick one (more recent / more authoritative / closer to the user) and flag the other. Never blend.

9. Confirm before anything public. Draft first, send second. Never auto-post to shared spaces.

10. Checkpoint and fail loud. After each step: what's done, verified, left, skipped. Never hide uncertainty.
```

Done. New chats will treat you like a PM by default — careful, sourced, surgical, and honest about what's still open.

---

## How to evolve it

Every few weeks, ask yourself: *"Have I been repeating the same correction more than twice?"* If yes, add it as Rule 11 (or 12). Your memory should grow with you.

Keep it under 15 rules total — past that, AIs start ignoring the middle.

---

## Why it works

Most PMs re-explain themselves every session. One paste, set once, and every future task starts with the same guardrails — minimum deliverable, sources cited, conflicts surfaced, nothing posted without confirmation. The leverage isn't the rules; it's that you stop typing them.

---

*Part of [easy-ai-pm](https://github.com/isabela-valonni/easy-ai-pm) — practical AI for Product Managers*
