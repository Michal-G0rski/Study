# Decision aid: keep C (current plan) vs SOC-only variant

**Status: not an active plan.** This file exists to compare two shapes of the fixed schedule so a decision can be made. Whichever is chosen, the monthly files and the [main README](../README.md) stay the source of truth until edited.

The question on the table: the fixed schedule spends its first ~4 months on C (Modern C, the protocol programs) before the first market-facing employability content. The September 2026 pivot made SOC / Detection Engineer (L1) the primary target — and **nothing in the SOC L1 bar requires C**. So: is C still worth its hours?

---

## Variant A — current plan (C first, SOC checkpoint at month 9)

Months 1–4: Modern C, Missing Semester, Kurose, and three protocol programs written in C from raw sockets up (TCP server, DNS resolver, traceroute). Months 5–9: Windows/AD, Sentinel, MITRE ATT&CK, triage, SC-200, the built-attacked-detected app. Checkpoint: **June 2027**.

What the ~200 hours of C and C programs buy:

- **The embedded side door.** Embedded Software Engineer (C): 576 openings nationally, the largest single row in the [target table](../README.md#target-roles), no security background required. Solid C is the entire bar. Available from month 4 and again at the checkpoint.
- **The entire deep backlog.** CS:APP, pwn.college, Ghidra, RE, exploitation, firmware, ChipWhisperer — every one of them assumes you read C the way you read your native language ([README: why C first](../README.md#stage-1--foundations)). Without C the backlog is decorative; the long-term target (Vulnerability Researcher) is C-gated.
- **The strongest portfolio artifacts.** A DNS resolver written from raw sockets is proof you can build, not consume — it is the interview material for the embedded door and a differentiator against junior SOC candidates holding only certificates.
- **The T's horizontal bar stays deep.** Memory model, UB, toolchain, debugging — the layer that transfers to every later role and that AI-assisted candidates demonstrably lack.

Cost: the tension the plan already names ([README: why the profile is T-shaped](../README.md#why-the-profile-is-t-shaped)): four months before the first employability-track hour, in a plan whose stated priority is fast employment.


## Variant B — SOC-only (no C, checkpoint ~2 months earlier)

Cut Modern C and the C protocol programs. Keep everything the SOC bar needs: Linux comfort, Missing Semester, Python scripting, Kurose, Windows/AD, Sentinel, ATT&CK, LetsDefend, SOC L1 path, SC-200, the own app (Python is fine — "any stack" is what the stage says).

Rough month-by-month:

| Month | Content |
| :-- | :-- |
| Oct 2026 | Linux fundamentals (TryHackMe), Missing Semester, Python for scripting |
| Nov 2026 | Kurose ch. 1–4; blog live with a networking writeup |
| Dec 2026 | Kurose ch. 5–6; Python tooling practice (log parsing, a small script against a service) |
| Jan 2027 | Kurose ch. 7–8 close; Windows and AD fundamentals |
| Feb 2027 | Sentinel, MITRE ATT&CK, triage; SOC Level 1 path; LetsDefend |
| Mar 2027 | SC-200 sat; first **light** applications possible |
| Apr 2027 | The own app: build, attack, write the detections |
| May 2027 | **Checkpoint — applications sent** (month 8, ~6–8 weeks earlier than Variant A) |

What changes, honestly:

- **Gained: time to hire.** The SOC-relevant fixed content (Kurose, Windows/AD, Sentinel, SC-200, the app, the SOC L1 path) totals roughly **235–345 hours** — 4 to 6 months at 15 h/week. Variant A spreads it over months 4–9 because C owns the front. Variant B reaches the same bar around **April–May 2027**.
- **Lost: the embedded door.** No C means no 576-opening side door at month 4 and a much weaker row at the checkpoint. The fallback ladder shrinks to SOC → QA.
- **Lost: the second career move, deferred again.** The backlog (CS:APP, RE, exploitation, VR — the plan's stated long-term target) still requires C. Variant B does not delete that debt; it moves it to after the hire, where it competes with a job instead of study hours. Learning C nights-and-weekends while employed SOC is a real, commonly-abandoned path.
- **Lost: the strongest artifacts.** Blog writeups of LetsDefend incidents are good; a from-scratch DNS resolver is better. In the SOC queue you are one of ~47 per posting — differentiators matter.
- **Neutral: risk concentration.** Variant B bets everything on the junior SOC queue staying open through spring 2027, plus QA as the only fallback. Variant A holds three doors (SOC, embedded, QA).


## Side by side

| | A — current (C first) | B — SOC-only |
| :-- | :-- | :-- |
| First applications | June 2027 (month 9) | **Apr–May 2027 (~6–8 weeks earlier)** |
| Doors at the checkpoint | SOC + embedded + QA | SOC + QA |
| Portfolio depth | Protocol programs from raw sockets; ELF parser writeup | Incident writeups, own app, scripts |
| Backlog reachable after hire | Immediately (C already in hand) | Requires learning C later, employed |
| Long-term VR target | On track | Delayed by ~6–12 months of C study |
| Main risk | 4 months with no market-facing content | All eggs in the SOC queue; thinner differentiators |

## The honest read

The two variants are a bet on different failure modes. Variant A's failure mode is: the SOC queue closes or slows, and you spent 4 months on C you cannot hand to a SOC hiring manager — mitigated by the embedded door that the same C opens. Variant B's failure mode is: the SOC queue closes, and you have no second door and no deep artifacts — mitigated by nothing except QA volume.

The market data (September 2026) says the junior SOC queue is real (24 openings, live zero-experience postings) and junior competition is easing. It also says embedded C is 576 openings of unconditional demand. Variant A is the only variant that holds both.

**Recommendation, stated so it can be disagreed with:** keep Variant A. The ~6–8 weeks of earlier employability in Variant B is real but modest, and it is the only thing Variant B strictly gains — while giving up the plan's hedge, its deepest artifacts, and the on-ramp to its own stated long-term goal. If speed-to-first-paycheck is the overriding priority above all else, Variant B is defensible; nothing in it is wrong, only narrower.

**Chosen:** *(to fill in when decided)*
