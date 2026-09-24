<h3>SOC Fast-Track — 11 months to Security Operations (L1) with Low-Level Backlog</h3>
<p>
  An eleven-month, market-measured run to a first job in security operations (SOC / Detection Engineer L1),
  built entirely on the tooling and vocabulary that junior postings actually require — Linux, Windows, networking,
  Python/PowerShell scripting, Microsoft Sentinel, KQL, Defender XDR, Entra ID, MITRE ATT&CK, and a self-hosted
  Wazuh SIEM run in parallel so the detection work never depends on one vendor or one billable subscription.
  The embedded / firmware security, reverse engineering and binary exploitation career is kept in full
  as the backlog that follows the hire.
</p>
<p>
  <a href="https://github.com/ossu/computer-science">
    <img alt="Open Source Society University - Computer Science" src="https://img.shields.io/badge/OSSU-derived-blue.svg">
  </a>
</p>

# Contents

- [Summary](#summary)
- [Curriculum](#curriculum)
  - [Stage 1 — Foundations for SOC](#stage-1--foundations-for-soc)
  - [Stage 2 — SOC Operations & Checkpoint](#stage-2--soc-operations--checkpoint)
- [After the checkpoint](#after-the-checkpoint)
  - [Computer architecture and systems](#computer-architecture-and-systems)
  - [Low-level and reverse engineering](#low-level-and-reverse-engineering)
  - [Offense and exploitation](#offense-and-exploitation)
  - [Embedded and hardware](#embedded-and-hardware)
  - [Extras (optional)](#extras-optional)
  - [The order to pick them up in](#the-order-to-pick-them-up-in)
- [Hands-on Practice](#hands-on-practice)
- [Target roles](#target-roles)
  - [How people actually get hired](#how-people-actually-get-hired)
  - [Employability checkpoint — month 11](#employability-checkpoint--month-11)
  - [If the checkpoint itself doesn't land](#if-the-checkpoint-itself-doesnt-land)
- [Market snapshot (September 2026)](#market-snapshot-september-2026)
- [Why this shape](#why-this-shape)
- [Portfolio and visibility](#portfolio-and-visibility)
- [Certifications](#certifications)
- [Home lab hardware](#home-lab-hardware)
- [Deliberately skipped](#deliberately-skipped)
- [Team](#team)
- [How to use](#how-to-use)

# Summary

This plan replaces the previous low-level-first path. The target is **Security Operations Center Analyst / Detection Engineer (L1)** — the only security role in Poland with a measured junior queue (24 junior security openings, live zero-experience postings at BNP Paribas, Aon, PwC in Kraków; junior pentest measured at zero openings in 45 live offers, September 2026).

The fixed, scheduled curriculum is cut to the minimum that has real junior market demand: **Linux CLI & scripting, networking end-to-end, Python for log parsing & threat intel, Windows Internals & Active Directory, PowerShell for triage, Microsoft Sentinel & KQL (practised free in the Log Analytics demo environment and a free Azure Data Explorer cluster), a self-hosted Wazuh SIEM, MITRE ATT&CK, phishing/email-header triage, Microsoft Defender XDR/Endpoint & Entra ID, an endpoint & AD attack-chain lab (Instrument → Attack → Detect, in both KQL/Sigma and Wazuh), and the SC-200 certificate**. It ends at the [employability checkpoint in month 11](#employability-checkpoint--month-11) — August 2027 — when applications are sent.

The deep low-level curriculum — C, assembly, CS:APP, Nand to Tetris, Ghidra, pwn.college, firmware, ChipWhisperer — still exists in this repo, as an [unscheduled backlog](#after-the-checkpoint) you drive by whatever job you actually land, not by a calendar. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.

---

## Curriculum

**Assumed pace:** 15 hours/week. **Fixed schedule: 11 months (October 2026 – August 2027).**

| Stage | Focus | Calendar |
| :-- | :-- | :-- |
| 1 — Foundations for SOC | Linux CLI, networking & packet analysis, Python scripting, Windows basics & event IDs, PowerShell, Active Directory & Kerberos | Months 1–4 |
| 2 — SOC Operations & Checkpoint | KQL, Sentinel, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, endpoint & AD attack-chain lab (two detection engines), SC-200 | Months 5–11 |

Both stages feed the [employability checkpoint](#employability-checkpoint--month-11) at month 11: the planned point to start sending applications. [Job-search networking](#how-people-actually-get-hired) is worth doing throughout, but it is not scheduled here — it is yours to run alongside the study.

---

### Stage 1 — Foundations for SOC

**Goal:** Build the operational foundation every SOC L1 posting expects. No C, no assembly, no binary formats — just the tooling you will use daily in a triage seat.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 5–10 h/week | —
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) — ch. 1–6, with the book's own [Wireshark labs](https://gaia.cs.umass.edu/kurose_ross/wireshark.php) | 7 weeks | 4–12 h/week | basic CS, algebra
Python for Security Tooling — see [November detail](plans/2026-11.md) | 4 weeks | 8–12 h/week | Missing Semester, basic programming
[Windows Fundamentals (TryHackMe)](https://tryhackme.com/) — rooms 1–3, Active Directory Basics | 3 weeks | 5–10 h/week | Linux comfort, networking
PowerShell for Triage — see [December detail](plans/2026-12.md) | 2 weeks | 8–12 h/week | Windows basics
Active Directory deep dive (Kerberos, LDAP, attack mapping) + consolidation week — see [January detail](plans/2027-01.md) | 5 weeks | 8–15 h/week | Windows basics

> Networking runs through months 1–2, read with the book's Wireshark labs and closed on a first hostile capture — it is the base layer for every security role in the [target table](#target-roles), and a SOC L1 interview is a networking interview wearing a badge.

---

### Stage 2 — SOC Operations & Checkpoint

**Goal:** The exact vocabulary and tooling of a working SOC analyst. Every item below appears in live junior postings (BNP Paribas, Aon, PwC, 24/7 SOC operations, September 2026).

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--
[Microsoft Sentinel learning path](https://learn.microsoft.com/en-us/training/paths/sc-200-configure-azure-sentinel-environment/) concepts + KQL practised free in the Log Analytics demo environment; self-hosted [Wazuh](https://wazuh.com/) installed in parallel as the permanent detection home | 6 weeks | 10–15 h/week | Networking, Windows/AD
[MITRE ATT&CK](https://attack.mitre.org/) as vocabulary + [LetsDefend](https://letsdefend.io/) labs + phishing/email-header triage module (SPF/DKIM/DMARC, sandboxed samples, PyTriage `.eml` parsing) | 6 weeks | 8–15 h/week | Sentinel basics
Microsoft Defender XDR / Endpoint + Defender for Cloud + Entra ID studied as concept from free Learn modules + docs (no live tenant); SC-200 exam | 7 weeks | 10–15 h/week | Sentinel, KQL
Endpoint & AD attack-chain lab: Instrument → Attack → Detect, twice over — KQL/Sigma, then native Wazuh rules | 6 weeks | 10–15 h/week | All above

---

## Month-by-month scope

Month | Stage | One-line summary
:-- | :-- | :--
[October 2026](plans/2026-10.md) | 1 | Missing Semester, Linux CLI, networking ch. 1–3 + Wireshark labs
[November 2026](plans/2026-11.md) | 1 | Networking ch. 4–6 + first hostile capture, Python for log parsing & threat intel
[December 2026](plans/2026-12.md) | 1 | Windows Fundamentals, PowerShell basics
[January 2027](plans/2027-01.md) | 1 | Active Directory, Kerberos, attack mapping, consolidation week + market spot-check
[February 2027](plans/2027-02.md) | 2 | Microsoft Sentinel concepts & KQL begin (demo environment); Wazuh installed
[March 2027](plans/2027-03.md) | 2 | Sentinel/KQL finishes; MITRE ATT&CK begins
[April 2027](plans/2027-04.md) | 2 | ATT&CK finishes, phishing/email-triage module, incident #2, SC-200 booked
[May 2027](plans/2027-05.md) | 2 | SC-200 exam prep: Defender XDR, Defender for Cloud, Entra ID
[June 2027](plans/2027-06.md) | 2 | Exam prep finishes, SC-200 sat, attack-chain lab stood up
[July 2027](plans/2027-07.md) | 2 | Attack-chain lab: Attack → Detect twice over — KQL/Sigma, then native Wazuh
[August 2027](plans/2027-08.md) | 2 + Checkpoint | Triage practice, interview vocab, CV, market re-measure, applications sent

The fixed schedule ends with August 2027. What comes next is the [backlog](#after-the-checkpoint), driven by the job you land.

---

## After the checkpoint

The deep low-level curriculum — the career this plan was originally built for — is not dropped. It is deferred until you have a salary, real incidents to study, and a team to learn from. Every item below is reachable from a SOC L1 seat; many are accelerated by it.

### Computer architecture and systems

> **The C on-ramp comes first.** The old plan's prerequisites formed a loop — CS:APP wanted "solid C", Effective C wanted CS:APP — with no step that actually taught C. So the backlog now starts with a C-fundamentals item, and everything downstream (CS:APP, assembly, pwn.college, firmware) depends on it, not on each other in a circle.

Course | Effort | Prerequisites
:-- | :--: | :--
**C fundamentals** — [CS50](https://cs50.harvard.edu/x/) weeks 1–5, or [Modern C (Gustedt, free PDF)](https://hal.inria.fr/hal-02383654) / [Beej's Guide to C](https://beej.us/guide/bgc/), with exercises | 6–8 weeks, 8–12 h/week | Programming basics (Python from Stage 1 covers this)
[Computer Systems: A Programmer's Perspective + CMU 15-213](https://www.cs.cmu.edu/~213/) (all 4 labs: Data, Bomb, Attack, Malloc) | 12 weeks, 10–15 h/week | C fundamentals (above)
[Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) | 8 weeks, 8–12 h/week | CS:APP ch. 8–10
[Nand to Tetris Part I & II](https://www.nand2tetris.org/) | 10 weeks, 8–12 h/week | Logic gates only — Part I is self-contained; take it *before* CS:APP if aiming at embedded

### Low-level and reverse engineering

Course | Effort | Prerequisites
:-- | :--: | :--
[Effective C (Robert Seacord)](https://nostarch.com/effective-c-2nd-edition) | 6 weeks, 8–12 h/week | C fundamentals; best read alongside or after CS:APP
x86_64 Assembly + [Ghidra](https://ghidra-sre.org/) fundamentals | 6 weeks, 10–15 h/week | CS:APP, C
[Arch1001 / Arch2001 (pwn.college Architecture track)](https://pwn.college/) | 8 weeks, 10–15 h/week | Assembly, C
[crackmes.one](https://crackmes.one/) — sustained practice | Ongoing, 3–5 h/week | Ghidra basics

### Offense and exploitation

Course | Effort | Prerequisites
:-- | :--: | :--
[pwn.college](https://pwn.college/) — Memory Errors, Program Security, Core Material | 16 weeks, 10–15 h/week | C, Assembly, Linux
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) — full track | 12 weeks, 8–12 h/week | HTTP, networking
[ROP Emporium](https://ropemporium.com/) + Nightmare | 6 weeks, 8–12 h/week | pwn.college basics

### Embedded and hardware

Course | Effort | Prerequisites
:-- | :--: | :--
ESP32 / STM32 bare-metal C (GPIO, UART, I2C, SPI, flash) | 8 weeks, 8–12 h/week | C, CS:APP
[OWASP Firmware Security Testing Methodology](https://owasp.org/www-project-firmware-security-testing-methodology/) on real device | 6 weeks, 8–12 h/week | Bare-metal, buses
[ChipWhisperer](https://www.newae.com/) fault injection & side-channel labs | 8 weeks, 8–12 h/week | Hardware access, C
[Hardware Hacking Handbook](https://www.nostarch.com/hardwarehacking) + [Practical IoT Hacking](https://www.nostarch.com/practicaliothacking) | 10 weeks, 8–12 h/week | Above

### Extras (optional)

- [Mathematics for Computer Science (MIT 6.042J)](https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-spring-2015/) — number theory, probability, graph theory
- [Cryptopals](https://cryptopals.com/) — applied crypto, in Python or C
- [Database Systems (CMU 15-445/645)](https://15445.courses.cs.cmu.edu/spring2023/) — internals, not SQL

### The order to pick them up in

After the checkpoint, the job picks. Work backwards from the role you actually landed:

- **SOC / Detection Engineer** → the things that actually compound in a detection seat first: KQL/SQL depth, Python automation of triage and enrichment, detection-as-code (Sigma at scale, version-controlled rules, CI), and log-parsing at volume — then CS:APP ch. 8–10 for the process/OS vocabulary behind the alerts you triage. (Cryptopals is a fine *interest* project, but it does not pay off in day-to-day detection work — it lives in the extras, not here.)
- **Junior SOC Engineer / Detection Engineer (stretch)** → Python automation, KQL/SQL depth, CI/CD for detection rules, then CS:APP ch. 2–3 for exploitation vocabulary.
- **Embedded Software Engineer (C) or adjacent** → Nand to Tetris Part I, then CS:APP. The architecture-from-NAND half pays off in interviews for exactly these roles.
- **Application Security Engineer / Junior Pentester** → CS:APP ch. 2–3 for exploitation vocabulary, then pwn.college early dojos and ROP Emporium.
- **Reverse Engineer / Vulnerability Researcher** (once a portfolio-gated opening appears) → Arch1001, Ghidra (Dbg1102), crackmes, then full CS:APP lab set, then pwn.college Core Material. Publish as you go; in that niche the writeups *are* the application.
- **Firmware / IoT Security** → ESP32/STM32 bare-metal first, then OWASP FSTM on a real device, then ChipWhisperer simulated labs.

If nothing has landed yet, the default is **the C on-ramp then CS:APP with the labs**: CS:APP is the single most-leveraged item on the shelf, but it assumes C, so the fundamentals course above comes first. Worked at whatever pace the applications leave room for.

---

## Hands-on Practice

Run these in parallel with the curriculum, not after it.

Platform | When to start | Effort | Prerequisites
:-- | :--: | :--: | :--
[Wireshark labs (Kurose & Ross)](https://gaia.cs.umass.edu/kurose_ross/wireshark.php) — the book's own, trace files included | Stage 1 (M1–M2) | with the reading | —
[malware-traffic-analysis.net](https://www.malware-traffic-analysis.net/) — traffic-analysis exercises (PCAP + answer key) | Stage 1 (M2), again M7 and M11 | 2–3 h per exercise | Wireshark labs
[TryHackMe](https://tryhackme.com/) — Windows Fundamentals 1–3, Active Directory Basics | Stage 1 (M3–M4) | 3–5 h/week | Networking, OS
[TryHackMe](https://tryhackme.com/) — SOC Level 1 path *(mostly Premium; free rooms suffice — see [Certifications](#certifications))* | Stage 2 (M7–M9) | 3–5 h/week | Windows/AD, Sentinel
[LetsDefend](https://letsdefend.io/) / [CyberDefenders](https://cyberdefenders.org/) — blue-team incident practice | Stage 2 (M6) | 3–5 h/week | SOC vocabulary
[picoCTF](https://picoctf.org/) / [CyLab Security Academy](https://cylabacademy.org) | Backlog | 3–5 h/week | Basic Linux
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | Backlog — with junior pentester move | 5–12 h/week | HTTP basics
[crackmes.one](https://crackmes.one/) | Backlog | 3–5 h/week | Ghidra basics
[pwn.college](https://pwn.college/) | Backlog | 10–15 h/week | C, Assembly
[Hack The Box](https://www.hackthebox.com/) | Backlog | 3–5 h/week | Networking, OS
[Microcorruption](https://microcorruption.com/) | Backlog | 4–6 h/week | Assembly

---

## Target roles

The fixed schedule is ordered around exactly one door: **SOC / Detection Engineer (L1)** — the only security role in Poland with a measured junior queue. Two side doors sit next to it and are applied for in parallel, not held in reserve: **Service Desk / NOC / IT support in a security-heavy SSC** (the most common real-world on-ramp into a SOC — you get hired into the org, then move internally) and **Junior QA / Software Tester**. The stretch target is Junior SOC Engineer / Detection Engineer.

Role title (as it appears in job ads) | Unlocked after | Remote in PL? | Notes
:-- | :--: | :--: | :--
SOC Analyst / Detection Engineer (L1) | [Checkpoint (month 11)](#employability-checkpoint--month-11) | Remote or hybrid | **Primary target** — live zero-experience postings, Sentinel/ATT&CK/SC-200 track is exact fit
Service Desk / NOC / IT support (security-heavy SSC) | [Checkpoint (month 11)](#employability-checkpoint--month-11) — parallel on-ramp | Hybrid, occasionally on-site | The classic real route into a SOC: get hired by a Kraków/Wrocław/Warsaw SSC, then move to its SOC internally in 6–18 months. Lower bar, faster hire, and the internal transfer skips the cold-application queue entirely
Junior QA / Software Tester | [Checkpoint (month 11)](#employability-checkpoint--month-11) — parallel fallback | Hybrid or remote | Wide junior door, but **not a free win from this plan**: the foundation gives you Linux/HTTP/scripting, and QA additionally wants test-design fundamentals (ISTQB vocabulary), API testing (Postman), a browser-automation tool (Playwright/Selenium) and **SQL** — none of which the fixed schedule teaches. Budget ~2–3 weeks of targeted top-up before applying here
Junior SOC Engineer / Detection Engineer | [Checkpoint (month 11)](#employability-checkpoint--month-11) — stretch | Remote or hybrid | Requires deeper KQL/SQL, Python automation, CI/CD for detection rules
Junior Penetration Tester | Backlog — after checkpoint | Usually remote | eJPT + full PortSwigger track; zero junior openings measured (45 live offers)
Application Security Engineer | Backlog — after checkpoint | Usually remote | Portfolio-gated; seeded by the backlog PortSwigger track, not the SOC flagship (which is endpoint/AD, not AppSec)
Reverse Engineer / Vulnerability Researcher | Backlog — after checkpoint | Remote is standard | Portfolio-gated; writeups > certificates
Firmware / IoT Security Engineer | Backlog — after checkpoint | Hybrid | Device audits, threat modeling; lab in office

---

### How people actually get hired

The checkpoint says when to start applying. The direction of the hiring research is not in dispute, even if the exact percentages are: cold applications convert in the low single digits (commonly cited around **0.1–2%**, i.e. dozens to a couple hundred applications per offer), while a referral converts far higher (often cited near **30%**) and gets you an interview at many times the cold rate. The widely-repeated "~85% of jobs filled through networking" and "~70% never publicly posted" figures circulate without a solid primary source — treat them as folklore that points the right way, not as measured fact. What you can rely on: a warm introduction beats a cold application by a large multiple, so the referral pipeline is worth more per hour than any single résumé tweak.

**This plan does not schedule networking, budget it, or track it** — it is left entirely to you to run in your own way. But it is worth doing, and probably the highest-leverage non-study thing you can do for the checkpoint, so it is flagged here rather than buried. A few things the hiring research suggests actually work, if and when you reach out, for whatever they are worth:

- Engaging with someone's work before messaging them lifts reply rates; a specific, personalised first contact beats a generic one by a wide margin.
- One follow-up after a few days helps; a second is noise.
- In Poland, showing up in person tends to out-convert online contact — [CONFidence](https://confidence-conference.org/) (Kraków), OWASP Poland chapter meetups, ISSA Polska, [Sekurak](https://sekurak.pl/) events, and local blue-team meetups are the ones that map to this path.

None of that is a curriculum item or a checklist to tick. It is context; the doing is yours.

---

### Employability checkpoint — month 11

**August 2027.** The fixed curriculum is finished: Linux, networking and packet analysis, Python, Windows, AD, PowerShell, Sentinel, KQL, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, the endpoint & AD attack-chain lab (two detection engines), SC-200. This is the planned moment to start sending applications.

If you have [built contacts in the field](#how-people-actually-get-hired) over the year — left to you, not scheduled by this plan — a referral is the fastest route in by a wide margin, and it is worth leaning on now.

**Lead with SOC / Detection Engineer (L1) — and only that.** This is the door the whole fixed schedule was rebuilt around (the September 2026 decision, [data in the snapshot](#market-snapshot-september-2026)). BNP Paribas and Aon both have live Kraków postings for it right now that explicitly say no experience is needed and training is provided; PwC runs SOC L1 seats in Kraków; 24/7 SOC operations hire juniors for shift triage because that is the seat seniors do not want.

Apply for | Why it fits at month 11 | Format
:-- | :-- | :--:
SOC Analyst / Detection Engineer (L1) — every title variant: Junior SOC Analyst, Cyber Security Analyst (SOC L1), Cybersecurity Operations Analyst (and, at the forensics-aware end, CSIRT Analyst) | The plan's primary target: live zero-experience postings, and the Sentinel/ATT&CK/SC-200 track is its exact shape — shift seats are the most junior-shaped in the country. CSIRT titles lean harder on host/memory forensics than L1 triage does — see the [forensics note](#deliberately-skipped) | Remote or hybrid
Service Desk / NOC / IT support in a security-heavy SSC — the parallel on-ramp | Not a fallback held in reserve — applied for at the same time. Lower bar, faster hire, and the standard internal route into the org's own SOC 6–18 months later, which bypasses the cold queue | Hybrid, sometimes on-site
Junior QA / Software Tester — a parallel door with a top-up | Wide junior door, but the foundation only covers part of its bar (Linux, HTTP, scripting); add test-design vocabulary, API testing, a browser-automation tool and **SQL** before applying — ~2–3 weeks of targeted work | Hybrid or remote

> The case for the checkpoint is arithmetic, not ambition. Getting hired here turns the remaining backlog from unpaid study into paid study, puts real systems in front of you, and removes the worst failure mode of a fixed plan — reaching the end of it with no work history. If nothing lands, nothing is lost: you continue into the [backlog](#after-the-checkpoint) exactly as written, on your own schedule now.

---

### If the checkpoint itself doesn't land

If the month 11 checkpoint does not produce an offer, the answer is not more study — it is widening the *targets*, which the plan does from day one rather than treating as a last resort:

- **Service Desk / NOC / IT support in a security-heavy SSC** is the widest real on-ramp and the one most people who now sit in a Polish SOC actually came through. You are hired into the organisation on a lower bar, then move to its SOC internally — an internal transfer that skips the cold-application queue entirely. Apply here in parallel with SOC L1, not after it fails.
- **QA / Software Tester** is a wide door, but be honest about the gap: this plan gives you Linux, HTTP and scripting; QA additionally wants test-design fundamentals (ISTQB-flavoured vocabulary), API testing (Postman), a browser-automation tool (Playwright/Selenium) and **SQL** — which the fixed schedule never teaches. It is a ~2–3-week targeted top-up, not a free win, so cost it in before leaning on it.
- **Junior sysadmin / cloud-support** roles suit the scripting-and-Windows/AD profile and are a second internal route toward security work.

The scheduled SOC unit already carries the SIEM vocabulary, so for the SOC seats themselves the remaining gap is interview practice and application volume, not skills. Do not convert a slow checkpoint into a third program of study; the constraint the market shows is the entry gap, and a foot in the door of the right organisation closes it faster than another certificate.

---

## Market snapshot (September 2026)

All figures from a **single-day** sweep of Polish job boards (justjoin.it, LinkedIn, pracuj.pl, rocketjobs.pl) on 15 September 2026. Treat every count below as one noisy data point, not a measurement: a board on a Tuesday in September is not the market. That is exactly why the plan re-counts the top two rows [every month](plans/README.md#standing-rules) — the line over time is the evidence; this table is only its first point.

Category | Count | Notes
:-- | :--: | :--
Junior security openings (all titles) | 24 | Of which SOC L1: ~14, Junior QA (sec): ~6, Other: ~4
Live zero-experience SOC postings (Kraków) | 3 | BNP Paribas, Aon, PwC — explicit "no experience, training provided"
Junior pentest openings (45 live pentest offers) | 0 | Every title Mid, Senior, Principal, Expert
Embedded C openings (all levels) | 576 | Largest single row; junior firmware measured separately at 0
Junior RE / Malware / VR | 2 | Both required 2+ years commercial experience

Trend (Poland, junior security openings, single-day snapshots): 2023 — 44, 2024 — 24, 2025 — 21, 2026 — 24. Read it carefully: the *opening* count has roughly halved and then held flat since 2023. It says nothing about the number of *applicants* per opening — that side was not measured, so the plan makes no claim that "competition is easing." What the numbers support is narrower: a small, stable junior queue that exists on the SOC-operations side and essentially nowhere else junior.

Regulatory tailwind, stated conservatively: **NIS2** set a 17 October 2024 *transposition* deadline for EU member states; Poland's implementing amendment to the Krajowy System Cyberbezpieczeństwa (KSC) Act was still moving through the legislative process into 2026, so the obligations bite as national law lands, not on the EU date. **DORA** applies to financial entities from 17 January 2025. Neither text literally mandates a "24/7 SOC"; both push a large set of regulated entities toward continuous monitoring, incident detection and mandatory reporting — and the practical, scalable way large orgs meet that is a shift-based SOC with junior L1 seats, which is the demand this plan is betting on. The bet is directional; do not oversell it in a cover letter as a legal 24/7 mandate.

**This snapshot is re-counted every month** (the 15-minute [standing-rule](plans/README.md#standing-rules) check), with two deep passes: a one-hour spot-check at the end of Stage 1 ([January consolidation week](plans/2027-01.md#week-5--1-to-6-february), before the Microsoft-specific months begin) and the full re-measure at the [checkpoint](plans/2027-08.md). Same boards, same rows, so the numbers compare.

---

## Why this shape

The thesis this plan runs on, stated plainly: **when the priority is fast employment, the safer strategy is a strong, specialization-agnostic operational foundation — a T-shaped profile — with the deep niche deferred until a job is paying for it.** The market data above is what forces it.

- **The horizontal bar — the agnostic operational foundation.** Linux CLI, networking end-to-end, Python/PowerShell scripting, Windows & AD, HTTP & web stack, logs, debugging, written English, published work. Every checkpoint role draws on it, and so do the fallback titles. It is also the layer AI fakes worst: recruiters report candidates leaning on AI tools getting disqualified for missing fundamentals, while agentic AI multiplies the output of experienced engineers and leaves juniors with marginal gains for now. The durable junior asset is the foundation, not the framework of the month.
- **The vertical bar — the legible specialization.** SOC operations: Windows & AD, Sentinel, KQL, MITRE ATT&CK, triage practice, Defender XDR, Entra ID, SC-200, and the endpoint & AD attack-chain lab — blue-team-tilted, on purpose. Cybersecurity is a persistent skills-shortage area in the Polish and wider EU market, with regulatory demand behind it ([NIS2, DORA — stated conservatively above](#market-snapshot-september-2026)), and the September 2026 measurement says the *junior* queue exists on the operations side only. It is a revisitable decision: if the [monthly re-count](plans/README.md#standing-rules) at the checkpoint points elsewhere, the vertical re-aims cheaply because the horizontal bar transfers whole.
- **Agnostic is not generic.** Juniors are hired into specific slots — SOC L1, junior QA, junior backend in a named stack — against ~47 competing applications. The horizontal bar without a readable vertical enters that queue with no story. The T is both bars, or it is nothing.
- **No C tax.** The previous plan spent ~200h on C before the first employability content. This plan spends zero hours on C in the fixed schedule. C, assembly, CS:APP, Ghidra, pwn.college, firmware live in the backlog — where they belong: after the hire, when the job pays for them.
- **The fastest lever costs no study hours.** A warm introduction beats a cold application by a large multiple, so [job-search networking](#how-people-actually-get-hired) matters more than any single syllabus choice. This plan deliberately does not schedule it — it is yours to run — but that is not the same as skipping it, and no curriculum choice compensates for skipping it.

> One line: build the base everything else assumes, make it legible through one security-tilted vertical, and let the job you land pick the deep material from the [backlog](#after-the-checkpoint).

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. The blog goes up in Stage 1 (month 1), and the first post is a lab writeup rather than an introduction. In a niche with no junior openings, publishing *is* the application.

Milestone | Where | What it proves
:-- | :--: | :--
Blog live, first lab writeup published | Stage 1, month 1 | You can document technical work clearly
Python log parser / threat intel enrichment script | Stage 1, month 2 | You can automate analyst grunt work
AD attack mapping document (Kerberoasting, AS-REP, DCSync) | Stage 1, month 4 | You understand identity telemetry
KQL + Wazuh detection library (ten detections, two engines, mapped to MITRE ATT&CK) | Stage 2, months 5–6 | You speak the SIEM language in more than one dialect
LetsDefend incident report published | Stage 2, month 6 | You can run triage end-to-end and write it up
Phishing triage playbook (SPF/DKIM/DMARC, sandboxed samples, PyTriage `.eml` parsing) | Stage 2, month 7 | You can triage the single most common initial-access vector
Defender XDR / Entra ID investigation writeup | Stage 2, month 8 | You pivot across endpoint → identity → cloud
SC-200 passed | Stage 2, month 9 | The certificate the checkpoint leans on
**Endpoint & AD attack-chain lab: Instrument → Attack → Detect, twice over (Atomic Red Team / Caldera → Sysmon + Windows Security, KQL, Sigma + native Wazuh), ATT&CK-mapped + Runbook** | Stage 2, months 9–10 | **Flagship artifact** — run a real intrusion chain, detect it in two engines, in one document

> Cheap IoT firmware is full of real bugs. A first CVE is a realistic long-term goal once the embedded backlog is worked, not before.

**Where the junior SOC seats actually are** (track these from the checkpoint — they hire L1 and shift analysts, which the boutiques below mostly do not):

- **Shared-service / GBS centres in Poland** that run their own SOCs and hire zero-experience juniors: BNP Paribas, Aon, PwC, and the wider Kraków/Wrocław/Warsaw SSC cluster (EY, Deloitte, Capgemini, HSBC, UBS, Credit Suisse-lineage, Motorola Solutions, ABB, Shell, Lufthansa Systems, and similar). This is where the "no experience, training provided" postings live, and where the Service-Desk-then-SOC internal route runs.
- **Managed SOC / MSSP providers** operating in PL: e.g. [Exatel](https://www.exatel.pl/), Orange Polska / [ICSA](https://www.orange.pl/), [T-Mobile Polska](https://www.t-mobile.pl/), [Comarch](https://www.comarch.pl/), [Nomios](https://www.nomios.pl/), Integrity Partners, and the SOC arms of the big consultancies. Check each one's current careers page against the [monthly market count](plans/README.md#standing-rules) rather than trusting this list — vendors and their staffing move.

The offensive-security boutiques the previous plan listed — [Securitum](https://securitum.pl/), [AFINE](https://afine.com/), [Trail of Bits](https://www.trailofbits.com/careers), [Doyensec](https://doyensec.com/careers.html), [Include Security](https://includesecurity.com/#careers), [NCC Group](https://www.nccgroup.com/) — belong to the **backlog / pentester move**, not the SOC checkpoint; they hire on an offensive portfolio, rarely at zero experience, and are tracked for later.

Expect the first job to be hybrid; full remote usually comes with experience.

---

## Certifications

Secondary to portfolio, but they still open doors in PL/EU recruiting.

Certification | When | Cost tier | Why
:-- | :--: | :--: | :--
[SC-200 — Microsoft Security Operations Analyst](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) | Month 9, in fixed schedule | Mid | The certificate the SOC L1 checkpoint leans on; Sentinel, XDR, Entra ID are its core
[SC-900 — Microsoft Security, Compliance, and Identity Fundamentals](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/) *(optional)* | Month 5–6, as warm-up | Low | Cheap vocabulary credential; skip if SC-200 prep is on track
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) | Backlog — with junior pentester move | Low | Cheap, fast, junior pentest credential — for the second move, after the hire
[OSCP / PEN-200 (OffSec)](https://www.offsec.com/courses/pen-200/) | Backlog — after hire, market-driven | High | Still the shortest route to an interview in PL/EU; full-load ~3-month course with 24h exam
[OSED / EXP-301 (OffSec)](https://www.offsec.com/courses/exp-301/) | Backlog — after OSCP, exploit-dev only | High | Only worth it once committed to exploit dev

> OSCP used to be a month 14–18 calendar item. It is now a decision you make with a job and a re-measured market in front of you — the same three honest answers apply: go (it becomes the plan for a while), defer (it is a raise rather than a door), or drop (your roles reward the portfolio more). Write the answer down when the question becomes real.

> **A note on "as concept."** Roughly seven weeks of Stage 2 study Defender XDR, Defender for Cloud and Entra ID from Learn modules and docs without operating the live product. That is an honest gap, and an interviewer can hear it. The plan narrows it two free ways before spending anything: [Microsoft Applied Skills](https://learn.microsoft.com/en-us/credentials/browse/?credential_types=applied%20skills) assessments run in a real hosted lab in the browser (Sentinel and Defender tracks), and [KC7](https://kc7cyber.com/) drills KQL on security stories. If you want genuine hands-on tenant time, the *optional* paid-adjacent route is below — bounded, not open-ended. Also: Microsoft is folding Sentinel into the **unified Defender portal** and revises the SC-200 objective domains periodically, so in [April](plans/2027-04.md) re-read the current [SC-200 study guide](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) against these notes before committing the May/June plan — the "three legs" framing may have shifted.

**What the fixed schedule actually costs.** The lab side is free by design — the Log Analytics demo, the free Azure Data Explorer cluster, self-hosted Wazuh, LetsDefend's free tier, Microsoft Learn, Applied Skills, KC7 — and no *required* lab step needs a card on an account that can bill. Two things cost money and are known in advance rather than discovered, plus one clearly-optional third:

- **The SC-200 exam fee**, paid when it is [booked in April](plans/2027-04.md). The September 2026 retail price is $165 (US), converted per country — check the price for Poland on the [exam page](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) before April. A retake is paid in full again, so budget for two attempts and treat May's practice assessments as the thing that saves the second fee.
- **TryHackMe Premium — optional.** Most of the [SOC Level 1 path](https://tryhackme.com/path/outline/soclevel1) (April–June) is subscriber-only (about $14/month in September 2026); only its introductory rooms are free. Free SOC rooms plus LetsDefend and CyberDefenders cover the same triage ground, so the subscription is a convenience, not a prerequisite — decide before 20 April. The same question comes up earlier for the browser-hosted AD lab in [January](plans/2027-01.md): check before 4 January whether the rooms you need are on the free tier, or budget one month.
- **An Azure free trial — optional, bounded, and the one place a card appears.** The default plan is card-free. If you want real hands-on time in a live Sentinel/Defender/Entra tenant to close the "as concept" gap, the honest route is an [Azure free account](https://azure.microsoft.com/free/) opened for **one billing month around the exam** (May–June): set a **hard spending limit / budget alert at 0**, use the free Microsoft Sentinel ingestion allowance, and **delete the resource group and the whole tenant the day the exam is done**. This is the single window in the plan where a bill is possible; it stays bounded because it is short, capped, and torn down on a fixed date, not left running. Skip it entirely and Applied Skills + the ADX cluster + Wazuh still carry the hands-on load — the trial buys tenant-UI familiarity, not detection skill you can't get elsewhere.

---

## Home lab hardware

**The one non-optional piece is the machine you already study on.** The fixed schedule assumes a workstation that can run a Windows VM (with Sysmon), a self-hosted Wazuh stack (OpenSearch-based — memory-hungry) and Docker *at the same time*, from February onward. In practice that means **16 GB RAM as a floor and 32 GB comfortable**, an SSD, and CPU virtualisation enabled. If your machine can't hold all three at once, the realistic options are: run Wazuh single-node with reduced heap and stop the VM when you don't need it, or push Wazuh to a small always-on box / cheap cloud VM and keep only the Windows VM local. Sort this out in [January](plans/2027-01.md) before February needs it — it is the one hardware dependency the plan cannot study its way around.

The list below is different: it is **optional until you start the [embedded backlog](#embedded-and-hardware)**, and the whole of it costs less than a single certification attempt.

Item | Approx. cost | Purpose
:-- | :--: | :--
[ESP32 dev board](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/index.html) or [STM32 Nucleo](https://www.st.com/en/evaluation-tools/nucleo-f411re.html) | 30–120 PLN | Your own firmware to write and then break
USB–UART adapter (CP2102 / FT232) | 15–40 PLN | Serial console on almost any embedded device
8-channel logic analyzer clone + [PulseView / sigrok](https://sigrok.org/wiki/PulseView) | 30–60 PLN | See SPI/I²C/UART traffic instead of guessing
[Bus Pirate](https://buspirate.com/) *(optional)* | ~200 PLN | One tool that speaks most buses
ST-Link V2 clone or [J-Link EDU Mini](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/) | 20–100 PLN | SWD/JTAG debugging and flash dumping
CH341A programmer + SOIC-8 clip + [flashrom](https://www.flashrom.org/) | 40–80 PLN | Read SPI flash straight off the board
Used router / IP camera (marketplace) | 20–60 PLN | The actual target — buy two, one will die
[ChipWhisperer-Nano](https://www.newae.com/product-page/chipwhisperer-nano) | ~250–400 PLN | Side-channel and fault injection at home
Soldering iron ([Pinecil](https://pine64.com/product/pinecil-smart-mini-portable-soldering-iron/) or similar) + multimeter | 150–300 PLN | Test points, headers, desoldering flash chips
[RTL-SDR](https://www.rtl-sdr.com/) *(optional)* | ~120 PLN | Wireless protocols, if RF turns out to interest you

---

## Deliberately skipped

Cut from the previous plan, listed here on purpose so the decisions can be revisited rather than quietly forgotten.

Item | Why it was cut
:-- | :--
[Calculus 1A / 1B / 1C (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.1x+2T2019/about) | ~32 weeks of calculus for a path whose relevant math is number theory and discrete math — Mathematics for CS covers what is needed
[Class-based Program Design](https://course.ccs.neu.edu/cs2510sp22/index.html) | OOP design theory aimed at application development, not systems work
[Programming Languages (CSE341)](https://courses.cs.washington.edu/courses/cse341/19au/) | Excellent course, wrong direction: ML/Racket/Ruby breadth instead of depth at the metal. Rust carries over the type-system lessons
[Object-Oriented Design (CS3500)](https://course.ccs.neu.edu/cs3500f19/) | Same reason; together these three add up to roughly ten months of OOP/FP theory for web development
[Software Architecture (Coursera)](https://www.coursera.org/learn/software-architecture) | Architecture-level material pays off much later, and not from a four-week survey
[Cybersecurity Fundamentals (edX)](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals) | Broad survey; the SOC unit covers the vocabulary in a fraction of the time
[Principles of Secure Coding (Coursera)](https://www.coursera.org/learn/secure-coding-principles) | Shallow, and off-target for a SOC seat; the secure-coding/AppSec ground lives in the backlog PortSwigger track, picked up with the pentester move
[Identifying Security Vulnerabilities (Coursera)](https://www.coursera.org/learn/identifying-security-vulnerabilities) | Same; its C/C++ variant is replaced by actually writing and breaking code in the project
[Greedy Algorithms, MST, Dynamic Programming (Coursera)](https://www.coursera.org/learn/algorithms-greedy) | Deferred to interview preparation
[Shortest Paths Revisited, NP-Complete Problems (Coursera)](https://www.coursera.org/learn/algorithms-npcomplete) | Deferred to interview preparation
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks × 15 h to become a web developer — wrong target for a SOC seat. The old plan's web-app purple-team has been replaced by the endpoint & AD attack-chain lab, which needs no web-dev track at all
The pentest-first Stage 2 (full PortSwigger + eJPT in fixed schedule) | The September 2026 measurement: zero junior pentest openings in 45 live offers, while the junior security queue that does exist — 24 openings — is SOC operations. Not dropped: moved to the [backlog](#after-the-checkpoint) as the second move, after the hire
Deep host & memory forensics (Volatility, Prefetch/Amcache/ShimCache/LNK parsing, full disk-image DFIR) | This is DFIR-analyst depth, not L1-triage depth — an L1 seat *recognises* these artifacts and escalates, it does not carve them. The plan keeps only a **light awareness pass**: a couple of [CyberDefenders](https://cyberdefenders.org/) forensics/endpoint challenges in Stage 2 and one memory-triage walkthrough, enough to speak to it in a CSIRT-flavoured interview. The full DFIR track (SANS FOR500/FOR508 territory) is a post-hire specialisation, market-driven like OSCP

---

## Team

Please update this section with your personal details.

- **[Your Name / GitHub]**: *add your GitHub profile link here*

---

## How to use

1. Work through Stage 1, then Stage 2, in order. The fixed schedule ends in month 11 — that is deliberate.
2. The employability content *is* Stage 2: KQL, Sentinel, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, the endpoint & AD attack-chain lab, and SC-200. It costs the bulk of the seven months after Stage 1, and it is the whole reason the month 11 checkpoint is possible.
3. Mark finished items with ✅ directly in the tables.
4. Publishing is part of the curriculum, not an extra — the first blog post in month 1, the attack-chain flagship writeup in month 10.
5. **Stop at the [employability checkpoint](#employability-checkpoint--month-11) and actually apply.** Carrying on studying is the comfortable option, not the right one.
6. After the checkpoint, work the [backlog](#after-the-checkpoint) in the order the job you landed demands — not in the order this file lists it.
7. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.

Month-by-month scope lives in [`plans/`](plans/). Stage 1: [October 2026](plans/2026-10.md), [November](plans/2026-11.md), [December](plans/2026-12.md), [January 2027](plans/2027-01.md). Stage 2 and the run to the checkpoint: [February](plans/2027-02.md), [March](plans/2027-03.md), [April](plans/2027-04.md), [May](plans/2027-05.md), [June](plans/2027-06.md), [July](plans/2027-07.md), and the checkpoint month itself, [August 2027](plans/2027-08.md). The fixed schedule ends there.

The deep material — architecture, reverse engineering, exploitation, embedded and firmware work — is unscheduled, and [`plans/README.md`](plans/README.md#what-the-fixed-schedule-holds) does the accounting: eleven months at fifteen hours a week hold roughly 680 study hours, the minimum junior-market curriculum fits in them with room for the programs and the blog, and everything deeper is deferred with reasons and a pickup order. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.
