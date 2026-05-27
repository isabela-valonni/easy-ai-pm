# Contributing to easy-ai-pm

Thanks for wanting to add to this. The goal is simple: a short list of things that actually work, for PMs who don't have time to experiment.

---

## The bar

Before submitting anything, ask yourself: **would a busy PM actually use this on a Tuesday morning?**

That means:
- **Usable in 5 minutes or less** — no setup, no configuration, no technical background needed
- **High signal-to-effort ratio** — the output should be noticeably better than what you'd get without it
- **One clear job** — it does one thing well, not five things adequately

If it requires writing code, installing a tool, or reading a 10-minute explainer first, it doesn't belong here.

---

## What to contribute

Two types of contributions:

### Prompts (`prompts/`)
Copy-paste prompts that work with any LLM. The core of the repo — low friction, high impact.

### Skills (`skills/`)
Reusable Claude Cowork / Claude Code skills. More setup than a prompt, but installable with one `/plugin install` command.

---

## File structure

Every contribution lives in its own file, named in lowercase with hyphens:

```
prompts/user-story-generator.md
skills/weekly-status-update/SKILL.md
```

---

## Prompt file template

Use this structure for every new prompt file:

```markdown
# [Name]

**Category:** [e.g., Prioritization / Discovery / Stakeholder Comms]
**Works with:** [e.g., Claude, ChatGPT, Gemini]
**Effort to set up:** [e.g., 2 minutes]
**Impact:** [High / Medium — one-line explanation]

---

## What it does

[One short paragraph. What problem does this solve? What does the PM get out of it?]

---

## How to use it

[Step-by-step instructions. Be specific about where to paste it.]

---

## The Prompt

\`\`\`
[The actual prompt goes here]
\`\`\`

---

## Example output

[Optional but encouraged — show what good output looks like]

---

## Why it works (the 80/20 principle)

[One short paragraph connecting this to the Pareto idea — why is this the 20% that matters?]

---

## Tips

- [Optional tips for getting the most out of it]

---

*Part of [easy-ai-pm](https://github.com/isabela-valonni/easy-ai-pm) — practical AI for Product Managers*
```

---

## Naming conventions

| Type | Convention | Example |
|------|------------|---------|
| Prompt files | lowercase, hyphenated | `user-story-generator.md` |
| Skill folders | lowercase, hyphenated | `weekly-status-update/` |
| Categories | Title Case | `Stakeholder Comms` |

---

## How to submit

1. Fork the repo
2. Create a branch: `git checkout -b add/your-prompt-name`
3. Add your file following the template above
4. Open a PR with a one-line description: *what it does and why it's worth adding*
5. The PR description should answer: **would a busy PM use this on a Tuesday morning? Why?**

---

## What gets rejected

- Prompts that require more than 5 minutes to set up
- Anything that needs code or a technical background
- Prompts that do too many things at once
- Generic "productivity hacks" with no PM-specific angle
- Anything that's already well-covered by an existing prompt

---

*When in doubt, open an issue first and describe what you're thinking. Better to align early than to build something that doesn't fit.*
