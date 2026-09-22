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

The fixed, scheduled curriculum is cut to the minimum that has real junior market demand: **Linux CLI & scripting, networking end-to-end, Python for log parsing & threat intel, Windows Internals & Active Directory, PowerShell for triage, Microsoft Sentinel & KQL (practised free in the Log Analytics demo environment and a free Azure Data Explorer cluster), a self-hosted Wazuh SIEM, MITRE ATT&CK, phishing/email-header triage, Microsoft Defender XDR/Endpoint & Entra ID, a Purple-Team project (Instrument → Attack → Detect, in both KQL/Sigma and Wazuh), and the SC-200 certificate**. It ends at the [employability checkpoint in month 11](#employability-checkpoint--month-11) — August 2027 — when applications are sent.

The deep low-level curriculum — C, assembly, CS:APP, Nand to Tetris, Ghidra, pwn.college, firmware, ChipWhisperer — still exists in this repo, as an [unscheduled backlog](#after-the-checkpoint) you drive by whatever job you actually land, not by a calendar. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.

---

## Curriculum

**Assumed pace:** 15 hours/week. **Fixed schedule: 11 months (October 2026 – August 2027).**

| Stage | Focus | Calendar |
| :-- | :-- | :-- |
| 1 — Foundations for SOC | Linux CLI, networking, Python scripting, Windows basics, PowerShell, Active Directory & Kerberos | Months 1–4 |
| 2 — SOC Operations & Checkpoint | KQL, Sentinel, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, Purple-Team project (two detection engines), SC-200 | Months 5–11 |

Both stages feed the [employability checkpoint](#employability-checkpoint--month-11) at month 11: the planned point to start sending applications. The [networking habit](#how-people-actually-get-hired) starts in month 1, outside the 15 h/week budget.

---

### Stage 1 — Foundations for SOC

**Goal:** Build the operational foundation every SOC L1 posting expects. No C, no assembly, no binary formats — just the tooling you will use daily in a triage seat.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 5–10 h/week | —
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) — ch. 1–6 | 7 weeks | 4–12 h/week | basic CS, algebra
Python for Security Tooling — see [November detail](plans/2026-11.md) | 4 weeks | 8–12 h/week | Missing Semester, basic programming
[Windows Fundamentals (TryHackMe)](https://tryhackme.com/) — rooms 1–3, Active Directory Basics | 3 weeks | 5–10 h/week | Linux comfort, networking
PowerShell for Triage — see [December detail](plans/2026-12.md) | 2 weeks | 8–12 h/week | Windows basics
Active Directory deep dive (Kerberos, LDAP, attack mapping) + consolidation week — see [January detail](plans/2027-01.md) | 5 weeks | 8–15 h/week | Windows basics

> Networking starts in month 1 and continues through month 4 — it is the base layer for every security role in the [target table](#target-roles), and a SOC L1 interview is a networking interview wearing a badge.

---

### Stage 2 — SOC Operations & Checkpoint

**Goal:** The exact vocabulary and tooling of a working SOC analyst. Every item below appears in live junior postings (BNP Paribas, Aon, PwC, 24/7 SOC operations, September 2026).

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--
[Microsoft Sentinel learning path](https://learn.microsoft.com/en-us/training/paths/sc-200-configure-azure-sentinel-environment/) concepts + KQL practised free in the Log Analytics demo environment; self-hosted [Wazuh](https://wazuh.com/) installed in parallel as the permanent detection home | 6 weeks | 10–15 h/week | Networking, Windows/AD
[MITRE ATT&CK](https://attack.mitre.org/) as vocabulary + [LetsDefend](https://letsdefend.io/) labs + phishing/email-header triage module (SPF/DKIM/DMARC, sandboxed samples, PyTriage `.eml` parsing) | 6 weeks | 8–15 h/week | Sentinel basics
Microsoft Defender XDR / Endpoint + Defender for Cloud + Entra ID studied as concept from free Learn modules + docs (no live tenant); SC-200 exam | 7 weeks | 10–15 h/week | Sentinel, KQL
Purple-Team project: Instrument → Attack → Detect, twice over — KQL/Sigma, then native Wazuh rules | 6 weeks | 10–15 h/week | All above

---

## Month-by-month scope

Month | Stage | One-line summary
:-- | :-- | :--
[October 2026](plans/2026-10.md) | 1 | Missing Semester, Linux CLI, networking ch. 1–3
[November 2026](plans/2026-11.md) | 1 | Networking ch. 4–6, Python for log parsing & threat intel
[December 2026](plans/2026-12.md) | 1 | Windows Fundamentals, PowerShell basics
[January 2027](plans/2027-01.md) | 1 | Active Directory, Kerberos, attack mapping, consolidation week + market spot-check
[February 2027](plans/2027-02.md) | 2 | Microsoft Sentinel concepts & KQL begin (demo environment); Wazuh installed
[March 2027](plans/2027-03.md) | 2 | Sentinel/KQL finishes; MITRE ATT&CK begins
[April 2027](plans/2027-04.md) | 2 | ATT&CK finishes, phishing/email-triage module, incident #2, SC-200 booked
[May 2027](plans/2027-05.md) | 2 | SC-200 exam prep: Defender XDR, Defender for Cloud, Entra ID
[June 2027](plans/2027-06.md) | 2 | Exam prep finishes, SC-200 sat, Purple-Team build begins
[July 2027](plans/2027-07.md) | 2 | Purple-Team: Attack → Detect twice over — KQL/Sigma, then native Wazuh
[August 2027](plans/2027-08.md) | 2 + Checkpoint | Triage practice, interview vocab, CV, market re-measure, applications sent

The fixed schedule ends with August 2027. What comes next is the [backlog](#after-the-checkpoint), driven by the job you land.

---

## After the checkpoint

The deep low-level curriculum — the career this plan was originally built for — is not dropped. It is deferred until you have a salary, real incidents to study, and a team to learn from. Every item below is reachable from a SOC L1 seat; many are accelerated by it.

### Computer architecture and systems

Course | Effort | Prerequisites
:-- | :--: | :--
[Computer Systems: A Programmer's Perspective + CMU 15-213](https://www.cs.cmu.edu/~213/) (all 4 labs: Data, Bomb, Attack, Malloc) | 12 weeks, 10–15 h/week | Solid C
[Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) | 8 weeks, 8–12 h/week | CS:APP ch. 8–10
[Nand to Tetris Part I & II](https://www.nand2tetris.org/) | 10 weeks, 8–12 h/week | Logic gates, CS:APP ch. 3–4

### Low-level and reverse engineering

Course | Effort | Prerequisites
:-- | :--: | :--
[Effective C (Robert Seacord)](https://www.cert.org/secure-coding/) | 6 weeks, 8–12 h/week | CS:APP
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

- **SOC / Detection Engineer** → Cryptopals & algorithms extras first (pay off in detection engineering), then CS:APP ch. 8–10 for process/OS vocabulary of alerts you triage.
- **Junior SOC Engineer / Detection Engineer (stretch)** → Python automation, KQL/SQL depth, CI/CD for detection rules, then CS:APP ch. 2–3 for exploitation vocabulary.
- **Embedded Software Engineer (C) or adjacent** → Nand to Tetris Part I, then CS:APP. The architecture-from-NAND half pays off in interviews for exactly these roles.
- **Application Security Engineer / Junior Pentester** → CS:APP ch. 2–3 for exploitation vocabulary, then pwn.college early dojos and ROP Emporium.
- **Reverse Engineer / Vulnerability Researcher** (once a portfolio-gated opening appears) → Arch1001, Ghidra (Dbg1102), crackmes, then full CS:APP lab set, then pwn.college Core Material. Publish as you go; in that niche the writeups *are* the application.
- **Firmware / IoT Security** → ESP32/STM32 bare-metal first, then OWASP FSTM on a real device, then ChipWhisperer simulated labs.

If nothing has landed yet, the default is **CS:APP with the labs**: it is the single most-leveraged item on the shelf, worked at whatever pace the applications leave room for.

---

## Hands-on Practice

Run these in parallel with the curriculum, not after it.

Platform | When to start | Effort | Prerequisites
:-- | :--: | :--: | :--
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

The fixed schedule is ordered around exactly one door: **SOC / Detection Engineer (L1)** — the only security role in Poland with a measured junior queue. The fallback is Junior QA; the stretch target is Junior SOC Engineer / Detection Engineer.

Role title (as it appears in job ads) | Unlocked after | Remote in PL? | Notes
:-- | :--: | :--: | :--
SOC Analyst / Detection Engineer (L1) | [Checkpoint (month 11)](#employability-checkpoint--month-11) | Remote or hybrid | **Primary target** — live zero-experience postings, Sentinel/ATT&CK/SC-200 track is exact fit
Junior QA / Software Tester (security flavour) | [Checkpoint (month 11)](#employability-checkpoint--month-11) — measured fallback | Hybrid or remote | Widest junior door in IT if SOC closes; foundation covers most of the bar
Junior SOC Engineer / Detection Engineer | [Checkpoint (month 11)](#employability-checkpoint--month-11) — stretch | Remote or hybrid | Requires deeper KQL/SQL, Python automation, CI/CD for detection rules
Junior Penetration Tester | Backlog — after checkpoint | Usually remote | eJPT + full PortSwigger track; zero junior openings measured (45 live offers)
Application Security Engineer | Backlog — after checkpoint | Usually remote | Portfolio-gated; the Purple-Team project is its seed
Reverse Engineer / Vulnerability Researcher | Backlog — after checkpoint | Remote is standard | Portfolio-gated; writeups > certificates
Firmware / IoT Security Engineer | Backlog — after checkpoint | Hybrid | Device audits, threat modeling; lab in office

---

### How people actually get hired

The checkpoint says when to start applying. The hiring research is blunt: cold applications convert at **0.1–2%** (50–200 apps before an offer). A referral converts at roughly **30%** — referrals get interviews at 10–20× the cold rate, one is worth ~40 cold apps, and a referral interview is ~35% more likely to end in an offer. ~85% of jobs are filled through networking; ~70% are never publicly posted.

The habit is a [standing rule](plans/README.md#standing-rules): **15–20 minutes a day, outside the 15 h/week budget**, from month 1. It never competes with programs for hours.

- **Engage before you message.** Comment usefully on posts from people working in target roles. A first message to someone whose content you engaged with gets ~2× reply rate (8% → 14%).
- **Personalize, specifically.** A connection request referencing something real about the recipient's work gets ~9–10% replies vs 5–6% generic; specific shared context reaches ~27%.
- **Follow up once, then stop.** One follow-up after 3–5 days roughly triples reply rate (5% → 14%). A second is noise.

---

### Employability checkpoint — month 11

**August 2027.** The fixed curriculum is finished: Linux, networking, Python, Windows, AD, PowerShell, Sentinel, KQL, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, Purple-Team project (two detection engines), SC-200. This is the planned moment to start sending applications.

By August the [networking habit](#how-people-actually-get-hired) has ten months behind it: the people a referral would come from have been seeing your name since October, long before you had anything to ask of them.

**Lead with SOC / Detection Engineer (L1) — and only that.** This is the door the whole fixed schedule was rebuilt around (the September 2026 decision, [data in the snapshot](#market-snapshot-september-2026)). BNP Paribas and Aon both have live Kraków postings for it right now that explicitly say no experience is needed and training is provided; PwC runs SOC L1 seats in Kraków; 24/7 SOC operations hire juniors for shift triage because that is the seat seniors do not want.

Apply for | Why it fits at month 11 | Format
:-- | :-- | :--:
SOC Analyst / Detection Engineer (L1) — every title variant: Junior SOC Analyst, Cyber Security Analyst (SOC L1), CSIRT Analyst, Cybersecurity Operations Analyst | The plan's primary target: live zero-experience postings, and the Sentinel/ATT&CK/SC-200 track is its exact shape — shift seats are the most junior-shaped in the country | Remote or hybrid
Junior QA / Software Tester (security flavour) — the measured fallback | The widest junior door in all of IT if SOC is shut; the foundation (HTTP, Linux, scripting, a built-attacked-detected app) covers most of its bar | Hybrid or remote

> The case for the checkpoint is arithmetic, not ambition. Getting hired here turns the remaining backlog from unpaid study into paid study, puts real systems in front of you, and removes the worst failure mode of a fixed plan — reaching the end of it with no work history. If nothing lands, nothing is lost: you continue into the [backlog](#after-the-checkpoint) exactly as written, on your own schedule now.

---

### If the checkpoint itself doesn't land

If the month 11 checkpoint does not produce an offer, the last resort is not more study — it is widening the search: hybrid roles, adjacent titles (QA with a security flavour, junior sysadmin with the scripting profile), and contract work. Testing is the widest of those side doors on current numbers — 6.75% of all postings on justjoin.it in 2025 — and the classic junior entry title for a profile that already reads Linux, HTTP, Python, PowerShell and an app it built and broke itself. The scheduled SOC unit already covers the SIEM vocabulary, so the only remaining gap is interview practice and volume. Do not convert this into a third program of study; the market snapshot says the constraint is the entry gap, not your skills.

---

## Market snapshot (September 2026)

All figures from a single-day sweep of Polish job boards (justjoin.it, LinkedIn, pracuj.pl, rocketjobs.pl) on 15 September 2026.

Category | Count | Notes
:-- | :--: | :--
Junior security openings (all titles) | 24 | Of which SOC L1: ~14, Junior QA (sec): ~6, Other: ~4
Live zero-experience SOC postings (Kraków) | 3 | BNP Paribas, Aon, PwC — explicit "no experience, training provided"
Junior pentest openings (45 live pentest offers) | 0 | Every title Mid, Senior, Principal, Expert
Embedded C openings (all levels) | 576 | Largest single row; junior firmware measured separately at 0
Junior RE / Malware / VR | 2 | Both required 2+ years commercial experience

Trend (Poland, junior security openings, single-day snapshots): 2023 — 44, 2024 — 24, 2025 — 21, 2026 — 24. The queue is not growing, but junior competition is easing.

Regulatory tailwind: NIS2 (effective Oct 2024) and DORA (Jan 2025) mandate 24/7 monitoring and incident reporting for thousands of PL entities. The only scalable way to staff that is shift-based SOC L1 — the role this plan targets.

**This snapshot is re-taken twice:** a one-hour spot-check at the end of Stage 1 ([January consolidation week](plans/2027-01.md#week-5--1-to-6-february), before the Microsoft-specific months begin) and the full re-measure at the [checkpoint](plans/2027-08.md). Same boards, same rows, so the numbers compare.

---

## Why this shape

The thesis this plan runs on, stated plainly: **when the priority is fast employment, the safer strategy is a strong, specialization-agnostic operational foundation — a T-shaped profile — with the deep niche deferred until a job is paying for it.** The market data above is what forces it.

- **The horizontal bar — the agnostic operational foundation.** Linux CLI, networking end-to-end, Python/PowerShell scripting, Windows & AD, HTTP & web stack, logs, debugging, written English, published work. Every checkpoint role draws on it, and so do the fallback titles. It is also the layer AI fakes worst: recruiters report candidates leaning on AI tools getting disqualified for missing fundamentals, while agentic AI multiplies the output of experienced engineers and leaves juniors with marginal gains for now. The durable junior asset is the foundation, not the framework of the month.
- **The vertical bar — the legible specialization.** SOC operations: Windows & AD, Sentinel, KQL, MITRE ATT&CK, triage practice, Defender XDR, Entra ID, SC-200, and the Purple-Team project — blue-team-tilted, on purpose. Cybersecurity is the [#1 deficit competency](#market-snapshot-september-2026) in the Polish market with regulatory underpinning (NIS2, DORA), and the September 2026 measurement says the junior queue exists on the operations side only. It is a revisitable decision: if the re-measured market at the checkpoint points elsewhere, the vertical re-aims cheaply because the horizontal bar transfers whole.
- **Agnostic is not generic.** Juniors are hired into specific slots — SOC L1, junior QA, junior backend in a named stack — against ~47 competing applications. The horizontal bar without a readable vertical enters that queue with no story. The T is both bars, or it is nothing.
- **No C tax.** The previous plan spent ~200h on C before the first employability content. This plan spends zero hours on C in the fixed schedule. C, assembly, CS:APP, Ghidra, pwn.college, firmware live in the backlog — where they belong: after the hire, when the job pays for them.
- **The fastest lever costs no study hours.** Referrals convert at 5–40× cold applications; the [networking habit](#how-people-actually-get-hired) is the operational foundation of the strategy in a stricter sense than any syllabus item. No curriculum choice compensates for skipping it.

> One line: build the base everything else assumes, make it legible through one security-tilted vertical, and let the job you land pick the deep material from the [backlog](#after-the-checkpoint).

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. The blog goes up in Stage 1 (month 1), and the first post is a lab writeup rather than an introduction. In a niche with no junior openings, publishing *is* the application.

Milestone | Where | What it proves
:-- | :--: | :--
Blog live, first lab writeup published | Stage 1, month 1 | You can document technical work clearly
Python log parser / threat intel enrichment script | Stage 1, month 2 | You can automate analyst grunt work
AD attack mapping document (Kerberoasting, AS-REP, DCSync) | Stage 1, month 4 | You understand identity telemetry
KQL + Wazuh detection library (10+ detections, two engines, mapped to MITRE ATT&CK) | Stage 2, months 5–6 | You speak the SIEM language in more than one dialect
LetsDefend incident report published | Stage 2, month 6 | You can run triage end-to-end and write it up
Phishing triage playbook (SPF/DKIM/DMARC, sandboxed samples, PyTriage `.eml` parsing) | Stage 2, month 7 | You can triage the single most common initial-access vector
Defender XDR / Entra ID investigation writeup | Stage 2, month 8 | You pivot across endpoint → identity → cloud
SC-200 passed | Stage 2, month 9 | The certificate the checkpoint leans on
**Purple-Team project: Instrument → Attack → Detect, twice over (Sysmon, KQL, Sigma + native Wazuh) + Runbook** | Stage 2, month 10 | **Flagship artifact** — instrument, attack, detect in two engines, in one document

> Cheap IoT firmware is full of real bugs. A first CVE is a realistic long-term goal once the embedded backlog is worked, not before.

**Companies that hire remotely in this space** (worth tracking from the checkpoint): [Securitum](https://securitum.pl/), [AFINE](https://afine.com/), [Trail of Bits](https://www.trailofbits.com/careers), [Doyensec](https://doyensec.com/careers.html), [Include Security](https://includesecurity.com/#careers), [NCC Group](https://www.nccgroup.com/). Expect the first job to be hybrid; full remote usually comes with experience.

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

**What the fixed schedule actually costs.** The lab side is free by design — the Log Analytics demo, the free Azure Data Explorer cluster, self-hosted Wazuh, LetsDefend's free tier, Microsoft Learn — and no lab step needs a card on an account that can bill. Two things cost money, and they are known in advance rather than discovered:

- **The SC-200 exam fee**, paid when it is [booked in April](plans/2027-04.md). The September 2026 retail price is $165 (US), converted per country — check the price for Poland on the [exam page](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) before April. A retake is paid in full again, so budget for two attempts and treat May's practice assessments as the thing that saves the second fee.
- **TryHackMe Premium — optional.** Most of the [SOC Level 1 path](https://tryhackme.com/path/outline/soclevel1) (April–June) is subscriber-only (about $14/month in September 2026); only its introductory rooms are free. Free SOC rooms plus LetsDefend and CyberDefenders cover the same triage ground, so the subscription is a convenience, not a prerequisite — decide before 20 April. The same question comes up earlier for the browser-hosted AD lab in [January](plans/2027-01.md): check before 4 January whether the rooms you need are on the free tier, or budget one month.

---

## Home lab hardware

Optional until you start the [embedded backlog](#embedded-and-hardware); the whole list costs less than a single certification attempt.

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
[Principles of Secure Coding (Coursera)](https://www.coursera.org/learn/secure-coding-principles) | Shallow next to the Purple-Team build-and-break plus the PortSwigger track
[Identifying Security Vulnerabilities (Coursera)](https://www.coursera.org/learn/identifying-security-vulnerabilities) | Same; its C/C++ variant is replaced by actually writing and breaking code in the project
[Greedy Algorithms, MST, Dynamic Programming (Coursera)](https://www.coursera.org/learn/algorithms-greedy) | Deferred to interview preparation
[Shortest Paths Revisited, NP-Complete Problems (Coursera)](https://www.coursera.org/learn/algorithms-npcomplete) | Deferred to interview preparation
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks × 15 h to become a web developer. Reduced to instrumenting and defending one small application in the fixed schedule
The pentest-first Stage 2 (full PortSwigger + eJPT in fixed schedule) | The September 2026 measurement: zero junior pentest openings in 45 live offers, while the junior security queue that does exist — 24 openings — is SOC operations. Not dropped: moved to the [backlog](#after-the-checkpoint) as the second move, after the hire

---

## Team

Please update this section with your personal details.

- **[Your Name / GitHub]**: *add your GitHub profile link here*

---

## How to use

1. Work through Stage 1, then Stage 2, in order. The fixed schedule ends in month 11 — that is deliberate.
2. The employability content *is* Stage 2: KQL, Sentinel, self-hosted Wazuh, MITRE ATT&CK, phishing triage, Defender XDR, Entra ID, the Purple-Team project, and SC-200. It costs the bulk of the seven months after Stage 1, and it is the whole reason the month 11 checkpoint is possible.
3. Mark finished items with ✅ directly in the tables.
4. Publishing is part of the curriculum, not an extra — the first blog post in month 1, the Purple-Team writeup in month 10.
5. **Stop at the [employability checkpoint](#employability-checkpoint--month-11) and actually apply.** Carrying on studying is the comfortable option, not the right one.
6. After the checkpoint, work the [backlog](#after-the-checkpoint) in the order the job you landed demands — not in the order this file lists it.
7. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.

Month-by-month scope lives in [`plans/`](plans/). Stage 1: [October 2026](plans/2026-10.md), [November](plans/2026-11.md), [December](plans/2026-12.md), [January 2027](plans/2027-01.md). Stage 2 and the run to the checkpoint: [February](plans/2027-02.md), [March](plans/2027-03.md), [April](plans/2027-04.md), [May](plans/2027-05.md), [June](plans/2027-06.md), [July](plans/2027-07.md), and the checkpoint month itself, [August 2027](plans/2027-08.md). The fixed schedule ends there.

The deep material — architecture, reverse engineering, exploitation, embedded and firmware work — is unscheduled, and [`plans/README.md`](plans/README.md#what-the-fixed-schedule-holds) does the accounting: eleven months at fifteen hours a week hold roughly 680 study hours, the minimum junior-market curriculum fits in them with room for the programs and the blog, and everything deeper is deferred with reasons and a pickup order. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.
