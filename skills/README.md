# Skills

Skills are reusable automations you can install into Claude Cowork and trigger with a single command. Unlike prompts (which you paste and forget), skills are purpose-built workflows that Claude executes on demand.

**Works with:** Claude Cowork mode only  
**Effort to install:** 5–15 minutes per skill

---

## What's a skill?

A skill is a set of instructions that tells Claude how to handle a specific repeatable task — step by step, every time, without you having to re-explain it.

Once installed, you just say "run [skill name]" (or the trigger phrase), and Claude does the rest.

**Examples of what skills can do:**
- Turn a meeting transcript into Linear tickets automatically
- Generate a weekly status update from your notes
- Build a UAT checklist from a feature description
- Score and improve every prompt you write

---

## How to install a skill

### Step 1 — Open the skill folder

Each skill lives in its own folder inside `skills/`. Open the folder for the skill you want to install.

### Step 2 — Read the skill file

Inside the folder you'll find a `SKILL.md` (or similarly named file). Read it — it contains the skill's instructions and any configuration notes.

### Step 3 — Open Claude Cowork

Open the Claude desktop app and make sure you're in **Cowork mode**.

### Step 4 — Create a new skill

In Cowork, navigate to **Skills** (in the sidebar or settings). Click **New Skill** or **Add Skill**.

### Step 5 — Fill in the skill details

Copy the fields from the skill file into the form:

| Field | What to paste |
|-------|---------------|
| **Name** | The skill's name (e.g., `Meeting to Tickets`) |
| **Trigger phrase** | The phrase you'll use to activate it (e.g., "extract tickets") |
| **Description** | What the skill does — Claude uses this to decide when to suggest it |
| **Instructions** | The full step-by-step logic — this is the core of the skill |

### Step 6 — Save and test

Save the skill. Then open a new conversation and use the trigger phrase to activate it.

If something doesn't work as expected, check the skill's `TIPS.md` (if present) or open an issue in this repo.

---

## Available skills

| Skill | What it does | Effort |
|-------|-------------|--------|
| *(more coming soon)* | | |

---

## Tips

- **Start with one skill** — pick the workflow you repeat most often, install that one, and use it for a week before adding more
- **Trigger phrases matter** — make them natural. You should be able to say it without thinking
- **Skills can be edited** — if the output isn't quite right, tweak the instructions. They're just text

---

*Part of [easy-ai-pm](https://github.com/yourusername/easy-ai-pm) — practical AI for Product Managers*
