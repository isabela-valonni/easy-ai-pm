# Install Test Plan — easy-ai-pm & prompt-evaluator

Run this in a **fresh Cowork or Claude Code session**, ideally in a **new/empty project folder** that has no `CLAUDE.md` and isn't your usual workspace. A clean session is the test environment — it shows what a brand-new user actually experiences.

> **One caveat before you start:** your account has a global prompting-coach config (in user preferences / global `CLAUDE.md`) that fires the evaluator in *every* session. That means the prompt-evaluator "does it auto-fire?" test below is partly contaminated — the coach may fire because of your global setup, not the plugin. Where this matters, the test says so. The 10 Rules tests are not affected.

---

## Repo 1 — easy-ai-pm (The 10 Rules)

### Test 1A — Plugin install

Paste, one at a time:

```
/plugin marketplace add isabela-valonni/easy-ai-pm
```
```
/plugin install ai-memory-for-pms@easy-ai-pm
```

**What you should see:** a confirmation that the marketplace was added, then that the plugin installed. No red errors, no "not found", no "invalid manifest".

**Pass:** both commands confirm cleanly.
**Fail:** any error — copy the full text.

### Test 1B — Does the behavior actually show up?

In the same session, paste this real PM task:

```
Summarize this Slack thread for the engineer joining Monday: [paste any 5-6 line back-and-forth, or make one up]
```

**What you should see (the rules working):** it asks a clarifying question if the ask is ambiguous, keeps the summary minimal, doesn't invent sources, and ends without auto-posting anywhere.

**Pass:** output feels careful and scoped, not bloated or over-confident.
**Fail:** it dumps a 9-paragraph summary, invents details, or offers to post to Slack on its own.

### Test 1C — Curl path (the no-plugin route)

In a terminal, in an empty folder:

```
curl -o CLAUDE.md https://raw.githubusercontent.com/isabela-valonni/easy-ai-pm/main/prompts/ai-memory-for-pms.md
```

**What you should see:** a `CLAUDE.md` file appears containing the 10 Rules block.

**Pass:** file downloads, content is the rules.
**Fail:** 404, empty file, or HTML instead of the rules.

### Test 1D — Paste-into-settings (optional)

Open `prompts/ai-memory-for-pms.md`, copy the rules block, paste into Claude/ChatGPT/Gemini custom instructions. Start a new chat, give it a PM task.

**Pass:** same careful behavior as Test 1B, in that tool.

---

## Repo 2 — prompt-evaluator

### Test 2A — Plugin install

Paste, one at a time:

```
/plugin marketplace add isabela-valonni/prompt-evaluator
```
```
/plugin install prompt-evaluator@prompt-evaluator
```

**What you should see:** marketplace added, plugin installed, no errors.

**Pass:** both confirm cleanly.
**Fail:** any error — copy the text.

### Test 2B — Does the evaluator fire on the first prompt? (the key question)

This is the test we built the whole "honest framing" around. **To test it cleanly you'd need a session WITHOUT your global coach config** — otherwise you can't tell whether the plugin fired or your global setup did.

If you can test on a clean account/session: start a brand-new chat and paste any normal first prompt, e.g.:

```
Write a short update about our Q3 launch slipping two weeks.
```

**What you should see if the plugin works:** a `PROMPTING FEEDBACK` block (score /10, what worked, to sharpen) appears, rendered on separate lines, then it answers normally.

**Pass:** the feedback block fires unprompted on the first message, four lines, correct format.
**Partial/unknown:** it fires, but you can't be sure it wasn't your global config (expected on your main account).
**Fail:** no feedback block appears at all in a session where your global config is off.

### Test 2C — Curl path

```
curl -o CLAUDE.md https://raw.githubusercontent.com/isabela-valonni/prompt-evaluator/main/PROMPT.md
```

**Pass:** `CLAUDE.md` appears with the evaluator block.

### Test 2D — Rendering check (no install needed)

Open the live README in a browser:
`https://github.com/isabela-valonni/prompt-evaluator#the-format`

**What you should see:** the `PROMPTING FEEDBACK` example renders on **four separate lines**, not one run-on line.

**Pass:** four lines.
**Fail:** collapsed to one line (means the rendering fix didn't take).

---

## Results — fill in as you go

| Test | Pass / Fail / Notes |
|------|---------------------|
| 1A — easy-ai-pm plugin install | |
| 1B — 10 Rules behavior | |
| 1C — easy-ai-pm curl | |
| 1D — easy-ai-pm paste-in | |
| 2A — prompt-evaluator plugin install | |
| 2B — evaluator auto-fires | |
| 2C — prompt-evaluator curl | |
| 2D — README rendering | |

---

## If something fails

Bring the failing test number and the exact error/output back to a chat. Most likely fixes:
- **Marketplace not found** → repo private, or wrong owner/name in the command
- **Invalid manifest** → JSON typo in `plugin.json` / `marketplace.json`
- **Skill not found at path** → `skills` path in `plugin.json` doesn't match the folder
- **Evaluator doesn't fire** → expected limitation of the skill model for always-on behavior; fall back to the CLAUDE.md install (Option B)
