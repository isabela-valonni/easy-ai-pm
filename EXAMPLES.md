# Examples

Tuesday-morning PM scenarios, one per rule. Each shows what AI does without the rules vs. with them.

These are the moments where the leverage shows up — not "improving your AI usage" in the abstract, but the specific drafts, tickets, and replies that would've gone out worse.

---

## 1. Think First

### Scenario: "Write the Q3 launch update."

**❌ Without the rules**

```
🎉 Exciting News — Q3 Launch Update!

We're thrilled to share that this quarter has been a milestone period for our
team. Our latest launch represents months of cross-functional collaboration,
and we're proud of the impact it's already making across the business.

[3 more paragraphs of generic enthusiasm, none of it grounded in your actual
launch, audience, or status]
```

Problems: AI assumed the launch has shipped. Assumed the audience wants a celebratory tone. Invented impact claims. Picked one interpretation of "update" silently.

**✅ With the rules**

```
Before I draft, two things to confirm:

1. Audience — exec readout, customer announcement, or team retrospective?
   The voice and what counts as "the update" change a lot between these.

2. Status — has the launch shipped, or is this a pre-announce / progress
   note? I'm seeing references in the doc to "GA targeted for Sept" but
   want to confirm before writing in past tense.

If you want me to draft something to keep moving while you answer: my
default would be a team-facing retrospective, assuming GA shipped. Say
"go with that" or correct me.
```

**The test:** Before drafting, did the AI name what it assumed?

---

## 2. Read Context First

### Scenario: "Draft a ticket from this Slack thread: [link]."

**❌ Without the rules**

AI reads the first message in the thread:

> "Hey, we should probably let users export their watchlists as CSV"

…and drafts a ticket for CSV export.

But the thread has 23 messages. By message 14, the team had pivoted to *"actually the real ask is shareable links, CSV is a workaround for a missing feature."* By message 19, the eng lead said *"CSV is a one-week ticket, shareable links is a six-week project — let's not conflate these."*

The drafted ticket is for the workaround, not the actual problem.

**✅ With the rules**

```
Before drafting, I read the full thread (23 messages). Quick summary of what
I found:

- Opening ask: CSV export for watchlists
- Pivot at msg 14 (Marina): the real ask is shareable links — CSV was a
  workaround for that
- Sizing at msg 19 (Tom): CSV ≈ 1 week, shareable links ≈ 6 weeks
- No resolution by end of thread — last message is Marina saying "let's
  decide async"

So before I draft: do you want one ticket (CSV as the immediate ask) or
two (CSV now, shareable links as a separate larger initiative)? The thread
didn't resolve this and writing one ticket would pick that for you silently.
```

**The test:** Could AI cite the message number of every claim it made?

---

## 3. Minimum Deliverable

### Scenario: "Write a one-pager on the new pricing change for the team."

**❌ Without the rules**

AI returns:

1. **Executive Summary** (2 paragraphs)
2. **Background** (3 paragraphs of context everyone already has)
3. **The Change** (4 paragraphs)
4. **Rationale** (3 paragraphs)
5. **Projected Impact** (a table with invented numbers)
6. **Rollout Plan** (a timeline with invented dates)
7. **Comms Plan** (sections for internal, customer, and sales)
8. **FAQ** (10 invented questions with invented answers)
9. **Glossary** (definitions of "ARR" and "MRR" because why not)
10. **Appendix**

Three pages. The team needed to know what changed and what they had to do.

**✅ With the rules**

```
The pricing change, in three paragraphs:

**What's changing**
Starter tier moves from $29 → $39/mo. Pro tier unchanged. Existing customers
grandfathered through end of contract.

**Why now**
[One concrete reason from the linked doc, with a quote/link.]

**What you need to do**
- Sales: new pricing in CRM by Friday
- Support: macros updated by Monday
- Anyone with a customer call this week: use the FAQ in
  [link to actual FAQ doc, not invented]

That's the whole thing. Want me to expand any section?
```

