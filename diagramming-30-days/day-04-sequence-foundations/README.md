# Day 04 — Sequence diagram foundations

## What we did
- First full sequence diagram: a user opens **"My orders"**, and the request passes through Browser → API Gateway → Auth Service → Orders Service → Orders DB and back.
- Six participants, 11 numbered messages, and nested activation bars that show who is waiting on whom.
- Only the **happy path** is drawn. Error branches (401, DB timeout) come in Day 06 with `alt` frames.

## Diagram
![Sequence: Browser → API Gateway → Auth Service → Orders Service → Orders DB](./day04-orders-request-sequence.drawio.svg)

Open the `.drawio.svg` in Draw.io (or the VS Code Draw.io extension) to edit it. The editable model is embedded in the SVG.

## The five Day 04 concepts
### 1. Participants
- One **column per participant**. A participant is anything that sends or receives a message: a person, a browser, a service or a database.
- Order the columns left → right **in the order they are first called**. Most arrows then point right on the way in and left on the way back, and none of them cross.
- Name each participant by its **role**, and put the technology on a second line when it matters ("Orders DB / PostgreSQL").
- Draw.io: *More shapes → UML → Lifeline* (`shape=umlLifeline`). Set `participant=umlActor` for a person.

| Participant | Colour | Role in this flow |
|---|---|---|
| User (actor) | grey | Starts the interaction |
| Browser (web app) | blue | Turns the click into an HTTP call and renders the result |
| API Gateway | yellow | Single entry point: checks auth, then routes |
| Auth Service | red | Validates the JWT and returns the identity. It never sees orders. |
| Orders Service | green | Business logic: loads and shapes the orders |
| Orders DB | purple | Stores the data |

### 2. Lifelines
- The **dashed vertical line** under each header is that participant's life during this scenario.
- A lifeline does nothing by itself. It only marks where messages start and end.

### 3. Messages (calls)
- A **solid line with a filled arrowhead** is a request. Label it with the operation and its key data: `GET /orders (Bearer JWT)`, `getOrders(userId)`.
- A **self-message** (⑧ map rows → DTOs) loops back to the same lifeline. Use it for internal work worth showing, and give it a nested activation bar.
- Use the protocol's vocabulary at each hop: HTTP verbs at the edge, method names between services, a short SQL intent at the DB.

### 4. Return messages
- A **dashed line with an open arrowhead** is a reply. Label it with **what comes back**, not "return": `valid: userId, scopes`, `rows`, `200 OK + orders`.
- Every call gets a reply here because all of them are synchronous. Calls ③/④, ⑤/⑨ and ⑥/⑦ form matching pairs.
- Colour backs up the line style: blue = request, green = reply.

### 5. Time ordering
- **Time runs down.** A message lower on the page happens later. The numbers ①…⑪ repeat that order so it can be read aloud in a review.
- **Activation bars** (the white rectangles) show when a participant is busy. The bars nest: Browser's bar contains API's bar, which contains Orders Service's bar. That means **each caller waits** until the call it made returns.
- The gap between ④ and ⑤ on the API Gateway bar shows that the gateway finishes auth *before* it routes the request.

## Message table
| # | From → To | Message | Type |
|---|---|---|---|
| ① | User → Browser | click "My orders" | call |
| ② | Browser → API Gateway | GET /orders (Bearer JWT) | call |
| ③ | API Gateway → Auth Service | validate(JWT) | call |
| ④ | Auth Service → API Gateway | valid: userId, scopes | reply |
| ⑤ | API Gateway → Orders Service | getOrders(userId) | call |
| ⑥ | Orders Service → Orders DB | SELECT orders by user_id | call |
| ⑦ | Orders DB → Orders Service | rows | reply |
| ⑧ | Orders Service → itself | map rows → DTOs | self-call |
| ⑨ | Orders Service → API Gateway | orders[ ] (JSON) | reply |
| ⑩ | API Gateway → Browser | 200 OK + orders | reply |
| ⑪ | Browser → User | render order list | reply |





