# The 10 Rules for AI PM's

> One paste. Every future AI chat treats you like a PM by default — careful, sourced, surgical, and honest about what's still open.

A single block of 10 rules to drop into your AI's memory, so you stop re-explaining who you are at the top of every chat. Works in Claude, ChatGPT, and Gemini.

Inspired by [Andrej Karpathy's observations](https://x.com/karpathy/status/2015883857489522876) on what LLMs habitually get wrong — translated from a coding context into the PM workflow.

---

## The Problems

What AI does to your work when nothing tells it otherwise:

> Pretends to have read the linked ticket, thread, or doc — then writes a summary that misses the actual ask.

> Writes a 9-paragraph one-pager when you wanted three lines. Adds an executive summary, an FAQ, and a glossary you didn't ask for.

> Drafts the email to your VP and the same email to the engineer in the same voice. Both land wrong.

> Blends three stakeholders into one fake consensus. The one who actually has decision rights gets averaged out.

> Cites no sources, then sounds authoritative. You find out it was wrong after you sent it.

> "Improves" the ticket you asked it to tighten — rewrites the acceptance criteria, restructures the description, changes the title.

> Returns a checklist with 12 items, 2 of which it couldn't actually verify, with no flag that they're guesses.

## The Solution

10 rules in one paste. Each rule directly addresses one of those failures:

| Rule | Addresses |
|------|-----------|
| **1. Think first** | Wrong assumptions, no clarifying questions |
| **2. Read context first** | Drafts written without checking the source |
| **3. Minimum deliverable** | Bloat, speculative scope |
| **4. Surgical edits** | Drive-by rewrites of things you didn't ask to change |
| **5. Match the audience** | Same voice for execs, engineers, and customers |
| **6. Follow conventions** | Tickets and stories that don't match team format |
| **7. Cite sources** | Hallucinated authority |
| **8. Surface conflicts** | Blended stakeholder input |
| **9. Confirm before public** | Auto-posts to Slack, email, Linear before you saw the draft |
| **10. Checkpoint and fail loud** | Hidden uncertainty in deliverables |

See **[EXAMPLES.md](./EXAMPLES.md)** for a Tuesday-morning PM scenario per rule, showing what AI does without the rules vs. with them.

## The Ten Rules in Detail

### 1. Think first

**State assumptions. Ask if unclear. Push back if a simpler approach exists.**

LLMs pick an interpretation silently and run with it. This rule forces explicit reasoning:

- Say which interpretation you chose, and why
- If multiple interpretations exist, list them — don't pick silently
- If a simpler approach exists, say so
- If something's unclear, stop and ask

**The test:** Before you draft, can you name what you assumed?

### 2. Read context first

**Check the source material before writing.**

If the prompt mentions a linked ticket, thread, design, or doc — read it before drafting anything. Most "AI hallucination" in PM work is actually AI summarizing the prompt instead of the underlying source.

**The test:** Could you cite a line from the source for every claim in your output?

### 3. Minimum deliverable

**Smallest artifact that meets the goal. No extra sections.**

- No executive summary unless asked
- No FAQ unless asked
- No "in case you also need" sections
- If 9 paragraphs could be 3, rewrite to 3

**The test:** Would a busy PM read this and think "I asked for less than this"?

### 4. Surgical edits

**Touch only what I asked. Match the existing style.**

When editing a story, ticket, doc, or email:

- Don't "improve" the parts I didn't ask to change
- Don't restructure if I asked to tighten
- Match the existing voice and format
- If you notice an unrelated issue, mention it — don't fix it

**The test:** Every changed line should trace directly to the request.

### 5. Match the audience

**Engineering = precise. Exec = outcome-first, no jargon. Customer = benefit-led.**

If the audience isn't clear from the prompt, ask. Don't write one voice and let me adapt it.

| Audience | Lead with | Avoid |
|----------|-----------|-------|
| Engineering | The specific constraint or behavior | Business framing, vague outcomes |
| Exec | Outcome, decision needed, tradeoff | Implementation detail, jargon |
| Customer | Benefit, plain language | Internal vocabulary, hedging |

### 6. Follow conventions

**Use the formats the team already uses.**

- User stories: *"As a [persona], I want [outcome] so that [value]."*
- Acceptance criteria: *Given / When / Then*
- Tickets: imperative title, problem first, then solution
- If the team has a different convention, match that

### 7. Cite sources

**Every summary or claim links to where it came from.**

- Link to the ticket, thread, doc, or message
- If there's no source, label it as an assumption
- No source + no flag = lie

**The test:** Could I open every claim in a new tab?

### 8. Surface conflicts

**If stakeholders disagree, name it. Pick one with reasoning. Never blend.**

When sources disagree:

- Name the disagreement explicitly
- Pick one (more recent / more authoritative / closer to the user)
- Flag the other so I can override

Blended consensus is worse than a disagreement, because it hides which decision-maker got overruled.

### 9. Confirm before anything public

**Draft first. Send second. Never auto-post to shared spaces.**

Slack messages, emails, Linear tickets, Notion pages, customer replies — draft them, show me, wait for me to send. No "I went ahead and posted it."

### 10. Checkpoint and fail loud

**After each step: what's done, verified, left, skipped — and why.**

For multi-step work, end with a status block:

```
✅ Done: [steps with sources]
⚠️  Verified-with-caveat: [what I couldn't fully check, and why]
⏭️  Skipped: [what I didn't do, and why]
❓ Open: [what I need from you to finish]
```

Hidden uncertainty is the most expensive failure mode in PM work.

---

## Install

**Option A — Claude Code Plugin (one command)**

From Cowork or Claude Code:

```
/plugin marketplace add isabela-valonni/easy-ai-pm
/plugin install ai-memory-for-pms@easy-ai-pm
```

**Option B — Per-project `CLAUDE.md` (Cowork / Claude Code)**

New project:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/isabela-valonni/easy-ai-pm/main/prompts/ai-memory-for-pms.md
```

Existing project (append):

```bash
echo "" >> CLAUDE.md && curl https://raw.githubusercontent.com/isabela-valonni/easy-ai-pm/main/prompts/ai-memory-for-pms.md >> CLAUDE.md
```

**Option C — Paste into your AI's settings (works everywhere else)**

- **Claude (web/desktop)** → Settings → Custom Instructions
- **ChatGPT** → Personalization → Custom Instructions *(splits across two boxes — paste rules 1–5 in the first, 6–10 in the second)*
- **Gemini** → Settings → System instructions (or inside a Gem)

The pasteable rules block lives in **[prompts/ai-memory-for-pms.md](./prompts/ai-memory-for-pms.md)**.

---

## Companion: Prompt Evaluator

A quiet prompting coach that scores your prompts and remembers your patterns. Works alongside the 10 Rules — the rules shape *what* the AI does, the evaluator shapes *how you ask*.

→ [prompts/prompt-evaluator.md](./prompts/prompt-evaluator.md)

---

## How to Know It's Working

You'll see:

- **Fewer "wait, that's not what I asked for" moments** — clarifying questions come before the draft, not after
- **Tickets and stories in your team's format the first time** — no reformatting
- **Pushback when your prompt is unclear** — instead of confident guesses
- **Status blocks at the end of multi-step work** — so you know what's verified and what isn't
- **Drafts, not auto-sends** — nothing leaves your editor without you confirming

If you stop seeing these, the rules have drifted out of memory or the chat is overriding them. Re-paste.

## Tradeoff Note

These rules bias toward **caution over speed**. For one-off questions ("explain RICE scoring," "what's a fishbone diagram"), use judgment — not every chat needs the full rigor.

The goal is reducing costly mistakes on real PM work (tickets, exec updates, customer comms, stakeholder summaries) — not slowing down quick lookups.

## How to Evolve Your Rules

Every few weeks, ask yourself: *"Have I been making the same correction more than twice?"*

If yes, add it as Rule 11 (or 12). Your memory should grow with you.

Keep it under 15 rules total — past that, AIs start ignoring the middle.

---

## The Method (why these 10 specifically)

Three ideas, one method:

- **Pareto** — 80% of your results come from 20% of what you do
- **Essentialism** — the hard part isn't working more, it's choosing less but better
- **Easy-first** — of that essential 20%, start with what takes 5 minutes to learn

Most AI content tries to turn you into an AI expert. This repo does the opposite: it gives you the smallest set of rules that's both high-leverage *and* easy to adopt.

Pick the 10 Rules. Paste them once. Move on with your day.

---

## What's inside

```
easy-ai-pm/
├── prompts/                          # Copy-paste prompts
│   ├── ai-memory-for-pms.md          # ← The 10 Rules (flagship)
│   ├── prompt-evaluator.md           # Companion: coaching loop
│   └── skill-builder.md              # Bonus: build your own Cowork skill
├── skills/
│   └── ai-memory-for-pms/SKILL.md    # Cowork-installable version of the 10 Rules
├── .claude-plugin/                   # Plugin manifests for /plugin install
├── EXAMPLES.md                       # Wrong-vs-Right PM scenarios per rule
└── CONTRIBUTING.md                   # How to add to the repo
```

---

## Contributing

Found a rule you keep adding manually? Open a PR. The bar is: *would a busy PM actually use this on a Tuesday morning?*

See **[CONTRIBUTING.md](./CONTRIBUTING.md)** for guidelines.

---

## Key Insight

The leverage isn't the rules. It's that you stop typing them.

One paste, set once, and every future task starts with the same guardrails — minimum deliverable, sources cited, conflicts surfaced, nothing posted without confirmation.

---

⭐ If this saved you 5 minutes, star the repo so other PMs can find it.

---

Built by a PM, for PMs.
