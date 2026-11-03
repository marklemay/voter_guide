# Voting guide rules

Output: `malden-w3p2-<election>.md` + optional wordy `...-notes.md`. No version suffixes; revisions go in git commits.

## Coverage
- Every race with >1 candidate, counting declared write-ins. Omit truly uncontested races entirely (no "uncontested" section).
- Ballot source of truth: Malden's sample-ballot PDF (cityofmalden.org/1348 election page, per state-rep district; W3P2 = 33rd Middlesex). Cache it in `ballots/` and link it from the guide header. Read it with the Read tool (pdf text extraction fails on the CJK fonts). SoS viewer blocks scripts.

## Content priority
1. Debates / forums: link straight to the playable recording (YouTube, CBS video page, etc.), never to an article about it. Verify YouTube titles via `https://www.youtube.com/oembed?url=...&format=json`; GBH "what you need to know" videos are explainers, not debates — label them so. No debate → `No debate: [who refused](evidence)` in a few words,. If nothing found, write nothing. This is most of the value.
2. Primary sources: official text, candidate sites, filings, poll releases.
3. Endorsements: ONLY high-quality secondary — Boston Globe editorial board, ACX community guide (Greater Boston, posted in ACX open threads). Never politicians or advocacy orgs.
4. Analysis only if it links to the specific finding and the finding is not marginal. Else omit.

## Do not include
- Win / pass probabilities.
- Prose summaries of analysis. A link label of 1–3 words is enough.
- Null statements ("No debate found", "no refusal on record"). Absence speaks for itself.
- Links to pages with no relevant info (empty aggregator profiles, AI meeting summaries, bot-walled pages). No link beats a bad link.
- Explanatory boilerplate (what "tie" means, links to notes, poll roundups in header). Header is just the ballot link.

## Format
- Races and questions in ballot order.
- Every race gets a tie probability (best guess if no data; math lives in notes file). Effort ∝ tie probability: close races get more digging, landslides get one line.
- Link labels terse: `[debate Oct 21](url)`, not sentences.
- Every factual claim is a link to its evidence.
