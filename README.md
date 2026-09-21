# Kausik

VIT Chennai. I build web apps students actually open between classes — and I
sweat the unglamorous parts: honest empty states, requests that time out instead
of hanging, and academic data that never leaves the device it belongs on.

## Now building

### [UltraCC](https://github.com/TGFUKAUSIK/UltraCC) — VIT Student OS

Attendance, timetable, marks, exams, LMS coursework, FFCS planning and campus
services in one installable PWA on top of VTOP and Moodle.

- **Nothing is invented.** Where the university publishes no data, the UI says
  so instead of filling the gap — a rule pinned by tests, not good intentions.
- **Credentials stay server-side.** VTOP and LMS authentication run through
  Supabase Edge Function gateways; the session is AES-GCM encrypted and lives in
  browser memory only. No cookies, CSRF tokens or marks in logs.
- **Survives a bad campus network.** Normalised academic data caches in
  IndexedDB, and the service worker is versioned per build so a stale deploy
  can't serve a broken shell.
- **Reminders outlive the browser tab** through scheduled Web Push, dispatched
  in-database, with delivery health reported honestly in Settings.
- **Question bank** of 3,100+ previous-year papers, mirrored server-side from
  [CodeChef-VIT's archive](https://github.com/CodeChefVIT/papers-codechef) (MIT).
  Metadata only — every paper opens from the source's own link.
- React 19 · TypeScript · Vite · Supabase Postgres and Edge Functions · Vitest.

### [Campusly](https://github.com/TGFUKAUSIK/campusly)

An iPhone-first student super-app: day timetable with current-class state,
attendance analytics, GPA trajectory, assignments, notes, a global `⌘K` command
palette, offline app-shell caching and Supabase Auth. Written from scratch as a
PWA that is meant to feel native.

## Started here

[Atom's Music](https://github.com/TGFUKAUSIK/Atom-s-Music) — a Discord music bot
on erela.js and discord.js v13, published in 2022. Around it sits a trail of
forked Lavalink bots I took apart to work out how they did it. Reading other
people's bots turned into writing the gateways, parsers, migrations and test
suites myself.

## How I work

- A bug report is a missing test: reproduce it, then pin the behaviour that broke.
- Empty is a real state, and so is *unavailable*. Neither gets an endless spinner.
- Mobile is the default rather than the fallback — this ships to phones.
- Facts before guesses: read the actual response before changing the code.

## Stack

TypeScript · React · Vite · PWA and Service Workers · Supabase (Postgres, Edge
Functions) · Express · Vitest · Node

Find me in the issues of whatever you're using, or on Discord as
`TGFU KAUSIK#0007`.

<!---
TGFUKAUSIK/TGFUKAUSIK is a ✨ special ✨ repository because its `README.md`
(this file) appears on your GitHub profile.
--->
