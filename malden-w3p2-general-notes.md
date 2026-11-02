# Notes: Nov 3, 2026 general guide (LLM working file)

This is the long companion to `malden-w3p2-general.md`. It covers how each number was derived, which judgment calls went into them, what I couldn't verify, and where I'd push back on my own estimates.

Compiled 2026-11-01.

---

## 1. What I interpreted the brief to mean

- "Focus on races inversely proportional to their chance of tie." Read literally, this would mean "spend the most effort on landslides," which makes no sense for a voting guide. I took it as **spend effort in proportion to tie probability**: the races most likely to be decisive get the most detail. That's why the guide is sorted by P(tie), closest first, and the near-zero races are collapsed into one-liners.
- The style follows the primary guide (`malden-w3p2-primary-v5.md`): headers, bare links, and one bolded estimate per race. For ballot questions, "candidates" became Yes and No, and "win probability" became "pass probability."
- Sources are mostly primary or near-primary: official ballot text (omniballot, SoS), Tufts cSPA reports (the nonpartisan analysis the media cites), the polls themselves, OCPF-derived finance coverage, and the Globe editorial board as the high-quality secondary endorser. The ACX Greater Boston community guide (Open Thread 456) was found in a second pass. Somerville YIMBY is included as an advocacy source on Q7 because it's local, but it is plainly partisan on the question.

## 2. Local races

The full office list came from Reading's printed sample ballot for Pcts 1, 7 and 8. Reading shares Gov Council 6, the 5th Middlesex Senate seat, DA Northern, Middlesex county and the Northeast Metro Tech district with Malden. The SoS viewer blocks scripts.

- **Contested:** Register of Probate (DeCristofaro D vs Martorella, Justice for All), and Northeast Metro Tech School Committee, Malden seat (Perry vs Salazar).
- **Uncontested, no write-in found:** Gov Council 6 (Kennedy), 5th Middlesex Senate (Lipper-Garabedian), DA Northern (Ryan), 33rd Middlesex Rep (Ultrino). Left out of the guide.
- **MA-5:** Clark, plus a declared write-in, Derek Fleming (Politics1).
- **Non-binding questions:** the ACX guide lists which rep districts get them, and the 33rd Middlesex isn't one.

### Northeast Metro Tech, the most decisive race on the ballot
Every voter in the 12 member towns votes on each town's seat: Chelsea, Malden, Melrose, North Reading, Reading, Revere, Saugus, Stoneham, Wakefield, Winchester, Winthrop and Woburn. I'd put total ballots at ~250k, with heavy roll-off on an obscure race, so N ≈ 150k votes cast in it. There's no polling and no party label. Salazar is the appointed incumbent (Malden School Committee, Jan 28, split vote), a union CTE teacher, with letters in the Reading papers. Perry has no web presence beyond the filing, but his name is printed first on the ballot. Incumbency is not printed for this race. I set m = +.15 for Salazar and s = .25 (essentially no information) → P(tie) ≈ 1.8×10⁻⁵ = 10⁻⁴·⁷. That's about 10× more decisive than any statewide question.

### Register of Probate
Countywide, N ≈ 800k. A minor-party challenger with ~$2k raised. m = .45, s = .12 → 10⁻⁸·¹.

### MA-5 write-in
m ≈ .95, s = .05 → 10⁻⁸². It's in the guide only because the rule is that every race with more than one candidate gets listed.

## 3. The tie model (same as the primary appendix)

P(tie) ≈ (2/N) · φ(m/s) / s

- m = expected two-way margin (yes share − no share, as a fraction of decided votes)
- s = sd of my forecast error on that margin
- N = 2.6M for every statewide item. MA 2022 midterm turnout was ~2.5M, and 2026 has a competitive-sounding ballot plus record question count. Ballot-question roll-off (blanks) cuts effective N by perhaps 5–10% on lower-salience questions, which raises P by the same 5–10%. Immaterial.

