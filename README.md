# Jared Silva

**Full-stack developer — TypeScript, Next.js, and the database underneath.**

I build things that go into production and stay there. Two of my projects are live right now: a charity
art auction running on its own domain for a housing nonprofit, and an AI kitchen assistant built on a graph
database. Both are documented well enough that someone else could pick them up.

Looking for my first full-time role as a junior developer.

---

## Projects

### 🎨 [Art Auction for a Cause](https://github.com/JaredPS03/TECHO) · [techoax.art](https://www.techoax.art/)

A charity auction platform for **TECHO Oaxaca**, a nonprofit that builds progressive housing. It replaced a
process that ran on WhatsApp messages and a handwritten tally of who was winning which piece.

`Next.js 16` `TypeScript` `MySQL` `Tailwind CSS` `Vercel`

The interesting decision was leaving payments out. Integrating a gateway would have meant fees on donated
money, merchant registration and legal responsibility over other people's funds — for an organization with no
technical staff that already closed deals by phone. So the platform solves what actually hurt, losing track of
bids, and leaves the closing where it already worked.

What I'd point a reviewer at:

- Bids resolve inside a transaction with `SELECT ... FOR UPDATE`. Without it, two simultaneous bids could both
  clear the minimum against the same stale price, and the later write would *lower* it. An auction price must
  never go backwards.
- The admin session is an HMAC-signed cookie compared in constant time. It used to store the admin's raw UUID,
  which proves the id exists but not that we issued the cookie.
- The README documents a measured 6.26 MB catalogue payload as a known limitation, with the fix and why it
  hasn't shipped yet.

### 🍳 [Check — AI Kitchen Assistant](https://github.com/JaredPS03/Che-K) · [che-k.vercel.app](https://che-k.vercel.app/)

Scan your fridge with the camera, find out what you can actually cook tonight, and follow the recipe step by
step. Built on a graph database because the domain is a network of relationships, not a hierarchy.

`Next.js 16` `TypeScript` `Neo4j` `Cypher` `Google Gemini` `pytest`

What I'd point a reviewer at:

- Recipe recommendations use **cosine similarity over sparse ingredient vectors, computed entirely in Cypher** —
  no GDS library, no client-side scoring. The same query also returns which ingredients you have and which you
  are missing, so the card renders with zero extra round trips.
- Allergen filtering happens *inside* the query, before scoring. A recipe you cannot eat never crosses the
  network.
- 61 unit tests written test-first. The division-by-zero case was a failing test before it was a guard clause in
  the query.
- The relational-to-graph conversion is documented end to end, starting from the original SQL DDL.

---

## How I work

**I write the "why", not just the "what".** Both repos carry architecture docs that explain the decisions and
what they cost — including the ones I'd make differently now.

**I document what's broken.** Every README has a *Known limitations* section with real numbers in it. A project
that admits its weak points is more useful to the next person than one that pretends.

**I turn the safety nets on.** Both projects started from scaffolding that shipped
`typescript.ignoreBuildErrors: true`. Both now fail the build on a type error, and CI runs type-check, build and
tests on every push.

**I read code before I change it.** The most valuable thing I found in my own auction project was a race
condition nobody had reported yet.

---

## Stack

**Languages** — TypeScript · JavaScript · SQL · Cypher · Python

**Frontend** — React 19 · Next.js 16 (App Router) · Tailwind CSS v4 · Radix / shadcn/ui · Framer Motion

**Backend & data** — Node.js · Next.js Route Handlers · MySQL · Neo4j · REST APIs · bcrypt & HMAC sessions

**AI** — Google Gemini (vision + text), prompt design and model fallback chains

**Testing & tooling** — pytest · Selenium · GitHub Actions · Git · Vercel

---

## Contact

📧 **silvajared371@gmail.com**

<!-- TODO: replace TU-USUARIO with your real LinkedIn handle, then delete this comment and uncomment the line below.
💼 [LinkedIn](https://www.linkedin.com/in/TU-USUARIO)
-->

Open to junior developer roles. If something here is useful to you, I'd like to hear about it.