**The test:** Would a busy PM read this and think "I asked for less than this"?

---

## 4. Surgical Edits

### Scenario: "Tighten this user story."

**Input:**

> *Title: User Story – Bulk Edit*
> *As a user, I want to be able to select multiple items at once and edit them together because doing them one by one is slow.*
> *Acceptance Criteria:*
> *- User can select multiple items*
> *- User can edit them*

**❌ Without the rules**

AI returns:

```
**Title:** Bulk edit for list items

**User Story:**
As a power user managing large datasets, I want to perform bulk
edits across multiple selected items so that I can reduce
repetitive manual effort and improve workflow efficiency.

**Acceptance Criteria:**
Given a user has selected two or more items
When they invoke the bulk edit action
Then a modal appears allowing them to edit shared fields

Given the user submits the bulk edit
When the system processes the request
Then all selected items are updated atomically
And the user receives a confirmation toast

**Definition of Done:**
- Code reviewed and merged
- Unit tests passing
- E2E tests covering the flow
- Documentation updated
```

Problems: changed the title, replaced the user story (didn't tighten — substituted), restructured AC into GWT (you didn't ask for that), invented a "power user" persona, added a Definition of Done you didn't request.

**✅ With the rules**

```
Tightened story:

*As a user, I want to edit multiple items at once so I can stop
repeating the same edit.*

Two notes I'm flagging, not fixing (you asked me to tighten, not rewrite):
- AC are very thin — "user can edit them" is vague enough to ship the
  wrong thing. Want me to draft AC in a separate pass?
- "Bulk Edit" as a title is fine but the team usually leads tickets with
  the verb. *Could* be "Add bulk edit to item list" — but that's a title
  rewrite, which is outside this ask.
```

**The test:** Every changed character traces directly to "tighten the story."

---

## 5. Match the Audience

### Scenario: "Summarize this incident for the team."

**❌ Without the rules**

AI writes one summary:

> *On Tuesday at 14:32 UTC, the auth service experienced a partial
> outage affecting 12% of login attempts. The root cause was a stale
> connection pool configuration in the auth-go service, which exhausted
> available connections under the morning traffic spike. We deployed a
> fix at 15:18 UTC. Customer impact was limited but visible. Going
> forward, we are introducing connection pool monitoring.*

The exec skims it and stops at "auth-go service" because they don't know what that is. The engineer reads it and finds nothing actionable. The customer-facing lead can't paste any of it into a status page.

**✅ With the rules**

```
Quick question first — which team? The summary changes a lot:

- **Exec**: outcome, customer impact, decision needed → 4 sentences,
  no service names
- **Engineering**: root cause, timeline, what to monitor → technical,
  with the auth-go connection pool detail
- **Customer-facing (support/CX)**: what customers experienced, how
  to respond if they call → impact-led, no internal jargon

If you want all three, say so and I'll draft three separate ones — but
I won't write a single summary that tries to do all three jobs, because
that's the version that fails for everyone.
```

**The test:** Could you paste the output directly to the named audience without rewording?

---

## 6. Follow Conventions

### Scenario: "Write a ticket for the login bug."

**❌ Without the rules**

```
Login Bug

Some users are reporting issues with logging in. It seems to be
happening when their email contains certain special characters.
We should look into this and fix it. Priority: high.
```

Problems: vague title, prose where structure is expected, no reproduction steps, no AC, no severity criteria, "we should look into this" is not a ticket.

**✅ With the rules**

```
**Title:** Fix login failure when email contains "+"

**Problem**
Users whose email addresses contain a "+" character (commonly used for
aliasing, e.g. `name+work@gmail.com`) cannot log in. The form returns a
generic "invalid credentials" error even when the password is correct.

**Reproduction**
1. Create or use an account with `+` in the email
2. Attempt to log in via /login
3. Observe: "invalid credentials" error
   Expected: successful login

**Solution (proposed)**
The email is being URL-encoded twice in the auth payload. Either:
(a) strip the double-encoding before the lookup, or
(b) normalize at write-time. (a) is the surgical fix.

**Acceptance Criteria**
- Given an email containing "+", when the user submits valid credentials,
  then login succeeds
- Given an email containing "+", when the user submits invalid credentials,
  then the error is "invalid credentials" (not "user not found")

**Severity:** P1 — silently locks out a known segment of users
```

