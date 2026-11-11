# Day 03 — Flowchart refinement

## What we did
- Improved the Day 02 chatbot flowchart so it also shows **what happens when things go wrong**.
- Added a time limit, retries, a backup answer and a hand-off to a person.
- Grouped the steps into 3 stages.
- Arranged it so no arrows cross.

## Diagram
![Support chatbot flowchart v2: success, failure and escalation paths](./day03-support-chatbot-flowchart-v2.drawio.svg)

## How to read it
1. **Stage ① Understand the question.** If the bot isn't sure, it hands over to a person.
2. **Stage ② Answer it.**
   - The AI gets **10 seconds** to reply.
   - No reply? **Try again**, up to 3 times (wait 1 s, then 2 s).
   - Still nothing? Use a **backup**: search the FAQ instead.
   - FAQ not a good match? Hand over to a person.
3. **Stage ③ A person takes over.**
   - Someone free within 2 minutes → live chat.
   - Nobody free → the customer gets a ticket number and a reply by email.

## The 4 new ideas
### 1. Group steps into stages
- Put related steps in a dashed box (a "container") with a short numbered title.
- The reader can see which stage they're in at a glance.
- Draw.io: *Arrange → Insert → Container*, then drag steps inside it.

### 2. Write clear box labels
- A step starts with a verb: "Create ticket", "Generate answer".
- A question ends with `?`: "Valid reply within 10 s?"
- Put numbers in the label (10 s, max 3, 2 min). Then anyone can check whether the rule is followed.

### 3. Label the arrows that matter
- Label every arrow that leaves a diamond (Yes / No).
- Be specific when it helps: "No: timeout / error / empty" says more than "No".
- Name the loop arrow ("retry") so it doesn't look like a mistake.
- Skip labels on plain step → step arrows.

### 4. Handle every error
- Every failure must lead somewhere. No dead ends.
- Use this order: **try again → use a backup → ask a person**.
- Every loop needs a limit (max 3 tries). Waiting for a person needs a limit too (2 min).

## Colours used
| Colour | Means |
|---|---|
| Blue | Normal step |
| Green | Success |
| Red | Retry |
| Purple | Backup (FAQ) |
| Orange | Hand-over to a person |

## Tips for no crossing arrows
- Give each kind of path its own column: success on the left, recovery in the middle, people on the right.
- Join all the "hand over to a person" arrows into one line before they enter stage ③.
- Keep the retry loop small and close to the step it repeats.
