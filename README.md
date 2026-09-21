# Kausik

I study at VIT Chennai and I build the software my own semester needs. Most of
it sits on top of VTOP and Moodle, because that is where the data lives and it
isn't going to turn into a usable app by itself.

## UltraCC — VIT Student OS

Attendance, timetable, internal marks, exam slots, LMS coursework, FFCS
planning and campus services (bus routes, library catalogue, clubs,
previous-year papers) in one installable PWA.

- React 19 and TypeScript on Vite, Supabase Postgres and Edge Functions behind
  it, Vitest for the tests.
- VTOP and Moodle logins are posted from edge functions, so your password never
  goes to a browser-originated request. The session the browser does hold is
  AES-GCM encrypted and memory-only.
- Normalised academic data is cached in IndexedDB so the app opens on a hostel
  floor with one bar of signal. The service worker is versioned per build,
  because a stale shell referencing deleted chunks is the worst failure an
  offline-first app can have.
- The Q-Bank lists 3,100+ previous-year papers from
  [CodeChef-VIT's archive](https://github.com/CodeChefVIT/papers-codechef).
  Their sync job copies metadata into Postgres and nothing else — the PDFs stay
  on CodeChef-VIT's storage and each entry links back out.

### What the tests argue about

There are 59 test files under `src`, and the ones worth reading are named after
complaints I actually received:

- `errorCopy.test.ts` checks that machine-authored error strings get replaced
  with copy a person wrote, while real failures stay visible.
- `upstreamIsolation.test.ts` fails the build if a data source's hostname ever
  shows up in frontend code.
- `railLayout.test.ts` pins the nav rail's collapsed and expanded widths, and
  the offset of the content next to it, so the collapse toggle can't vanish.
- `naming.test.ts` requires the desktop rail and the mobile menu to offer the
  same destinations under the same labels.
- `phoneIdentity.test.ts` separates "that number is invalid" from "you are
  talking to a stale deployment" from "the server is genuinely down".
- `cabshareOwnership.test.ts` makes sure the app never hands out a share code
  for somebody else's ride listing.
- `pyqAttribution.test.ts` fails if the paper archive loses its credit line or
  a PDF sneaks into the repo.

Where VTOP has nothing, the app says it has nothing. An ungraded internal
assessment displays as ungraded instead of quietly averaging over an empty set.

## Campusly

A separate, iPhone-first student PWA: day timetable with current-class state,
attendance analytics, GPA trajectory, assignments, notes, a `⌘K` command
palette, offline app-shell caching and Supabase Auth. It is where I work out
what a campus app feels like when it is designed to be opened with one thumb.

## Before that

[Atom's Music](https://github.com/TGFUKAUSIK/Atom-s-Music) — a Discord music bot
on erela.js and discord.js v13, published in 2022, along with a set of Lavalink
bot forks I took apart to see how they handled sessions and queues. Reading
other people's bot code is how I picked up Node, WebSockets, and the difference
between polling a REST endpoint and holding a connection open.

## Elsewhere

Discord: `TGFU KAUSIK#0007`. Otherwise, the issues tab of whichever repository
you found me from.

<!---
TGFUKAUSIK/TGFUKAUSIK is a ✨ special ✨ repository because its `README.md`
(this file) appears on your GitHub profile.
--->