**The test:** Could an engineer pick this up without asking a single follow-up question?

---

## 7. Cite Sources

### Scenario: "Summarize last sprint's retro."

**❌ Without the rules**

```
Last sprint's retro went well overall. The team felt good about velocity
and was happy with the launch. Some concerns were raised about the
on-call rotation, and there was discussion about improving documentation.
Action items were assigned.
```

Problems: nothing is sourced, "the team felt good" is invented, "action items were assigned" is filler. If this gets pasted into a status update, AI just laundered fiction into authority.

**✅ With the rules**

```
Retro summary, with line refs to the retro doc:

**What went well**
- Launch hit the GA date with no Sev1s (Marina, line 14)
- Bug triage process from last sprint kept the backlog flat (Tom, line 23)

**What didn't**
- On-call rotation: two engineers paged 8+ times in the week
  (Priya, line 41) — *flagged as needing follow-up, no owner yet*
- Doc drift on the new payments flow (mentioned three times — lines
  47, 52, 58)

**Action items (with owners, as recorded in the doc)**
- On-call rebalance proposal — Priya, due next retro (line 67)
- Payments doc audit — Tom, no due date yet (line 71)

One source-flagged note: the retro doc has a "Hot Takes" section
(lines 80–95) that wasn't formally captured as decisions. I didn't
include it in the summary — let me know if you want it surfaced.
```

**The test:** Could you open every claim in a new tab?

---

## 8. Surface Conflicts

### Scenario: "What did the team agree on for Q3 scope?"

**❌ Without the rules**

```
The team agreed to focus on growth-driving features in Q3, with some
investment in platform stability. The plan includes shipping the new
onboarding flow and addressing key infrastructure improvements.
```

Problems: there was no consensus. AI blended three disagreeing voices into one fake one. The infrastructure lead who pushed hardest for stability just got averaged out, and the doc reads like everyone agreed.

**✅ With the rules**

```
There isn't one agreement — there are three positions and a most-recent
decision. Surfacing them:

**Position 1 — Growth focus** (PM lead, Q3 planning doc, March 18)
Argument: customer acquisition cost rising, need conversion improvements.
→ Proposed scope: onboarding rewrite, pricing page A/B tests.

**Position 2 — Infra focus** (Eng lead, Slack #q3-planning, March 12)
Argument: tech debt blocking velocity, two Sev2 incidents this month.
→ Proposed scope: auth refactor, observability buildout.

**Position 3 — Split** (CTO, design review, March 20)
Argument: do both, smaller surface in each.
→ Proposed scope: onboarding + auth refactor, drop pricing tests.

**Most recent decision:** Position 3 (CTO call, March 20).
**Unresolved:** Eng lead's pushback was not formally addressed before
the call. Worth checking before treating this as locked.

I'm not blending these because the disagreement is the information.
```

**The test:** Could you tell which decision-maker got overruled, and on what?

---

## 9. Confirm Before Anything Public

### Scenario: "Reply to this customer email asking about the pricing change."

**❌ Without the rules**

```
Sent! ✉️

I've replied to the customer with a friendly explanation of the
pricing change and an offer to schedule a call if they have more
questions. I also CC'd the account manager.
```

Problems: you didn't see the draft. You don't know what was promised. The CC was a guess. The customer now has a written commitment in their inbox.

**✅ With the rules**

