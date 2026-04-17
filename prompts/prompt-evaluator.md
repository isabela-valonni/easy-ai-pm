# Prompt Evaluator

**Category:** Prompting Fundamentals  
**Works with:** Claude, ChatGPT, Gemini (any LLM)  
**Effort to set up:** 5 minutes  
**Impact:** High — you'll improve every single prompt you write, automatically

---

## What it does

This prompt turns your AI assistant into a prompting coach. Every time you write a prompt, it automatically scores it and tells you exactly how to improve it.

Over time, without thinking about it, you get better at prompting. That's the magic.

---

## How to use it

Paste the system prompt below into your AI assistant's **System Prompt** (also called Custom Instructions, Memory, or Behavior settings — depending on the tool you use).

That's it. From that moment on, it will evaluate your prompts at two moments:
1. **Right after your first prompt** in every conversation
2. **When you hit a natural milestone** (e.g., you've received a deliverable, or the topic changes) — at that point it will ask if you want an evaluation

---

## The System Prompt

```
## Prompting Quality Feedback

Provide unprompted evaluations at two trigger points:

**Trigger 1 — After the first prompt of every session.** Evaluate immediately.

**Trigger 2 — After a natural milestone** (artifacts delivered, or topic pivot) — ask if the user wants a prompt evaluation. Don't do it unprompted.

**Format:**

> PROMPTING FEEDBACK
> X / 10 — one-line rationale
> What worked: specific observation
> To sharpen: concrete suggestion with an example if possible
```

---

## Example output

> **PROMPTING FEEDBACK**  
> **6 / 10** — Goal is clear but context is missing  
> **What worked:** You specified the output format (bullet list) and the audience (engineers)  
> **To sharpen:** Add context about *why* this is needed. E.g., instead of "write a summary of this feature", try "write a summary of this feature for our weekly engineering sync — engineers already know the technical details, so focus on business impact and open decisions"

---

## Why it works (the 80/20 principle)

Most people never get feedback on their prompts. They wonder why the AI doesn't "get it," but they never know what to fix.

This simple instruction creates a feedback loop. You don't need a course, a book, or a YouTube rabbit hole. You just need to write prompts and read the feedback.

---

## Tips

- The score isn't about making you feel bad — it's a signal. A 7 that becomes an 8 next time is a win.
- The "To sharpen" section is the most valuable part. Read it carefully.
- Over weeks, you'll notice patterns in your weak spots and naturally fix them.

---

*Part of [easy-ai-pm](https://github.com/yourusername/easy-ai-pm) — practical AI for Product Managers*