| race | m | s | m/s | φ | pass/win | P | log₁₀ |
|---|---|---|---|---|---|---|---|
| Q3 | −.02 | .12 | −.17 | .393 | 43% | 2.5×10⁻⁶ | −5.6 |
| Q5 | +.02 | .15 | .13 | .395 | 55% | 2.0×10⁻⁶ | −5.7 |
| Q7 | +.10 | .15 | .67 | .319 | 75% | 1.6×10⁻⁶ | −5.8 |
| Q6 | +.20 | .15 | 1.33 | .164 | 91% | 8.4×10⁻⁷ | −6.1 |
| Treasurer | +.41 | .12 | 3.46 | .0010 | >99.9% | 6.5×10⁻⁹ | −8.2 |
| Q2 | +.25 | .15 | 1.67 | .0995 | 95% | 5.1×10⁻⁷ | −6.3 |
| Q4 | +.25 | .12 | 2.08 | .0455 | 98% | 2.9×10⁻⁷ | −6.5 |
| Q9 | +.30 | .12 | 2.50 | .0175 | 99.4% | 1.1×10⁻⁷ | −6.9 |
| Q8 | −.33 | .12 | −2.75 | .0091 | 0.3% | 5.8×10⁻⁸ | −7.2 |
| AG / Sec | +.30 | .10 | 3.00 | .0044 | 99.9% | 3.4×10⁻⁸ | −7.5 |
| Governor | +.26 | .08 | 3.25 | .0020 | 99.9% | 2.0×10⁻⁸ | −7.7 |
| Q1 | +.45 | .12 | 3.75 | .00035 | >99.9% | 2.3×10⁻⁹ | −8.6 |
| Senate | +.31 | .08 | 3.88 | .00022 | >99.9% | 2.1×10⁻⁹ | −8.7 |
| Auditor | +.50 | .10 | 5.00 | 1.5×10⁻⁶ | ~100% | 1.1×10⁻¹¹ | −10.9 |
| NE Metro Tech SC | +.15 | .25 | 0.60 | .333 | — | 1.8×10⁻⁵ (N=150k) | −4.7 |
| Register of Probate | +.45 | .12 | 3.75 | .00035 | — | 7.3×10⁻⁹ (N=800k) | −8.1 |

Here pass/win = Φ(m/s), so the pass probabilities are fully consistent with the tie figures this time. In the primary guide they were set separately.

Note how flat the top of the table is. Q3, Q5 and Q7 sit within a factor of ~1.5 of each other, and Q6 and Q2 within another factor of ~2. Given how uncertain s is, **treat the top three as tied for "most decisive," and the next two as about half as decisive.**

## 4. How I set m and s for each close item

### The core problem: two polls a mile apart

| | Suffolk/Globe (Oct 14–18, n=500, ±4.4) | UMass Amherst/YouGov/WCVB (Oct 5–12, n=800, ±4.2) |
|---|---|---|
| Q3 | 46–41 (10 und) | 49–39 |
| Q5 | 40–38 (20 und) | 58–20 (21 und) |
| Q6 | 49–39 | 70–19 |
| Q7 | 41.2–40.6 | 65–21 |
| Gov | Healey 59–36 | Healey 57–32 |

The two polls agree on the governor's race and on Q3. They disagree by 30–45 points of margin on Q5, Q6 and Q7. That can't be sampling error. It's question wording and mode: YouGov is an online opt-in panel, and its ballot-question prompts are often shorter and friendlier, while Suffolk is live phone and probably reads closer to the official ballot text. Suffolk's director noted that undecideds tend to break toward the status quo (No) on ballot questions. That's the well-known ballot-question pattern: support for a change erodes as Election Day nears and opponents spend.

So I didn't average naively. My rules:

- I weight Suffolk more heavily on the questions where the wording matters (Q5 and Q7 both have abstract mechanics).
- I apply a status-quo drift of a few points toward No.
- I use Kalshi as a sanity anchor, because markets have seen both polls. The prices I have are from undated search snippets that conflicted (Q3 at 32 and at 41), so they're soft.
- s = .15 on the questions where the polls disagree (Q5, Q6, Q7, Q2) and .12 on those where they roughly agree.

### Q3 — all-party primary
Polls: +5 and +10 for Yes. Kalshi: 32–41. Both party establishments, organized labor, Healey and Minogue all oppose it. Yes outspends heavily ($5.8M spent, the 2nd most of any question). The relevant precedent is 2020's ranked-choice question (Q2 2020), which polled near even and lost 45–55. Structural election-reform questions lose ground late. I set m = −.02 (a slight No lean), s = .12 → 43%. A reasonable person could put this at 35–50%. **It doesn't matter much for P(tie) anyway**: near m = 0, φ is flat, so any m within ±.05 gives log₁₀ P ≈ −5.6.

### Q5 — 62F rebase
Polls: +2 and +38. Kalshi: 45. Tax-refund questions are popular in the abstract ("keep more of your money") and the opposition message is technical ("budget instability"), which argues Yes. But the opposition is the Raise Up labor coalition, which won the 2022 surtax fight and has money and a field operation. Suffolk's 20% undecided is large, and its drift should run No. I set m = +.02, s = .15 → 55%. This is my lowest-confidence pass estimate.