```
Draft reply (not sent — confirm before I do anything):

---
Subject: Re: Question about the new pricing

Hi [Name],

Thanks for flagging this. To clarify what's changing for your account:
[specific to their tier, based on the linked email — not invented].

Two things to know:
- Your current contract is grandfathered through [date from CRM].
- After that, your renewal would be at [new rate], assuming the same
  tier.

Happy to set up a call if it'd help to walk through it.

[Your name]
---

Three flags before I send:
- "[date from CRM]" — I don't have CRM access, you'll need to fill in
- The grandfathering clause is what I read in the pricing doc; confirm
  it applies to their specific contract type before I claim it
- I haven't CC'd anyone — let me know if their AM should be on it

Reply "send it" or "fix X" and I'll act on that.
```

**The test:** Did anything leave the chat without you confirming?

---

## 10. Checkpoint and Fail Loud

### Scenario: "Build a launch checklist for the new pricing rollout."

**❌ Without the rules**

```
Launch Checklist ✅

✅ Update pricing page
✅ Update billing system
✅ Update sales materials
✅ Send customer comms
✅ Update support macros
✅ Brief the sales team
✅ Update the FAQ
✅ Schedule the rollout
✅ Set up monitoring
✅ Prepare rollback plan
✅ Update legal terms
✅ Announce internally
```

All checkmarks. No flags. Looks done. Two of those are guesses, three of them have no owner, and the legal terms one is a thing AI invented because launches usually have one.

**✅ With the rules**

```
Launch checklist with verification status:

**✅ Verified (sourced from the launch doc)**
- Update pricing page → owned: Marketing (Jess), due Friday
- Update billing system → owned: Eng (auth-billing squad), due Wed
- Update support macros → owned: Support (Priya), due Monday
- Brief the sales team → owned: PMM (Lin), AE call scheduled Thursday
- Schedule the rollout → 2026-06-15, 09:00 PT (per the launch doc)

**⚠️ Verified with caveat**
- Send customer comms → draft exists in the comms doc, but the segment
  list is empty. Who's pulling the list?
- Update legal terms → mentioned once in the launch doc but no owner
  named. Likely needs Legal — flagging because "update legal terms"
  without an owner is how things slip.

**❓ Open — I couldn't verify these**
- Rollback plan: not in the launch doc. Has one been written?
- Monitoring: launch doc says "monitoring in place" but no link. If
  you tell me where it lives, I can check.
- Internal announce: mentioned in passing in Slack but I couldn't find
  a draft. Does one exist?

**⏭️ Not included (deliberately)**
- I did NOT add "update legal terms" as a generic line item — I only
  included it because the launch doc mentioned it. If your launches
  don't usually need legal review, drop it.

Status summary: **5 verified / 2 caveat / 3 open / 0 invented.**
```

**The test:** Could you tell which items are real, which are guesses, and which are open — without reading the source doc?

---

## Anti-Patterns Summary

| Rule | Anti-pattern | Fix |
|------|--------------|-----|
| Think first | Picks one interpretation silently | Names assumptions, asks before drafting |
| Read context first | Summarizes the prompt, not the source | Reads the full thread/doc, cites lines |
| Minimum deliverable | Adds FAQ, glossary, appendix unprompted | Smallest artifact that meets the goal |
| Surgical edits | "Improves" things you didn't ask to change | Only changes what was asked, flags the rest |
| Match audience | One voice for everyone | Asks which audience, drafts for that one |
| Follow conventions | Prose where structure is expected | Team's actual format (GWT, imperative titles, etc.) |
| Cite sources | Fluent authority with no links | Every claim sourced, no source = labeled assumption |
| Surface conflicts | Blends disagreement into fake consensus | Names positions, picks one with reasoning, flags the others |
| Confirm before public | Auto-sends, auto-posts | Drafts, waits for "send it" |
| Checkpoint and fail loud | All checkmarks, no flags | Status block with verified / caveat / open / skipped |

---

## Key Insight

The "wrong" outputs above aren't obviously broken. They're fluent, professional, and look done. That's the failure mode: AI in PM work doesn't usually produce garbage — it produces **confident-looking output with quiet gaps**, and the gaps land on you when you ship it.

The 10 Rules don't make the AI smarter. They make it **stop hiding the gaps.**
