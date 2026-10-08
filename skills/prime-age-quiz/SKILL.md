---
name: prime-age-quiz
description: Run the Prime Age quiz in conversation — twelve habit questions asked one at a time, then the person's Prime Age and the habit to move first, with its protocol. Use when someone asks for their Prime Age, wants to take the quiz or test their habits, or asks "how old are my habits".
---

# The Prime Age quiz

Prime Age is a self-assessment of twelve daily habits (sleep, movement, food,
stress, alcohol, smoking and more), expressed as an age. It is educational
wellness content: not a medical test, not a diagnosis, and it never says
anything about a body — only about the answers given.

## How to run it

1. Call `prime_age_questions`. It returns twelve questions, each with its
   options and their `choice` numbers.
2. Ask **one question at a time**, with its options as a short list. Do not
   paraphrase the options into something else, and do not comment on an
   answer ("great", "that's bad") — just move to the next one.
3. Ask the person's age (16–100). Under 16: stop politely; the product is 16+.
4. Call `prime_age_calculate` with the age and one `{lever, choice}` per answer.
5. Report, in this order and briefly:
   - the Prime Age, next to the calendar age;
   - the **one** habit to move first, with its protocol and its agegen.ai link;
   - the other two from the result, one line each.

## If they are signed in

If the Prime Age tools are connected and `get_my_prime_age` says
`quiz_taken: false`, offer once to keep the result: "Want me to save this to
your Prime Age account?" Only on a yes, call `save_quiz_result` with the same
age and the same twelve answers. If the account already has a Prime Age, do
not offer — the daily check-in updates it instead.

## Boundaries

- Never state doses, brands or diagnoses. For symptoms, say plainly that this
  is a question for a clinician.
- Never call a number good or bad. The result is a description of habits.
- If a result mentions Prime Age Pro, say so once, plainly, with the link the
  tool gave. Do not repeat it or push it.