### Q7 — starter homes
Polls: 0 and +44. Kalshi: 75. Endorsements are broad on Yes (Globe, Healey, Wu, Pioneer on the right, YIMBY and DSA groups on the left), and organized opposition is mostly the Municipal Association, a weak, low-money opponent. I went with Kalshi: m = +.10, s = .15 → 75%. The Suffolk 41–41 result is the strongest counterevidence. If Suffolk is right and undecideds break No, this fails narrowly.

### Q6 — conservation fund
Polls: +10 and +51. No organized No campaign. A well-funded Yes coalition, with Healey strongly for it. The Globe's No vote (on budget earmarking) is the main elite dissent. m = +.20, s = .15 → 91%.

### Treasurer
Suffolk Oct 14–18: Goldberg 58, Dionne 24, 17 undecided (via WWLP). m = 34/82 = .41, with s = .12 because it is a single poll → 10⁻⁸·². This replaces the earlier no-poll guess of m = .20 (10⁻⁶·²).

### Everything else
These all have m/s > 2. As the primary appendix warned, the normal tail is doing the work there, so **the log₁₀ P values from Q4 downward are lower bounds**. Fat tails would push them up, but not into contention with the top six.

## 5. Funding

Per-question totals are hard to get. OCPF can't split multi-question committees by question (OCPF spokesperson via Boston.com, Oct 19). Known figures: $25M+ raised and $22.1M spent across 21 committees; Q8 has the most spent ($6.3M), Q3 is 2nd ($5.8M). The Coalition for Healthy Democracy (Yes on Q1 and Q3) was the single largest committee as of early September (~$2.9M raised). The raw data is at ocpf.us/Data/BallotQuestionsElection, which I didn't scrape.

## 6. Endorsement grid (sourced)

| Q | Globe | Healey | Minogue | ACX Boston (Y–N–abstain) |
|---|---|---|---|---|
| 1 | Yes | Yes | Yes | Yes 4–3–2 |
| 2 | Yes | undecided | skeptical | No 5–3–1 |
| 3 | Yes | No | No | Yes 8–0–1 |
| 4 | Yes | Yes | No (absent ID check) | Yes 8–1 |
| 5 | No | leans No | "all for that" (ambiguous) | No 5–1–2 |
| 6 | No | Yes | No | No 7–1 |
| 7 | Yes | Yes | open | Yes 7–1 |
| 8 | No | No | No | No 4–1–3 |
| 9 | Yes | Yes | No | Yes 7–1 |

ACX: Greater Boston ACX community guide, linked from ACX Open Thread 456 (https://docs.google.com/document/d/1dxSeXrFKr89jXFCMjR6bb36pxKIaryKBbW-2xA3mwLc/edit). It covers questions only and says no Greater Boston candidate race was worth endorsing. Healey and Minogue positions are from NBC Boston, "How are Maura Healey and Mike Minogue voting on 9 Mass. ballot questions?" Globe positions are from its Oct 29 roundup.

## 7. Things I could not verify (look before trusting)

1. **The ballot URL and the office list.** The SoS viewer is blocked to scripts (see §2). The candidate list comes from Politics1 (updated Oct 19), cross-checked against Wikipedia's infobox for the Senate race and Ballotpedia/Wikipedia for the Treasurer race.
2. **The Kalshi prices** come from undated search snippets. A live fetch hit HTTP 429.
3. **5th Middlesex primary totals** are DDHQ's ~92%-reporting snapshot, not certified results.
4. **Senate poll numbers** come via the PollCheck aggregator, not the original Suffolk or UMass releases. The WBUR UMass article didn't report Senate numbers.
5. **Q2, Q4, Q9 and Q1 No-side numbers from Suffolk** weren't reported in the coverage I could read, and the Suffolk crosstabs PDF wasn't linked from the coverage.
6. **The official IFV PDF** (the red book) I found was an archive link that returned undecodable binary. The guide links omniballot and the SoS questions page as official text instead.
7. **Malden's ballot itself:** the office list comes from Reading's ballot. A Malden-only item would be missed.

## 8. If you only read one paragraph

The most decisive vote on the ballot is the Northeast Metro Tech School Committee seat (10⁻⁴·⁷). After that come Q3, Q5 and Q7, all at P(tie) ≈ 10⁻⁵·⁷ — about the same as the Markey–Moulton primary. Q6 and Q2 are next, about half as decisive. Everything else is decided. On Q9, remember that **Yes keeps** the law.
