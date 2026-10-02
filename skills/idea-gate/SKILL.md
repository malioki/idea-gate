---
name: idea-gate
description: Evaluate a business idea, money-making scheme, side project, growth tactic or "opportunity" against the user's own situation and their past decisions, then return a clear verdict (take / don't take / take one piece / park) with the reason and the next step. Use this whenever the user shares an idea, a startup or SaaS concept, a viral post or thread about how someone makes money, an idea catalog, a course pitch, a new channel or venture they are considering, or asks "what do you think about X", "is this worth doing", "should we try this", "разбери идею", "стоит ли" — even if they don't say "evaluate". Also use it when an idea resembles one the user already decided on, so the old decision is applied instead of re-debated.
---

# Idea Gate

People who build things on the side get pitched ideas constantly: posts about apps making $300k/month, idea catalogs, courses, "steal this startup" threads, a friend's scheme. Most of these are fine in general and wrong for this particular person. The expensive failure isn't a bad verdict. It's debating the same class of idea for the fifth time, or getting pulled off the current plan by a shiny post.

This skill does three things a generic opinion doesn't:

1. **It judges against the person, not the market.** It uses a profile with their skills, assets, current projects and hard rules.
2. **It remembers.** It checks the decision log first and applies earlier verdicts instead of starting over.
3. **It salvages.** Even a rejected idea usually contains one mechanic worth keeping, and that piece is often the real value of the conversation.

## Step 0: load the context

Find the user's profile, in this order:

1. `.claude/idea-gate/profile.md` in the current project
2. `~/.claude/idea-gate/profile.md`

The profile says who the user is, what they're already working on, their hard rules, where their decision log and task list live, and how they want verdicts recorded. Read the files it points to that matter for this idea. Usually that means the decision log, plus the strategy or project file closest to the idea.

If no profile exists, still do the evaluation, but say what you had to assume. Then offer to create a profile from `references/profile-template.md`. The verdict gets much sharper with it.

**Search the decision log before forming an opinion.** Look for the idea itself, its category (idea catalogs, paid UGC, marketplaces, courses), the source, and the core mechanic. If an existing decision already covers this class, say so up front, quote the rule, and apply it in a few lines. Reopen a past decision only if something material changed: new facts, a constraint that no longer holds, or a trigger condition the decision named. Even then, say explicitly what changed. Re-debating settled questions is exactly what the log exists to prevent.

## Step 1: say what the idea actually is

Restate it in one or two sentences: what gets sold, to whom, and the claimed mechanism that makes money. Posts often bury this under hype. Writing it out plainly is half the evaluation.

## Step 2: check the source and the evidence

Ask who is telling this story and what they get out of it. A course seller, a paid community funnel, an affiliate, or a tool vendor isn't automatically wrong, but the incentive shapes which facts appear. Note it in one line.

Then label every number the idea leans on:

- **Verified:** read directly from a payment processor, public filings, or the user's own data.
- **Estimate:** third-party trackers such as app-revenue estimators or traffic estimators. Useful for order of magnitude, not as revenue.
- **Anecdote or survivorship:** one winner shown, the losers using the same method not shown.

Proof that the market is large isn't proof of demand for this specific product. Keep those apart.

## Step 3: judge the merit

Judge the idea on its own merit first. Skip **time and capacity** at this stage unless the profile says otherwise. "No time" is a scheduling question, and mixing it in hides whether the idea is actually good. Bring capacity in at the end, when placing the idea into a plan.

Cover what is relevant, briefly:

- **Fit:** does it use the user's real skills and assets? Does it strengthen a current project or compete with it for the same scarce resource?
- **Economics:** who pays, how much, and when the first money arrives. An idea that pays from the first sale behaves very differently from a startup-shaped idea that needs building before any revenue. Name which kind this is.
- **Distribution:** how does it reach buyers? This is where most ideas die for solo builders. If the channel needs something the user has ruled out (public presence, paid ads before revenue, cold outreach), the idea fails here, however good the product is.
- **Competition and moat:** free or self-hosted alternatives, incumbents, and whether anything stops a copy.
- **Viability:** legal and platform risk, and dependencies on someone else's rules.

## Step 4: apply the hard rules

Check the profile's hard rules: what the user won't do, can't do, or has decided against. These are filters, not weights. One failed hard rule sinks the idea as proposed, but the salvage step still applies.

Some rules have an intent behind the wording. A "no social media presence" rule might really be about personal time and exposure. Then a version where hired creators do the posting isn't a violation of that rule, but it is paid advertising, which may hit a different rule. Reason about the intent and say which rule actually decides.

## Step 5: verdict

Give exactly one:

- **TAKE:** worth doing; name the first concrete step.
- **DON'T TAKE:** fails on merit or a hard rule. "No" is a complete, useful answer, so don't soften it into "maybe later" without a reason.
- **TAKE A PIECE:** the whole idea doesn't fit, but one mechanic, trick or insight transfers. Say exactly where it goes in the user's existing work.
- **PARK:** promising, but blocked by something specific. Name the trigger that would reopen it, such as a date, a metric, or an event. Without a trigger it's just a soft "no".

Then answer the salvage question even for DON'T TAKE: is anything here worth keeping? Often the answer is no, and that's fine.

**Write the reason so it works as a rule for the whole class.** "We don't take idea catalogs as an idea source; we use them only as a reference for verified revenue" settles the next ten such posts. "This catalog isn't good" settles only this one.

## Step 6: record it

Follow the profile's recording rules. Typically:

- Add an entry to the decision log in the user's format: date, the decision in one line, why, and what to do with the next similar idea.
- Add any action the user must take personally to their task list.
- If the profile doesn't say whether to write or propose, propose the entry and ask.

## Output shape

Lead with the verdict and the reason in two or three sentences, so the user gets the answer even if they read nothing else. Then give the supporting breakdown, only the parts that actually mattered for this idea. Skip sections that add nothing. Respond in the user's language, in the tone the profile asks for. Default to direct and unsentimental: the user wants an honest filter, not encouragement.

```
**Verdict: <TAKE | DON'T TAKE | TAKE A PIECE | PARK>** — <one-sentence reason>

<If an earlier decision covers this: which one, and how it applies>

**What it is:** <the idea in plain words>
**Source and evidence:** <who's telling it; which numbers are verified vs estimates>
**Why:** <the 2–4 points that decided it>
**What we keep:** <the transferable piece, or "nothing">
**Next:** <concrete step, or the trigger for PARK>
```

See `references/example.md` for a worked evaluation.
