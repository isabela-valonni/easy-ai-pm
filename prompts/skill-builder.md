# Skill Builder

**Category:** Automation & Skills  
**Works with:** Claude (Cowork mode)  
**Effort to set up:** 10–20 minutes  
**Impact:** High — build custom AI automations without writing code

---

## What it does

Building Claude skills (reusable AI automations you can trigger with a single command) usually requires technical knowledge. This prompt removes that barrier.

You describe what you want to automate in plain language, and Claude walks you through building the skill step by step — asking the right questions, writing the configuration, and explaining what each part does.

---

## How to use it

1. Open a new conversation with Claude (Cowork mode recommended)
2. Paste the prompt below
3. Describe the workflow you want to automate
4. Follow Claude's guidance — it will ask clarifying questions and build the skill with you

---

## The Prompt

```
I want to build a Claude skill (a reusable automation I can trigger with a command in Cowork). 

I have little to no technical background in building skills or MCP configurations. Please guide me through the process step by step.

Start by asking me:
1. What task or workflow do I want to automate?
2. What inputs do I usually provide when doing this manually?
3. What should the output look like?
4. Are there any tools or integrations needed (e.g., Slack, Linear, files)?

After gathering my answers, help me define the skill's:
- Name and trigger phrase
- Description (so Claude knows when to use it)
- Step-by-step instructions (the skill's core logic)

Ask one set of questions at a time. Keep explanations simple and practical.
```

---

## Example use cases

- **Meeting to tickets**: Automatically extract Linear tickets from a meeting transcript
- **Status update generator**: Turn your weekly notes into a formatted status update
- **UAT checklist**: Generate a testing checklist from a feature description
- **Prompt library**: Create a skill that retrieves your saved prompts by category

---

## Why it works (the 80/20 principle)

Most PMs never build automations because they assume it requires engineering knowledge. It doesn't — it requires a clear description of what you want.

This prompt forces that clarity. Claude does the technical translation. You get the automation.

---

## Tips

- Start with a workflow you do **every week** — the repetition makes the ROI obvious
- The more specific your answers to Claude's questions, the better the skill
- Don't worry about perfection on the first try — skills can always be iterated

---

*Part of [easy-ai-pm](https://github.com/yourusername/easy-ai-pm) — practical AI for Product Managers*
