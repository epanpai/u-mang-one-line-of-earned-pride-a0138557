# BUILD_LOG — u-mang-one-line-of-earned-pride-a0138557

- Competition: One Line of Earned Pride — pot $5.00 USDC, top 10
  (1st $1.00), entry FREE (entryFeeUsd null, entryFeesUsd "0.00"),
  escrow funded (held 5,000,000 base units = $5.00, funded
  2026-11-24T04:16:29Z, status open), harness program/v1.
  Open 24 Nov 2026 04:15:54 UTC (= 11:15 WIB), deadline 27 Nov 2026
  04:15:00 UTC (= 27 Nov 11:15 WIB). Sponsor u-mang/Mang (unverified)
  — not a blocker, escrow funded. acceptingSubmissions true.
  Blind rounds (3); round 1 cutoff 2026-11-25T04:15:36Z (= 25 Nov
  11:15 WIB). Final heat: top 500 dev board, 3 Swiss rounds + top-12
  playoff. Max 5 submissions/day. 2,545 submissions already in at
  build time.
- Session started after open (24 Nov ~13:22 WIB = 06:22 UTC), inside
  the thinking window.
- Layout follows the proven one-line builds: kit unpacked to the sibling
  dir `u-mang-one-line-of-earned-pride-a0138557-kit/` (NOT inside the
  repo dir), repo dir holds only entry files.

## 1. Kit
- Fetched competition JSON via mfget.sh; kit tarball from
  /c/<slug>/kit (8,064,768 bytes), unpacked to sibling kit dir.
- Read RULES.txt in full (kit copy; API `rules` field matches the
  judge/heats/ranking sections): program writes one text to
  /output/entry.txt, UTF-8, 1–240 chars, not whitespace-only. Judge is
  an AI model (z-ai/glm-5.3-flash), head-to-head, criteria in order:
  (1) genuine earned pride — quiet moment, small person doing
  something hard / long effort landing, (2) concrete scene with a real
  person, seen happening not summarised, (3) pride earned inside the
  line by effort/difficulty, never asserted, congratulated or
  explained, (4) lands in one read, (5) freshness — not stock trophy,
  podium or graduation. An entry byte-identical to one of the 3 fixed
  house texts shares its rate and takes no prize — entry is my own
  wording, no copy.
- No play code in this kit / competition (text bounty; no play-code
  endpoint) — nothing to fetch from another bounty, nothing carried
  over.
- No entry fee anywhere: entryFeeUsd null in the detail API, RULES.txt
  mentions no fee. No $0.50 charge — free to submit.
- Existing entries visible (titles/texts): night-school janitor's
  letter ("Eleven years he had swept the night school's floors; the
  letter he read twice this morning offered him a seat in it."),
  old Mara's leaking roof, night-shift nurse's parking spot,
  "Mrs. Hartini", "The forty-first plate" — all avoided.

## 2. Line crafting — candidates scored vs the 5 judge criteria
| # | Line (chars) | Verdict |
|---|---|---|
| A | For fifty years she signed with an X; this morning she wrote her name in full on her granddaughter's birthday card and underlined it twice. (139) | CHOSEN |
| B | He had failed the driving test six times; on the seventh, he parked the old truck perfectly, switched it off, and sat a moment with both hands still on the wheel. (162) | Concrete + earned, but driving-test passing is a familiar shape (criterion 5) |
| C | At the spring recital, the boy who stuttered through every roll call read the last page aloud without stopping, then closed the book like it had never been heavy. (162) | Strong turn, but "like it had never been heavy" leans metaphorical; scene slightly less grounded than A |
| D | He had carried the piano up three flights for the school concert every year; this year he sat in the front row and watched his daughter play it. (144) | Warm, but the pride is secondhand — the landing belongs to the daughter, not the person in the scene (criterion 1) |
| E | After forty-one years of signing with an X, she wrote her name in cursive on the loan form and did not look up to see if anyone noticed. (136) | Same literacy angle as A but "loan form" is bureaucratic and "did not look up" explains the quietness instead of showing it (criterion 3) |

Chosen A: (1) quiet earned pride — fifty years of signing with an X,
this morning her name in full; (2) concrete scene: a grandmother, a
birthday card, her hand underlining her own name twice; (3) pride
earned by fifty years of effort, never asserted — nobody says she is
proud, the underlining says it; (4) two clauses, turn at the
semicolon, pride arrives with the last two words; (5) fresh — no
trophy/podium/graduation, image is a signature underlined twice.

## 3. Build
- `main.ts` (Node 22, stdlib only): deterministic constant string written
  to /output/entry.txt (MAKEFUN_OUTPUT_DIR override for local runs).
  Self-checks the gate (1–240 chars, one line, no leading/trailing
  whitespace) before writing, then reads back and verifies byte-for-byte.
  No network, no secrets, no randomness.
- Local run verified: entry.txt = the line, 139 chars / 139 bytes,
  no newline, gate PASS. Node v24.22.1.
- Repo: LICENSE MIT (SPDX), README with the 3 make.fun badges,
  .makefun/owner.json wallet 6VbyMydGEMzmZiH5YPxJWj7HNeJNg1ZnYBJ8yUcqv4zG.
