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

## A session is a unit of value

A session with a language model is not only a chat log
on the way to the real work. It is a bounded run of
context and attention that either compounds into
something durable or evaporates when the window closes.

That framing has a practical consequence. Context is
finite and spent continuously, and a session has an
inherent shape it will follow whether or not you attend
to it. What is worth doing early is thinking about how
the problem you are bringing fits that shape — and
writing down whatever you can already see.

Sometimes that is a lot. Sometimes you are walking into
a bug you do not understand yet and it is almost
nothing. A thin board is a fine board; it fills in as
you learn. The point is to start thinking in this shape
sooner, not to have the answer up front.

The punch list is the instrument for that. Chat scrolls;
a status pane doesn't. The board is drawn once at the
start to settle what this session is, redrawn whenever
the shape changes, and shown again at the end, where it
does two things for a handoff: it is the reminder to
write one, and it keeps the material ready — since items
carry their pull requests, tickets and paths, whatever
gets written has them already at hand.

## Sessions have an arc

Read-heavy at the start, action-heavy through the
middle, retrospective at the end. This is not a
methodology imposed on the work — it is the shape work
has, common enough that it usually goes without saying,
and common enough that it is the shape the model
absorbed from nearly everything it was trained on.

So it is the trajectory you are on either way. The
value in naming it is that you can then play to it: put
the reading where the session is already disposed to
read, the building where it is disposed to build, the
synthesis where it is disposed to look back. A checklist
read top to bottom encodes the same arc, which is why
the ordering does real work instead of merely ranking
priority.

**Near the top** — what you know, what you are unsure
of, the questions to answer, the analyses to run, the
things to go read.

**Through the middle** — the actions. Run the
simulation, write the code, open the pull request, run
the adversarial review, verify the signal in production.
Whatever your workflow's real steps are, they get named
here instead of assumed.

**At the bottom** — synthesize, extract, summarize,
project, make durable.

That last band is the one that gets skipped, and it is
skipped for a structural reason: it comes due exactly
when the context is longest and attention is thinnest.
Writing it onto the board at the start, when it costs
nothing, is what makes it survive to the end. A session
that did good work and recorded none of it spent all its
context and kept nothing.

The buckets themselves are temporal and all of them are
scoped to the session in front of you: what is done,
what is moving, what is stalled, what is queued, and
what probably will not happen. Name them, merge them, or
drop the empty ones to fit the work.

## The rule that does the work

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
