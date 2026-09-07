# Jared Silva

**Full-stack developer — TypeScript, Next.js, and the database underneath.**

Software engineering student in Oaxaca, México, building production software for real organizations while I
finish my degree. A nonprofit runs its fundraising auction on something I wrote. A gallery manages 350 artworks
through a panel I built. I care about the part most portfolios skip: what happens after launch, when someone
else has to maintain it.

Open to junior developer roles and internships.

---

## Projects

### 🏠 [Art Auction for a Cause](https://github.com/JaredPS03/TECHO) — [techoax.art](https://www.techoax.art/) · 2026

Built and deployed as a volunteer for **TECHO Oaxaca**. TECHO works across 19 countries and has built housing
with more than 150,000 families in Latin America.

`Next.js 16` · `TypeScript` · `MySQL` · `Tailwind CSS` · `Vercel`

It replaced a process that ran on scattered WhatsApp messages and a handwritten tally of who was winning which
piece. Public catalogue, bid registration with contact details, and an admin panel the team operates without
touching the database — all built against requirements defined with the organization.

The decision worth defending is what I left out. Integrating a payment gateway would have meant fees on donated
money, merchant registration and legal responsibility over other people's funds, for an organization with no
technical staff that already closed deals by phone. So the platform solves what actually hurt — losing track of
bids — and leaves the closing where it already worked.

If you're reviewing the code, look at:

- **Bids resolve inside a transaction with `SELECT ... FOR UPDATE`.** Without it, two simultaneous bids could
  both clear the minimum against the same stale price, and the later write would *lower* it. An auction price
  must never go backwards.
- **The admin session is an HMAC-signed cookie**, compared in constant time. It used to store the admin's raw
  UUID — which proves the id exists, but not that we issued the cookie.
- **A measured 6.26 MB catalogue payload documented as a known limitation**, with the fix and an honest note on
  why it hasn't shipped yet.

### 🖼 Arte de Oaxaca — E-commerce with augmented reality and CMS · 2025

An online store and management panel for a gallery that handles **350 artworks** in catalogue and a history of
**3,000+ inventory and sales records**.

`Next.js` · `TypeScript` · `Tailwind CSS` · `Prisma`

**Inventory reports went from 2–3 hours to 2 minutes**, and manual inventory tracking disappeared entirely. I
also integrated an augmented reality view so buyers can preview a piece on their own wall before committing to
it — the objection that kills most online art sales.

> Delivered to the client; not yet in production, so there is no public demo.

### 🗣 DILLA — Open repository of indigenous languages · 2026 – present

An open, freely accessible platform to collect and preserve the indigenous languages of México, aimed at
research and documentary record.

`Next.js` · `PostgreSQL` · `Prisma` · [dilla-web.vercel.app](https://dilla-web.vercel.app/)

I modelled the PostgreSQL schema with Prisma and built an **asynchronous moderation queue** for user
contributions — necessary because linguistic data submitted by the public needs expert review before it enters a
record intended for research.

### 🍳 [Check — AI Kitchen Assistant](https://github.com/JaredPS03/Che-K) — [che-k.vercel.app](https://che-k.vercel.app/) · 2026

A personal project, and the one to read if you want to see how I actually write and document code: it has the
most complete public codebase, full architecture docs, CI and a test suite.

`Next.js 16` · `TypeScript` · `Neo4j` · `Cypher` · `Google Gemini` · `pytest`

Scan your fridge with the camera, find out what you can cook tonight, and follow the recipe step by step. Built
on a graph database because the domain is a network of relationships, not a hierarchy.

- **Cosine similarity over sparse ingredient vectors, computed entirely in Cypher** — no GDS library, no
  client-side scoring. The same query also returns what you have and what you're missing, so the card renders
  with zero extra round trips.
- **Allergen filtering happens inside the query, before scoring.** A recipe you cannot eat never crosses the
  network.
- **61 unit tests written test-first.** The division-by-zero case was a failing test before it was a guard clause
  in the query.
- The relational-to-graph conversion is documented end to end, starting from the original SQL DDL.

---

## How I work

**I write the "why", not just the "what".** My repos carry architecture docs explaining the decisions and what
they cost — including the ones I'd make differently now.

**I document what's broken.** Every README has a *Known limitations* section with real numbers in it. A project
that admits its weak points is more useful to whoever comes next than one that pretends.

**I turn the safety nets on.** Both public projects started from scaffolding that shipped
`typescript.ignoreBuildErrors: true`. Both now fail the build on a type error, and CI runs type-check, build and
tests on every push.

**I read code before I change it.** The most valuable thing I found in my own auction project was a race
condition nobody had reported yet.

---

## Stack

**Languages** — TypeScript · JavaScript · SQL · Cypher · PHP · HTML/CSS

**Frontend** — React · Next.js (App Router) · Tailwind CSS · Radix / shadcn/ui

**Backend & data** — Node.js · Prisma ORM · PostgreSQL · MySQL · Neo4j · REST APIs · bcrypt & HMAC sessions

**AI** — Google Gemini (vision + text), prompt design and model fallback chains

**Testing & tooling** — pytest · Selenium · Git · GitHub Actions · Vercel

**Currently learning** — advanced SQL (indexes, CTEs, window functions) · Python · React Native · machine learning

---

## Education

**Universidad Autónoma Benito Juárez de Oaxaca** — *B.Eng. in Technological Innovation* · 2023 – 2027
Oaxaca, México · graduating August 2027

Relevant coursework: Data Structures · Algorithms · Databases · Data Science · Artificial Intelligence · OOP ·
Software Engineering

---

## Contact

📧 **silvajared371@gmail.com**

<!-- TODO: replace TU-USUARIO with your LinkedIn handle, then delete this comment line and the closing one so the link renders.
💼 [LinkedIn](https://www.linkedin.com/in/TU-USUARIO)
-->

**Languages:** Spanish (native) · English (B2) · French (basic)

Away from the keyboard, I played basketball for the **Mexican national team** and represented México in
international competition in Colombia. Most of what I know about preparation, losing well and showing up anyway,
I learned there.

Open to junior developer roles. If something here is useful to you, I'd like to hear about it.
