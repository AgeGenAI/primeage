---
name: daily-checkin
description: Do the Prime Age daily check-in in conversation — today's open morning or evening questions, answered one at a time and saved to the person's Prime Age account, with the same points and streak as the app. Use when someone asks to check in, do their morning or evening check-in, log today, or answers "yes" to a check-in offer.
---

# The daily check-in

The check-in keeps a Prime Age current: a few questions a day, the same ones
the Prime Age app asks. A check-in done here **is** the app's check-in — the
same streak and the same Prime Points.

## When to start

Only when the person asks, or says yes to an offer. When a signed-in result
carries `checkin_today.offer`, mention it **once** in one short sentence and
ask whether they want to do it now. Never start the questions unprompted and
never repeat the offer in the same conversation.

## How to run it

1. Call `get_checkin`.
   - `open_now` empty and `later_tonight` set: say when the evening questions
     open (the person's own time) and stop.
   - `done_for_today: true`: say today is done. No nudge, no "don't forget".
2. Ask each question in `open_now` **one at a time**, with its options. For a
   question marked `multi`, say several answers may apply.
3. Call `submit_checkin` once, with every answer:
   `{lever, choice}` — and for a `multi` question also `choices` with every
   picked number (`choice` is then the largest of them).
4. Report what came back: the Prime Age, the streak in days, the points
   earned. If `still_open` is not empty, say what is left.

Evening questions ask about *today* and only open at the person's evening
hour. If a submit is refused as "not open right now", call `get_checkin`
again rather than retrying.

## Measurements

If the person also mentions a measurement ("I weighed 80 kg"), offer to log
it with `log_metrics` in the unit `get_my_trends` lists. The first time this
needs a one-time consent given in the Prime Age app — if the tool says so,
pass the link on and do not retry. Measurements never change Prime Age.

## Boundaries

- No judgement on any answer or number: no "good", "bad", "worrying".
- Never state doses, brands or diagnoses. For symptoms, refer to a clinician.
