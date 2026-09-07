# Jared Silva

Engineering student in Oaxaca, México. I build web applications with TypeScript and Next.js, usually with a
database doing the interesting part.

Most of what I've built has been for people outside a classroom: a fundraising auction for a nonprofit, a
management panel for an art gallery, an open archive for indigenous languages. I'm still learning, and the
projects below are the honest state of that.

Open to junior developer roles and internships.

---

## Projects

### 🏠 [Art Auction for a Cause](https://github.com/JaredPS03/TECHO) — [techoax.art](https://www.techoax.art/) · 2026

Built and deployed as a volunteer for **TECHO Oaxaca**, part of an organization that works across 19 countries
and has built housing with more than 150,000 families in Latin America.

`Next.js 16` · `TypeScript` · `MySQL` · `Tailwind CSS` · `Vercel`

It replaced a process that ran on scattered WhatsApp messages and a handwritten tally of who was winning which
piece. Public catalogue, bid registration with contact details, and an admin panel the team operates without
touching the database — built against requirements defined with the organization.

There is no payment gateway, and that was on purpose. It would have meant fees on donated money, merchant
registration and legal responsibility over other people's funds, for an organization with no technical staff
that already closed deals by phone. The platform handles the part that was actually failing — keeping track of
bids — and leaves the rest where it worked.

A few things in the code I'd point at:

- Bids are resolved inside a transaction using `SELECT ... FOR UPDATE`. Without it, two people bidding at the
  same time could both clear the minimum against the same stale price, and the second write would lower it.
- The admin session cookie is signed with HMAC and compared in constant time. It used to store the admin's UUID
  as-is, which proves the id exists but not that the cookie came from us.
- The README documents a measured 6.26 MB catalogue payload as a known limitation, along with the fix I haven't
  shipped yet.

### 🖼 Arte de Oaxaca — E-commerce with augmented reality and CMS · 2025

An online store and management panel for a gallery handling **350 artworks** in catalogue and a history of
**3,000+ inventory and sales records**.

`Next.js` · `TypeScript` · `Tailwind CSS` · `Prisma`

Inventory reports went from taking 2–3 hours to about 2 minutes, and the manual inventory tracking went away. I
also integrated an augmented reality view so a buyer can see a piece on their own wall before deciding.

> Delivered to the client; not yet in production, so there's no public demo.

### 🗣 DILLA — Open repository of indigenous languages · 2026 – present

An open, freely accessible platform to collect and preserve the indigenous languages of México, aimed at
research and documentary record.

`Next.js` · `PostgreSQL` · `Prisma` · [dilla-web.vercel.app](https://dilla-web.vercel.app/)

I modelled the PostgreSQL schema with Prisma and built an asynchronous moderation queue for user contributions,
since submissions need review before they become part of a record meant for research.

### 🍳 [Check — AI Kitchen Assistant](https://github.com/JaredPS03/Che-K) — [che-k.vercel.app](https://che-k.vercel.app/) · 2026

A personal project. It has the most complete public codebase of the four, so it's probably the easiest one to
actually read.

`Next.js 16` · `TypeScript` · `Neo4j` · `Cypher` · `Google Gemini` · `pytest`

Scan your fridge with the camera, see what you can cook tonight, and follow the recipe step by step. I used a
graph database because the data is mostly relationships — a user has ingredients, a recipe requires them.

- Recipe matching is cosine similarity over sparse ingredient vectors, written entirely in Cypher. The same
  query returns which ingredients you have and which you're missing, so the card renders without a second
  request.
- Allergen filtering happens inside the query rather than on the client, so a recipe you can't eat is never sent.
- 61 unit tests covering the matching algorithm, including the empty-pantry and division-by-zero cases.
- The conversion from the original relational schema to the graph model is documented step by step.

---

## How I try to work

Nothing here is a principle I arrived with. They're all habits I picked up after doing the opposite first.

**Writing down why, not just what.** Coming back to my own code a few weeks later, I couldn't remember why I'd
picked a graph database over Postgres. Now the reasoning goes in a doc next to the code, so the next person —
often me — doesn't have to guess.

**Saying what doesn't work yet.** My READMEs have a "known limitations" section. It started as a note to myself
so I wouldn't forget the rough edges, and it's ended up being the part people ask about.

**Leaving the checks turned on.** Both public projects came from scaffolding with
`typescript.ignoreBuildErrors: true`. Turning it off surfaced two real errors I'd been shipping without noticing,
one of them an import of a module that didn't exist.

**Reading before changing.** I found a race condition in the auction's bidding while writing documentation for
it, not while building it. Explaining code slowly is how I catch what I missed the first time.

---

## Stack

**Languages** — TypeScript · JavaScript · SQL · Cypher · PHP · HTML/CSS

**Frontend** — React · Next.js (App Router) · Tailwind CSS · Radix / shadcn/ui

**Backend & data** — Node.js · Prisma ORM · PostgreSQL · MySQL · Neo4j · REST APIs

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

Outside of this, I played basketball for the Mexican national team and represented México in an international
competition in Colombia.

If something here is useful to you, I'd be glad to hear about it.
