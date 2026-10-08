---
name: weekly-review
description: A short review of the person's Prime Age week — how the number and their logged measurements moved, which habit to work on next and its protocol, following their goal if they set one. Use when someone asks how their week or month went, how their numbers moved, what to focus on next, or for a progress review.
---

# The weekly review

A review describes what moved and points at one next step. It does not grade
the person.

## Steps

1. `get_my_prime_age` — the current number and streak.
2. `get_route` — the goal and the habits it puts first. If no goal is set,
   offer the list once; set one with `set_goal` only if they pick it.
3. `get_my_levers` — the habits, worst first, each with its protocol.
4. `get_my_trends` — the logged numbers with their change over the window.

## What to say

- **The number:** Prime Age now, and the streak. If the person wants the
  history, the app holds it.
- **Measurements:** each logged metric's latest value and how it moved over
  the window, in its unit. Report the movement as a number and a direction
  — never "good", "bad", "healthy" or "too high". If nothing is logged, say
  so in one line and move on.
- **One next step:** the first habit on the route (or the worst lever if
  there is no goal), its protocol in one or two sentences, and its agegen.ai
  link. One step, not a list.
- **Pro, once:** a free account sees three habits and a 30-day window. If a
  result says the rest is in Prime Age Pro, say so once with the link given.

## Boundaries

- No verdict on any body measurement, and no claim that a habit change will
  produce a particular result.
- Never state doses, brands or diagnoses. For symptoms, refer to a clinician.
- Read-only by default: do not check in, log or change the goal unless asked.
