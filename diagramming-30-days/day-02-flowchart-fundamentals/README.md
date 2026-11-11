# Day 02 — Flowchart fundamentals

## What we did
- Drew a flowchart for a support chatbot. It either answers the customer's question or hands it to a person.
- Used the 5 basic flowchart shapes.
- Drew the same chatbot as a sequence diagram, to compare the two.

## Diagram
![Support chatbot flowchart: answer or escalate](./day02-support-chatbot-flowchart.drawio.svg)

Open the `.drawio.svg` file in Draw.io (or the VS Code Draw.io extension) to edit it.

## How to read it
1. The chatbot works out what the customer wants.
2. **Does it understand?** No → send to a person.
3. **Is it safe to answer?** (billing or complaints are not) No → send to a person.
4. Both Yes → the chatbot answers. Done.

## The 5 shapes
| Shape | Means | Example |
|---|---|---|
| Rounded box | Start or end | "Start", "Resolved" |
| Slanted box | Something comes in or goes out | "Receive question" |
| Rectangle | A step | "Classify intent" |
| Box with side lines | A bigger step with its own details | "Generate answer" |
| Diamond | A yes/no question | "Safe to auto-answer?" |

## Bonus: the same chatbot as a sequence diagram
![Support chatbot sequence: who talks to whom](./day02-support-chatbot-sequence.drawio.svg)

- A flowchart shows **the steps and choices**.
- A sequence diagram shows **who talks to whom, in order**.
- More on choosing between them in [Day 05](../day-05-sequence-notation/README.md#when-to-use-which).

## Lessons
- Each shape has one meaning. Use it the same way every time.
- A diamond asks a question. Label every arrow that leaves it (Yes / No).
- Keep the same direction for the same answer: Yes goes down, No goes right.
- If two paths do the same thing, join them instead of drawing the boxes twice.
- Every path must reach an end.
