# Jared Silva

Engineering student in Oaxaca, México. I build web applications with TypeScript and Next.js, usually with a
database doing the interesting part.

Most of what I've built has been for people outside a classroom: a fundraising auction for a nonprofit, a
management panel for an art gallery, an open archive for indigenous languages. I'm still learning, and the
projects below are the honest state of that.

Open to junior developer roles and internships.

---

## Projects

### 🖼 Arte de Oaxaca — E-commerce with augmented reality and CMS · 2025 https://www.artedeoaxaca.com.mx/

An online store and management panel for a gallery handling **350 artworks** in catalogue and a history of
**3,000+ inventory and sales records**.

`Next.js` · `TypeScript` · `Tailwind CSS` · `Prisma`

Inventory reports went from taking 2–3 hours to about 2 minutes, and the manual inventory tracking went away. I
also integrated an augmented reality view so a buyer can see a piece on their own wall before deciding.

> Delivered to the client; not yet in production, so there's no public demo.

### 🗣 DILLA — Open repository of indigenous languages · 2026 – present https://www.dilla.com.mx/

An open, freely accessible platform to collect and preserve the indigenous languages of México, aimed at
research and documentary record.

`Next.js` · `PostgreSQL` · `Prisma`

I modelled the PostgreSQL schema with Prisma and built an asynchronous moderation queue for user contributions,
since submissions need review before they become part of a record meant for research.


### Sistema a medida de contabilidad, contratos, administración de piezas, etc e inventario Autos Alianza Seminuevos https://alianzaseminuevos.com/


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

**Languages** — TypeScript · JavaScript · SQL · Cypher · PHP · HTML/CSS • python

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

**Languages:** Spanish (native) · English (B2) · French (A2)

Outside of this, I played basketball for the Mexican national team and represented México in an international
competition in Colombia.

If something here is useful to you, I'd be glad to hear about it.
