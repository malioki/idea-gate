# Idea Gate

A Claude skill for people who build things on the side and get pitched ideas constantly: viral "this app makes $300k/month" threads, idea catalogs, courses, a friend's scheme.

Most of those ideas are fine in general and wrong for you in particular. The costly mistake is rarely a bad verdict. It's debating the same kind of idea for the fifth time, or getting pulled off your plan by a good-looking post.

Idea Gate makes Claude judge every idea against **your** situation, and remember what you already decided.

## What it does differently

- **Judges against you, not the market.** A short private profile holds your skills, current projects and hard rules ("no paid ads before revenue", "no personal social media"). An idea that fails a hard rule fails, however good the product is.
- **Remembers.** Before forming an opinion, it searches your decision log. If you already settled this kind of idea, it applies that rule in three lines instead of re-arguing it.
- **Checks the evidence.** It labels each number as verified revenue, a third-party estimate, or one survivor's anecdote, and notes who is telling the story and what they sell.
- **Salvages.** Even a rejected idea often has one transferable trick. It names that piece and where it goes in what you already do.
- **Merit first, calendar later.** "No time" is a scheduling question. The skill judges the idea on its own merit and leaves capacity to the planning step.

Every evaluation ends in one verdict: **TAKE**, **DON'T TAKE**, **TAKE A PIECE**, or **PARK** with the trigger that would reopen it. The reason is written as a rule for the whole class of idea, so the next similar post is settled in advance.

See a [worked example](skills/idea-gate/references/example.md).

## Install

In Claude Code:

```
/plugin marketplace add malioki/idea-gate
/plugin install idea-gate@idea-gate
```

Or copy `skills/idea-gate/` into `~/.claude/skills/`.

## Set up your profile

Copy [`profile-template.md`](skills/idea-gate/references/profile-template.md) to one of:

- `.claude/idea-gate/profile.md` in the project where you keep your business notes, or
- `~/.claude/idea-gate/profile.md` to use it everywhere.

Fill in who you are, what you're working on, your hard rules, and where your decision log lives. Short is fine. Pointing to files you already keep beats copying them.

The profile is yours and stays on your machine. Nothing in this repository needs your data, and the skill works without a profile too. It just says what it had to assume.

## Use

Paste an idea, a link or a post, and ask "worth it?". The skill triggers on its own for idea evaluation, or you can call it as `/idea-gate:idea-gate`.

## License

MIT
