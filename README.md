# ArchitecturalDiagrams

A 30-day plan to learn technical and software architecture diagrams, all drawn in **Draw.io**.
Started 2026-11-07 · Target 2026-12-06 · Full tracker: [PROGRESS.md](diagramming-30-days/PROGRESS.md)

## Days done

### Week 1: Foundations ✅
Milestone: redraw the MCP sequence diagram from memory. **Done on Day 07.**

| Day | Topic | What we achieved | Diagrams |
|---|---|---|---|
| [01](diagramming-30-days/day-01-foundations/README.md) | Diagramming foundations | Context sketch of an AI assistant, then a data-flow diagram with an animated step-through player | [context](diagramming-30-days/day-01-foundations/day01-ai-assistant-context.drawio) · [data flow](diagramming-30-days/day-01-foundations/day01-ai-assistant-dataflow.svg) · [player](diagramming-30-days/day-01-foundations/day01-ai-assistant-dataflow-player.html) |
| [02](diagramming-30-days/day-02-flowchart-fundamentals/README.md) | Flowchart fundamentals | Support chatbot flowchart using the 5 basic shapes, plus the same story as a sequence diagram | [flowchart](diagramming-30-days/day-02-flowchart-fundamentals/day02-support-chatbot-flowchart.drawio.svg) · [sequence](diagramming-30-days/day-02-flowchart-fundamentals/day02-support-chatbot-sequence.drawio.svg) |
| [03](diagramming-30-days/day-03-flowchart-refinement/README.md) | Flowchart refinement | Chatbot flowchart v2 with time limit, retries, backup answer and hand-off to a person | [flowchart v2](diagramming-30-days/day-03-flowchart-refinement/day03-support-chatbot-flowchart-v2.drawio.svg) |
| [04](diagramming-30-days/day-04-sequence-foundations/README.md) | Sequence foundations | First full sequence diagram: "My orders" request through Gateway → Auth → Orders → DB | [sequence](diagramming-30-days/day-04-sequence-foundations/day04-orders-request-sequence.drawio.svg) |
| [05](diagramming-30-days/day-05-sequence-notation/README.md) | Sequence notation | MCP sequence v1 (sync, async, notes, numbering) + the same story as a flowchart | [sequence v1](diagramming-30-days/day-05-sequence-notation/day05-mcp-sequence-v1.drawio.svg) · [flowchart](diagramming-30-days/day-05-sequence-notation/day05-mcp-flowchart.drawio.svg) |
| [06](diagramming-30-days/day-06-sequence-control-flow/README.md) | Sequence control flow | MCP sequence v2 with `loop`, `alt` and `ref` boxes for errors, timeouts and the tool limit | [sequence v2](diagramming-30-days/day-06-sequence-control-flow/day06-mcp-sequence-v2.drawio.svg) |
| [07](diagramming-30-days/day-07-week1-review/README.md) | Week 1 review | MCP sequence v3 redrawn from memory, with 5 improvements over v1 | [sequence v3](diagramming-30-days/day-07-week1-review/day07-mcp-sequence-v3.drawio.svg) |

### Week 2: Diagram types
Milestone: a three-diagram mini design pack.

| Day | Topic | What we achieved | Diagrams |
|---|---|---|---|
| [08](diagramming-30-days/day-08-drawio-workflow/README.md) | Draw.io workflow | One `.drawio` file with 2 pages (flowchart + sequence), 3 layers, tooltips, page links and PNG exports | [source](diagramming-30-days/day-08-drawio-workflow/day08-chatbot-pack.drawio) · [flowchart](diagramming-30-days/day-08-drawio-workflow/day08-flowchart.png) · [sequence](diagramming-30-days/day-08-drawio-workflow/day08-sequence.png) |
| [09](diagramming-30-days/day-09-sequence-patterns/README.md) | Sequence patterns | Production-style LLM tool-call sequence (7 participants), with intent kept apart from execution | [sequence](diagramming-30-days/day-09-sequence-patterns/day09-llm-tool-call-sequence.drawio.svg) |
| [10](diagramming-30-days/day-10-flowchart-patterns/README.md) | Flowchart patterns | Left-to-right RAG request flowchart in 4 stages, with a no-results fallback and offline ingestion kept separate | [flowchart](diagramming-30-days/day-10-flowchart-patterns/day10-rag-request-flowchart.drawio.svg) |
| [11](diagramming-30-days/day-11-class-diagrams/README.md) | Class diagrams | Agent / Tool / ToolCall / ToolResult / Message classes with 4 relationship types and multiplicity, built around one design question | [class diagram](diagramming-30-days/day-11-class-diagrams/day11-agent-tool-classes.drawio.svg) |
| [12](diagramming-30-days/day-12-er-diagrams/README.md) | ER diagrams | Conversation storage ERD: 5 tables with PK / FK / UQ keys and crow's-foot cardinality | [ERD](diagramming-30-days/day-12-er-diagrams/day12-conversation-erd.drawio.svg) |

### Week 3: Visual design
Milestone: a polished Agentic AI architecture. *Not started.*

### Week 4: Real-world architecture
Milestone: an enterprise knowledge assistant pack. *Not started.*

## How to open the diagrams
`.drawio` and `.drawio.svg` files open in [draw.io](https://app.diagrams.net) or the VS Code Draw.io extension. The `.drawio.svg` files also show as normal images on GitHub.
