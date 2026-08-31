# session-punchlist

An agent skill that draws the whole working session as
a punch list — an ASCII-and-emoji status pane bucketed
by where each item actually sits right now.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 📋  PUNCH LIST — flaky test in the retry path
     ▓▓▓▓▓▓▓▓░░░░░░░░░░░░  2/5
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✅ DONE
   ✔ Reproduced it — fails 1 run in 20
   ✔ Traced it to a shared clock in the fixture

🔨 IN FLIGHT
   ▸ Inject the clock instead of reaching for it

⏳ WAITING
   ⊘ Full suite on CI · #412

⏭️ NEXT
   ☐ Drop the retry loop once it is green

💭 MAYBE
   ◌ Audit the other fixtures for the same shape
```

## Install

```
npx skills add landon9720/session-punchlist
```

Or copy `skills/session-punchlist/SKILL.md` into your
agent's skills directory.

## What it is for

Chat scrolls; a status pane doesn't. The board is drawn
once at the start to settle what the session is, redrawn
whenever the shape changes, and shown again at the end —
where, because items carry their pull requests, tickets
and paths, it doubles as the handoff.

The buckets are temporal and all of them are scoped to
the session in front of you: what is done, what is
moving, what is stalled, what is queued, and what
probably will not happen. Name them, merge them, or drop
the empty ones to fit the work.

One rule does the load-bearing work:

> **Started or not started.** That is the only line
> between in flight and next — not importance, not size,
> not what you intend to pick up soonest. Anything you
> have touched is in flight until it is finished or it
> leaves your hands. When it leaves your hands and you
> are waiting on a machine or a person, it moves to
> waiting, never back to next.

Without it, "in flight" quietly becomes "the thing I
care about most" and the board stops describing reality.

## Style

The look is borrowed from text-mode interfaces — BBS
door games, character sheets, roguelike status lines —
where position carries meaning and you read the change
rather than the text. So: glyphs and bucket order stay
put between renders, emoji are spent on structure rather
than sprinkled through the prose, nothing is padded into
a right-hand column, and no line is ever long enough to
fold. How wide is a judgment call; that it never wraps
on its own is not.

## License

MIT
