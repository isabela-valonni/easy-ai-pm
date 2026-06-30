# The 10 Rules for AI PM's

> One paste. Every future AI chat treats you like a PM by default — careful, sourced, surgical, and honest about what's still open.

A single block of 10 rules to drop into your AI's memory, so you stop re-explaining who you are at the top of every chat. Works in Claude, ChatGPT, and Gemini.

Inspired by [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on what LLMs habitually get wrong — translated from a coding context into the PM workflow.

---

## The Problem

What AI does to your work when nothing tells it otherwise:

> Pretends to have read the linked ticket, then writes a summary that misses the actual ask.

> Writes a 9-paragraph one-pager when you wanted three lines.

> Drafts the email to your VP and to the engineer in the same voice. Both land wrong.

> Blends three stakeholders into one fake consensus. The decision-maker gets averaged out.

> Cites no sources, then sounds authoritative. You find out it was wrong after you sent it.

> "Improves" the ticket you asked it to tighten, rewriting acceptance criteria you never touched.

## The Solution

10 rules, one paste. Each fixes one failure:

| Rule | Fixes |
|------|-------|
| 1. Think first | Wrong assumptions, no clarifying questions |
| 2. Read context first | Drafts written without checking the source |
| 3. Minimum deliverable | Bloat, speculative scope |
| 4. Surgical edits | Drive-by rewrites of things you didn't ask to change |
| 5. Match the audience | Same voice for execs, engineers, and customers |
| 6. Follow conventions | Tickets and stories that don't match team format |
| 7. Cite sources | Hallucinated authority |
| 8. Surface conflicts | Blended stakeholder input |
| 9. Confirm before public | Auto-posts before you saw the draft |
| 10. Checkpoint and fail loud | Hidden uncertainty in deliverables |

See **[EXAMPLES.md](./EXAMPLES.md)** for a Tuesday-morning scenario per rule — what AI does without each rule, and with it.

---

## Install

The rules work best as **always-on context**: read every session, with nothing to trigger. Two ways below do that. A plugin is offered last, for people who prefer `/plugin`.

**1. Paste into your AI's settings (works everywhere)**

Copy the block from **[prompts/ai-memory-for-pms.md](./prompts/ai-memory-for-pms.md)** into:

- Claude (web/desktop) → Settings → Custom Instructions
- ChatGPT → Personalization → Custom Instructions (paste the whole block into the "How would you like ChatGPT to respond?" box; it fits)
- Gemini → Settings → System instructions (or inside a Gem)

**2. Claude Code / Cowork (per-project `CLAUDE.md`)**

Append the rules to your project's `CLAUDE.md`. Run it once so they aren't duplicated:

```bash
echo "" >> CLAUDE.md && curl -s https://raw.githubusercontent.com/isabela-valonni/easy-ai-pm/main/prompts/claude-md-rules.md >> CLAUDE.md
```

New project with no `CLAUDE.md` yet? Swap `>> CLAUDE.md` for `-o CLAUDE.md` to create one.

Prefer a plugin? Run `/plugin marketplace add isabela-valonni/easy-ai-pm` then `/plugin install ai-memory-for-pms@easy-ai-pm`. (The plugin name ends in `-s`; if the marketplace add hits an SSH error, use the HTTPS URL `https://github.com/isabela-valonni/easy-ai-pm.git`.) The plugin ships the rules as a skill the AI loads when it judges them relevant; for guardrails on *every* task, options 1 and 2 are more reliable.

---

## How to Know It's Working

Clarifying questions come before the draft, not after. Tickets and stories arrive in your team's format the first time. The AI pushes back when a prompt is unclear instead of guessing. Multi-step work ends with a status block. Drafts wait for your "send it" instead of auto-posting. If these fade, the rules have drifted out of memory — re-paste.

## Tradeoff

These rules bias toward caution over speed. For one-off questions ("explain RICE scoring"), use judgment. Not every chat needs the full rigor. The goal is fewer costly mistakes on real PM work, not slower lookups.

## How to evolve them

Every few weeks, ask: *"Have I made the same correction more than twice?"* If yes, add it as Rule 11. Keep it under 15 total. Past that, AIs start ignoring the middle.

---

## Why these 10 (the method)

Three ideas, one method. **Pareto** — 80% of your results come from 20% of what you do. **Essentialism** — the hard part isn't working more, it's choosing less but better. **Easy-first** — of that essential 20%, start with what takes 5 minutes to learn.

Most AI content tries to turn you into an expert. This does the opposite — the smallest set of rules that's both high-leverage and easy to adopt. Pick the 10. Paste once. Move on with your day.

---

## Related

- **[EXAMPLES.md](./EXAMPLES.md)** — each rule in action, wrong vs. right.
- **[prompt-evaluator](https://github.com/isabela-valonni/prompt-evaluator)** — companion repo. The 10 Rules shape *what* the AI does; the evaluator shapes *how you ask*. They compose.
- **[CONTRIBUTING.md](./CONTRIBUTING.md)** — found a rule you keep adding by hand? Open a PR.

---

⭐ If this saved you 5 minutes, star the repo so other PMs can find it.

Built by a PM, for PMs.
