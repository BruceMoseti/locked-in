# Locked In

**Commit to your day.** Write your to-dos messy. Locked In lays out the day using
human assumptions about when work actually gets done — then holds you to it.

### [→ Try it live](https://brucemoseti.github.io/locked-in/)

No sign-up, no install, no backend. One HTML file.

---

## Why not just ask an AI to plan your day

A language model is good at reading *"finish the deck sometime tomorrow, call mom,
gym"* and turning it into structured tasks. It is bad at scheduling, because
scheduling is constraint satisfaction — and the same input should produce the same
day every time.

So parsing may be model-assisted. **Placement never is.** Every block is decided in
ordinary code and carries a reason you can argue with:

> *Post-lunch dip — low-focus work while attention is lowest.*

Three things follow. The plan is reproducible, so you can tell whether a change made
it better. It works offline with no API key. And when it puts something somewhere you
disagree with, you can read the reason and change the rule.

## The assumptions

| Rule | Why |
|---|---|
| Lunch is placed first and never scheduled over | a "flexible" break is a deleted break |
| Deep work in the morning peak, hardest first | focus is a depleting resource, not a constant |
| Nothing deep in the post-lunch dip | it gets done badly and resented |
| Focus blocks capped at 90 min, then a break | past that the hour stops paying for itself |
| Admin batched, not scattered | the context switch costs more than the task |
| Exercise kept 45 min clear of lunch | |
| Errands pushed to the end of the day | leaving at 11am costs the whole morning, not 45 minutes |
| 5-minute buffer between everything | people do not context-switch instantly |
| Overflow deferred with a reason | a plan you cannot follow teaches you to ignore plans |

## Committing to it

A plan you only read is a suggestion. The second half of the app is about living
inside one.

**Lock in** a block and it becomes immovable — every later re-plan routes around it.
If a commitment can be quietly rescheduled, it was never a commitment.

**Start** runs a timer. **Finish** records what it *actually* took, not what you
budgeted. That gap is the only honest input a re-plan has; a scheduler that assumes
you finished on time will be wrong by lunch.

**Re-plan from now** rebuilds the rest of the day around reality. Three kinds of block
never move:

| | |
|---|---|
| **Locked** | you committed; moving it would make the commitment meaningless |
| **Done** | it happened, and history is not reschedulable |
| **Running** | interrupting focus to optimise a timetable is exactly backwards |

The header shows **drift** — how far behind or ahead you are, measured from finished
work only.

## What it understands

```
finish the quarterly deck 2h
urgent: fix the login bug by 2pm
standup at 9:30am 15m
email Sarah about the invoice
call mom 15m
gym
buy groceries
```

Durations (`45m`, `2h`, `quick`), fixed times (`at 9:30am`), deadlines (`by 3pm`),
urgency (`urgent`, `asap`). Unrecognised work is assumed to need focus —
under-scheduling a shallow task costs minutes, under-scheduling a deep one wrecks
the day.

Preferences accept plain English: `start 8am, lunch at 1, finish by 5`.

## Running it

Open `index.html`. That is the whole thing — no build step, no server, no dependencies.

## Stack

Vanilla JavaScript. No framework, no bundler, no packages. The scheduling engine is a
plain ES module with no imports and no DOM, which is what lets the rules be tested
without a browser.

## Licence

MIT
