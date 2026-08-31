---
name: session-punchlist
description: >-
  Draw the session as a punch list — an ASCII-and-emoji
  status pane of check marks, bucketed by where each
  item sits in the session: done, in flight, waiting,
  next, maybe. Open with it to settle scope, update it
  as work lands, show it at the end and fold it into any
  handoff. Use on "punch list", "punchlist", "where are
  we", "what's left", or when a multi-step session is
  worth framing before starting.
---

# Session Punch List

The session, drawn as a status pane — text-mode
lineage, where position carries meaning and you read
the change rather than the text.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 📋  PUNCH LIST — <what this session is>
     ▓▓▓▓▓▓▓▓░░░░░░░░░░░░  3/8
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✅ DONE
   ✔ <finished, and checked that it worked>
   ✔ <finished> · <#123>
   ✔ <finished>

🔨 IN FLIGHT
   ▸ <started, not finished> · <path/to/file>

⏳ WAITING
   ⊘ <started — now on CI, a review, a reply>

⏭️ NEXT
   ☐ <not started, and first in line> · <TICKET-1>
   ☐ <not started>
   ☐ <not started>

💭 MAYBE
   ◌ <might not happen, or not this session —
     plus the reason, which is the part worth
     keeping>
```

That is the spec. The buckets are temporal, and all of
them are about this session — what is done, what is
moving, what is stalled, what is queued, what probably
will not happen. Name them, merge them, drop the empty
ones to fit the work.

A session is a unit of value, its context is finite and
spent continuously, and it has an inherent shape it will
follow whether or not you attend to it. The board is
where you think about how the work in front of you fits
that shape.

Populate what you can from what you know. Sometimes that
is a lot; sometimes you are walking into a bug you do
not understand yet and it is almost nothing. A thin
board is a fine board — it fills in as you learn.

**Order along the session's arc.** Sessions run
read-heavy, then action-heavy, then retrospective, and
ordinary checklist order already encodes that. Near the
top: what you know, what you are unsure of, questions to
answer, analyses to run, things to go read. Through the
middle: the actions — run it, write it, open the pull
request, review it adversarially, check the signal in
production. At the bottom: synthesize, extract,
summarize, project, make durable.

**The closing band is an item, not an afterthought.**
Recording what the session learned comes due exactly
when context is longest and attention is thinnest, which
is why it is the part that gets skipped. Put it on the
board at the start, when it costs nothing. A session
that did good work and wrote none of it down spent all
its context and kept nothing.

**Started or not started.** That is the only line
between in flight and next — not importance, not size,
not what you intend to pick up soonest. Anything you
have touched is in flight until it is finished or it
leaves your hands. When it leaves your hands and you
are waiting on a machine or a person, it moves to
waiting, never back to next.

**Line width is deliberate.** Nothing should run long
enough to fold — a terminal wrap lands at whatever
column the window happens to be, and the drawing comes
apart. So you do the wrapping, not the terminal. How
wide is a judgment call: let the content choose it,
keep one board internally consistent, and let a section
sit narrower than the rest where that reads better. The
rules set the width; everything else lives inside them.
Continuations align under the item text, and a line
that will not fit is usually two items.

**The frame is furniture.** Glyphs and bucket order
stay put between renders, so the diff is readable at a
glance. Retitle and reflow freely; don't move the
cabinet.

**Emoji are sprite work.** One glyph, one state, spent
on structure — bucket headers and item marks, not
inside item text where they compete with the marks
doing the work.

**No right border.** Rules, insets, whitespace.
Anything hand-aligned is something you stop redrawing.

**Items carry their handles.** A pull request, a
ticket, a repo path — appended after a `·`, not
described in prose. Bare identifiers are clickable in
most terminals, they survive being pasted elsewhere,
and they are what lets the closing board double as the
handoff. Don't pad them into a column.

Redraw when the shape changes, not every turn. In
between, a line is plenty:

`✔ <last thing> → 🔨 <what is now in flight>`

Open with a draft board rather than an interview — the
guesses in the bottom buckets are what surface an
unspoken expectation. Show it again at the end, ahead
of any prose.
