<h3>Low-Level Security Path — from OSSU to firmware, RE and exploitation</h3>
<p>
  A nine-month, market-measured run to a first job in security operations (SOC / Detection Engineer L1),
  on a foundation of C, UNIX and networking — with the embedded / firmware security, reverse engineering
  and binary exploitation career kept in full as the backlog that follows the hire.
</p>
<p>
  <a href="https://github.com/ossu/computer-science">
    <img alt="Open Source Society University - Computer Science" src="https://img.shields.io/badge/OSSU-derived-blue.svg">
  </a>
</p>

# Contents

- [Summary](#summary)
- [Curriculum](#curriculum)
  - [Stage 1 — Foundations](#stage-1--foundations)
  - [Stage 2 — Networking and employability](#stage-2--networking-and-employability)
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
  - [Employability checkpoint — month 9](#employability-checkpoint--month-9)
  - [If the checkpoint itself doesn't land](#if-the-checkpoint-itself-doesnt-land)
- [Market snapshot (September 2026)](#market-snapshot-september-2026)
- [Why the profile is T-shaped](#why-the-profile-is-t-shaped)
- [Portfolio and visibility](#portfolio-and-visibility)
- [Certifications](#certifications)
- [Home lab hardware](#home-lab-hardware)
- [Deliberately skipped](#deliberately-skipped)
- [Team](#team)
- [How to use](#how-to-use)

# Summary

This plan replaces the previous OSSU-derived web/cloud path. The target is **embedded and firmware security with a strong reverse-engineering component**: firmware analysis, binary exploitation, protocol and hardware attacks.

The reasoning behind the switch: classic hardware work (PCB, bring-up, FPGA, embedded development) is lab work and rarely remote, especially at entry level. Low-level *security* keeps the hardware mindset but the actual work happens on binaries, firmware images and protocols — which is done remotely. And the reason this niche resists automation is not "hardware": it is that the ground truth lives in memory state, on a logic analyzer, or in an undocumented protocol, not in plausible-looking high-level code.

The [market research](#market-snapshot-september-2026) forced a second structural decision: the original target roles — Reverse Engineer, Malware Analyst, Vulnerability Researcher — have effectively **zero junior openings** (two junior offensive/low-level roles in all of Poland; every RE/VR/malware title found was mid, senior, principal or expert). So the fixed, scheduled curriculum was cut to the minimum that has real junior market demand. A third decision, made in September 2026 on fresh measurement, goes further: **one entry path, chosen on data — SOC / Detection Engineer (L1)**, the only door in security with a measured junior queue (24 junior security openings on the snapshot date, live zero-experience SOC postings; junior pentest measured at zero openings in 45 live offers). The fixed schedule is therefore **C, UNIX and networking (the foundation), Windows and Active Directory fundamentals, a SIEM with MITRE ATT&CK and triage practice, the SC-200 certificate, and an own web application built, attacked and then detected** — and it ends at the [checkpoint in month 9](#employability-checkpoint--month-9), not month 18. The full PortSwigger track, eJPT and everything deeper (assembly, reverse engineering, exploitation, embedded and firmware work) still exist in this repo, as an [unscheduled backlog](#after-the-checkpoint) you drive by whatever job you actually land, not by a calendar. If the SOC queue closes instead, the measured fallback is junior QA — see [If the checkpoint itself doesn't land](#if-the-checkpoint-itself-doesnt-land).

**Assumed pace:** 15 hours/week. **Fixed schedule: 9 months (October 2026 – end of June 2027).**

| Stage | Focus | Calendar |
| :-- | :-- | :--: |
| 1 — Foundations | C and the UNIX toolchain | months 1–4 |
| 2 — Networking and employability | Kurose/Beej, Windows/AD, Sentinel and triage, SC-200, own app build-attack-detect | months 3–9 |

The deep material that used to be Stages 3, 4 and 5 is no longer calendar stages. It lives in [After the checkpoint](#after-the-checkpoint), unscheduled, with its effort estimates intact.

Two tracks run alongside the stages rather than inside them — the employability content is now the *main* content of Stage 2, not a side track:

| Parallel track | Runs | Purpose |
| :-- | :--: | :-- |
| Portfolio | from month 3 | one public artifact per stage, starting with the ELF parser writeup |
| Networking | from month 1, outside the 15 h/week | the referral path — see [How people actually get hired](#how-people-actually-get-hired) |

Both feed the [employability checkpoint](#employability-checkpoint--month-9) at month 9: the planned point to start applying — plus a narrower, optional opening at month 4, see [Early checkpoint](#early-checkpoint--month-4).

To track progress, mark completed items with a ✅.

---

## Curriculum

> Duration and effort for the surviving OSSU courses are kept as published by OSSU. For the added material the estimates assume the 15 h/week pace.

### Stage 1 — Foundations

**Topics covered**: C and the memory model, the UNIX toolchain.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) ✅ | 13 weeks | 8–10 hours/week | none
[Modern C — Jens Gustedt (free PDF)](https://gustedt.gitlabpages.inria.fr/modern-c/) | 8 weeks | 10–12 hours/week | Systematic Program Design
[Effective C, 2nd ed. — Robert C. Seacord](https://nostarch.com/effective-c-2nd-edition) *(alternative or complement to Modern C)* | 6 weeks | 8–10 hours/week | basic C
[Beej's Guide to C Programming](https://beej.us/guide/bgc/) *(reference, read alongside)* | ongoing | 2 hours/week | none
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 10–12 hours/week | none

> Why C first: every later stage — CS:APP labs, pwn.college, Ghidra output, MCU firmware — assumes you read C the way you read your native language. This is the one prerequisite with no workaround.

> Mathematics for Computer Science and Rust used to sit in this table. Neither is named by any junior posting this plan targets — not SOC, not pentest, not embedded C — so both moved to [Extras](#extras-optional): Mathematics with a note on where it still earns its keep, Rust exactly where its own prerequisite already said to put it, after the checkpoint. The roughly 5 hours/week Mathematics took go straight to Modern C instead — every exercise worked, not a sample, and more room on the chapters that need it.

### Stage 2 — Networking and employability

**Topics covered**: the network stack end to end, Windows and Active Directory fundamentals, a SIEM, MITRE ATT&CK and the alert-triage vocabulary, one certificate, and an application you build, attack and then write detections for — the whole stage aimed at one door, [SOC / Detection Engineer (L1)](#target-roles), the role the September 2026 market measured as the only genuinely junior one in security.

Courses | Duration | Effort | Additional Text / Assignments | Prerequisites
:-- | :--: | :--: | :--: | :--:
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/) | basic CS, algebra
Windows and Active Directory fundamentals — [TryHackMe](https://www.tryhackme.com/) Windows Fundamentals 1–3 and Active Directory Basics (or TCM Security's free Windows & AD Fundamentals course) | 3 weeks | 5–10 hours/week | the Windows event-log vocabulary, written from your own VM | Linux comfort, networking
SOC operations — [Microsoft Sentinel learning path](https://learn.microsoft.com/en-us/training/paths/sc-200-configure-azure-sentinel-environment/), MITRE ATT&CK, alert triage | ~3 weeks | 8–12 hours/week | [LetsDefend](https://letsdefend.io/) free labs; the [TryHackMe](https://www.tryhackme.com/) SOC Level 1 path alongside, February–May, 3–5 hours/week | networking, Windows basics
[SC-200 — Microsoft Security Operations Analyst](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) — the exam, month 7 | ~2 weeks focused | 10–15 hours/week | the Microsoft Learn SC-200 study paths | Sentinel, Windows/AD
Own web application (one project, any stack) — build it, attack it, then write the detections for the attacks | 4 weeks | 8–12 hours/week | — | programming, networking, a SIEM

> Networking moved to the front of this stage: it is the base layer for every security role in the [target table](#target-roles), and a SOC L1 interview is a networking interview wearing a badge.

> Why SC-200 and not eJPT: the September 2026 measurement again. Junior pentest openings — zero in 45 live pentest offers, every title mid or senior. The junior queue that actually exists — 24 junior security openings on the snapshot date, with live zero-experience SOC postings in Kraków — is on the operations side, and SC-200 is its certificate. eJPT is not dropped: it moves to the [backlog](#after-the-checkpoint) with the junior-pentester plan, and costs nothing to take after the hire.

> The own-app project is the stage's flagship artifact now, not an appsec play: build it, attack it, and then write the detections that would have caught you. "Built, attacked, detected" in one writeup is the portfolio piece a SOC hiring manager reads twice.

---

## After the checkpoint

Everything below is **unscheduled**. It is the deep low-level security curriculum this path was originally built around — architecture, reverse engineering, exploitation, embedded and firmware work — kept in full, with durations and effort estimates, to be picked up after you are hired (or when a specific role demands it). None of it has junior market demand on its own (see the [market snapshot](#market-snapshot-september-2026)); all of it is what makes the long career. The order to work through it in is decided by the job you actually land — see [The order to pick them up in](#the-order-to-pick-them-up-in).

### Computer architecture and systems

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Nand to Tetris Part I (Coursera)](https://www.coursera.org/learn/build-a-computer) (alt: [nand2tetris.org](https://www.nand2tetris.org/)) | 6 weeks | 7–13 hours/week | a C-like language
[Nand to Tetris Part II (Coursera)](https://www.coursera.org/learn/nand2tetris2) | 6 weeks | 12–18 hours/week | Nand to Tetris Part I
[Computer Systems: A Programmer's Perspective + CMU 15-213](https://www.cs.cmu.edu/~213/) | 12 weeks | 10–15 hours/week | [self-study guide](http://csapp.cs.cmu.edu/3e/students.html), [labs](http://csapp.cs.cmu.edu/3e/labs.html) — do **Data Lab, Bomb Lab, Attack Lab, Malloc Lab** | solid C
[Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) ([OSSU page](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md)) | 10–12 weeks | 6–10 hours/week | Nand to Tetris Part II

> CS:APP with the CMU labs is the single highest-leverage item in this backlog — Bomb Lab and Attack Lab are, in practice, a first course in reverse engineering and memory-corruption exploitation, and every exploitation topic below assumes them. If you pick up one thing from this backlog, pick this. Three chapters are skippable with reasons: chapter 4 (the Y86-64 processor is built in N2T project 5), chapter 5 (it optimises performance; this path cares about correctness under attack), chapter 11 (the Kurose + Beej + raw-socket work in Stage 2 already did it the hard way). The Cache Lab is droppable — its reading, sections 6.4–6.7, is what the side-channel work needs, not the matrix-transpose optimisation.

> OSTEP follows Nand to Tetris Part II, as the OSSU page orders it. If you want the OS material without the compiler half of Part II, CS:APP chapters 8, 9, 10 and 12 cover the same ground in the context this path prefers.

### Low-level and reverse engineering

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[OpenSecurityTraining2 — Architecture 1001: x86-64 Assembly](https://ost2.fyi/Arch1001) | 6 weeks | 6–8 hours/week | C, CS:APP
[OpenSecurityTraining2 — Architecture 2001: x86-64 OS Internals](https://ost2.fyi/Arch2001) | 6 weeks | 6–8 hours/week | Arch1001
[Azeria Labs — ARM assembly and ARM exploitation](https://azeria-labs.com/writing-arm-assembly-part-1/) | 4 weeks | 6–8 hours/week | Arch1001
[Reverse Engineering 101 — Malware Unicorn](https://malwareunicorn.org/workshops/re101.html) | 2 weeks | 8 hours/week | assembly
[OpenSecurityTraining2 — Debuggers 1102: Introductory Ghidra](https://ost2.fyi/Dbg1102), then scripting and your own [Ghidra](https://github.com/NationalSecurityAgency/ghidra) plugins | 4 weeks | 6–8 hours/week | assembly
[Practical Malware Analysis](https://nostarch.com/malware) | 8 weeks | 6–8 hours/week | assembly, Ghidra
[Practical Binary Analysis](https://nostarch.com/binaryanalysis) *(optional, deeper tooling)* | 6 weeks | 6–8 hours/week | assembly, C
[crackmes.one](https://crackmes.one/) — graded RE practice | ongoing | 3–5 hours/week | Ghidra basics

> Notes worth keeping, learned while this material was on a calendar. **Arch1001**: its stated prerequisite is comfort with C; it publishes no hour count, so the 6 weeks is an estimate from the chapter list. After *CISC Delight* it branches into Windows and Linux chapters that replay the same examples — take the Linux branch only. It ends with its own binary bomb lab: do it even if you already did CMU's, because the speed difference is the measurement. **Arch2001** is far heavier than its chapter count suggests — sub-lessons with question counts in the hundreds — and its subject is met in CS:APP chapter 9 and pwn.college's kernel modules; it is for after the rest of the backlog if kernel work is the direction. **ARM is not x86 with different names**: fixed-length, load/store, link register — learn it as its own thing; the transfer is in the method, not the mnemonics.

### Offense and exploitation

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) — the full beginner-to-intermediate track | ~12 weeks | 5–12.5 hours/week | HTTP basics
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) — the junior pentest credential | ~2 weeks focused | 10–15 hours/week | the PortSwigger track, networking
[pwn.college](https://pwn.college/) — full track, from shell basics to kernel exploitation | 16 weeks | 10–15 hours/week | C, assembly, Linux
[Nightmare — binary exploitation course](https://guyinatuxedo.github.io/) | 6 weeks | 5–8 hours/week | assembly, gdb
[ROP Emporium](https://ropemporium.com/) | 3 weeks | 5 hours/week | stack overflows
[exploit.education](https://exploit.education/) | 4 weeks | 5 hours/week | C, assembly

> pwn.college's Core Material must be earned belt-by-belt, in order — you cannot skip to the exploitation dojos because the early ones look easy. **ROP Emporium** ships in x86, x86-64, ARMv5 and MIPS: do the full eight-rung ladder (ret2win → ret2csu) in x86-64, then repeat the early rungs on ARMv5 and MIPS — and note that **ret2csu has no 32-bit x86 build**, so the full ladder only exists in 64-bit. **Dynamic Allocator Misuse** in pwn.college assumes you built an allocator: keep your Malloc Lab source open next to it. The own web application moved out of this section into Stage 2 — not as offense material but as the built-attacked-detected artifact the SOC checkpoint leans on. The PortSwigger track and eJPT moved *into* this section in September 2026: they are the junior-pentester move, and that move is second, after the hire.

### Embedded and hardware

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[ESP-IDF (ESP32) in C](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/index.html) — or [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) with a [Nucleo board](https://www.st.com/en/evaluation-tools/nucleo-f411re.html) | 6 weeks | 8–10 hours/week | C
UART / SPI / I²C / JTAG / SWD in practice — sniff and drive real buses | 4 weeks | 6–8 hours/week | MCU basics
[The Hardware Hacking Handbook](https://nostarch.com/hardwarehacking) | 6 weeks | 6–8 hours/week | electronics basics, C
[Practical IoT Hacking](https://nostarch.com/practical-iot-hacking) | 5 weeks | 6–8 hours/week | networking, Linux
[OWASP Firmware Security Testing Methodology](https://github.com/scriptingxss/owasp-fstm) + [binwalk](https://github.com/ReFirmLabs/binwalk) + [EMBA](https://github.com/e-m-b-a/emba) — dump and analyze firmware from a cheap router or IP camera | 4 weeks | 8 hours/week | Linux, RE basics
[Microcorruption](https://microcorruption.com/) — embedded (MSP430) exploitation CTF | 3 weeks | 4–6 hours/week | assembly
[ChipWhisperer](https://chipwhisperer.readthedocs.io/en/latest/) — side-channel analysis and fault injection ([Jupyter tutorials](https://github.com/newaetech/chipwhisperer-jupyter)) | 4 weeks | 6–8 hours/week | MCU basics, Python

> Notes from when this was scheduled. The **ESP32 scope starts with security architecture** — the ESP-IDF Security Guides (secure boot, flash encryption, and the threat model they assume) — not the toolchain install. **EMBA's output is a lead, not a finding**: every automated result gets confirmed by hand before it goes in a writeup. **Microcorruption** is a browser CTF on the MSP430, a 16-bit architecture unlike anything else here — work it in its own order. **ChipWhisperer's SCA101** early labs ship in a SIMULATED variant, so the power-analysis fundamentals (leakage model, correlation attack on AES) can be done with no board on the desk; fault injection and real-trace labs need the hardware.

### Extras (optional)

Kept because they are short and genuinely useful, not because the path depends on them.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Mathematics for Computer Science (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about) | 13 weeks | 5 hours/week | high school math
[The Rust Programming Language](https://doc.rust-lang.org/book/) + [Rustlings](https://github.com/rust-lang/rustlings) | 6 weeks | 8–10 hours/week | C; best started after the checkpoint
[Divide and Conquer, Sorting and Searching (Coursera)](https://www.coursera.org/learn/algorithms-divide-conquer) | 4 weeks | 4–8 hours/week | any language, Mathematics for CS
[Graph Search, Shortest Paths, and Data Structures (Coursera)](https://www.coursera.org/learn/algorithms-graphs-data-structures) | 4 weeks | 4–8 hours/week | Divide & Conquer
[Cryptopals Crypto Challenges](https://cryptopals.com/) | ongoing | 3–5 hours/week | any language
[Databases: Modeling and Theory (edX)](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 weeks | 10 hours/week | programming
[Databases: Relational Databases and SQL (edX)](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 weeks | 10 hours/week | programming

> Mathematics for CS is not dead weight even out of the fixed schedule — it is the natural prerequisite sitting right above it in this table, and the number-theory unit is what used to let February's networking month prove RSA rather than take it on faith. Pick it up before the algorithms pair, or whenever a role asks for it.

### The order to pick them up in

The backlog is not a sequence. It is a shelf, and the job picks. Work backwards from the role you actually landed:

- **Embedded Software Engineer (C) or adjacent** — Nand to Tetris Part I, then CS:APP. The architecture-from-NAND half pays off in interviews for exactly these roles.
- **SOC / Detection Engineer** — Cryptopals and the algorithms extras first (both pay off in detection engineering), then CS:APP chapters 8–10 for the process and OS vocabulary of the alerts you triage.
- **Application Security Engineer / Junior Pentester** — CS:APP chapters 2–3 for the exploitation vocabulary, then pwn.college's early dojos and ROP Emporium when web work starts feeling like the ceiling.
- **Reverse Engineer / Vulnerability Researcher** (once a portfolio-gated opening appears) — Arch1001, Ghidra (Dbg1102), crackmes, then the full CS:APP lab set, then pwn.college Core Material. Publish as you go; in that niche the writeups *are* the application.
- **Firmware / IoT Security** — the ESP32 and the buses first, then OWASP FSTM on a real device, then ChipWhisperer's simulated labs.

If nothing has landed yet, the default is **CS:APP with the labs**: it is the one item that every branch of this backlog eventually assumes.

---

## Hands-on Practice

Run these in parallel with the curriculum, not after it.

Platform | When to start | Effort | Prerequisites
:-- | :--: | :--: | :--:
[TryHackMe](https://www.tryhackme.com/) — Windows Fundamentals 1–3, Active Directory Basics, then the SOC Level 1 path | Stage 2 (fixed), from February | 3–5 hours/week | networking, OS
[LetsDefend](https://letsdefend.io/) / [CyberDefenders](https://cyberdefenders.org/) — blue-team incident practice | Stage 2 (fixed), from March | 3–5 hours/week | SOC vocabulary
[picoCTF / CyLab Security Academy](https://cylabacademy.org) | backlog | 3–5 hours/week | basic Linux
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | backlog — with the [junior pentester move](#offense-and-exploitation) | 5–12.5 hours/week | HTTP basics
[crackmes.one](https://crackmes.one/) | backlog | 3–5 hours/week | Ghidra basics
[pwn.college](https://pwn.college/) | backlog | 10–15 hours/week | C, assembly
[HackTheBox](https://www.hackthebox.com/) | backlog | 3–5 hours/week | networking, OS
[Microcorruption](https://microcorruption.com/) | backlog | 4–6 hours/week | assembly

---

## Target roles

The fixed schedule is ordered so that each month opens a door. Since the September 2026 decision it opens exactly one: SOC / Detection Engineer (L1), the primary target below. The measured fallback is junior QA. The deep roles are reachable, but through the backlog and a portfolio, not through the calendar — see [Employability checkpoint](#employability-checkpoint--month-9) for the ordering.

Role title (as it appears in job ads) | Unlocked after | Remote in PL? | Notes
:-- | :--: | :--: | :--:

SOC Analyst / Detection Engineer (L1) | [Checkpoint (month 9)](#employability-checkpoint--month-9) | remote or hybrid | **the plan's single primary target** — the one genuinely junior door the September 2026 market measured in security; job ads call it Junior SOC Analyst, Cyber Security Analyst (SOC L1), CSIRT Analyst, Cybersecurity Operations Analyst
Junior QA / Software Tester (security flavour) | [Checkpoint (month 9)](#employability-checkpoint--month-9) — the measured fallback | hybrid or remote | the widening door if the SOC queue closes: the most junior openings in all of IT, and the foundation covers most of the bar
Junior Penetration Tester | backlog — after the checkpoint | usually remote | eJPT plus a full PortSwigger track, both in the backlog now; zero junior openings measured on 45 live pentest offers
Application Security Engineer | backlog — after the checkpoint | usually remote | portfolio-gated; the own app from the fixed schedule is its seed
Malware Analyst / Threat Intelligence Analyst | backlog — after the checkpoint | usually remote | portfolio-gated like RE; dedicated listings barely exist in PL, CTI titles start at Mid
Reverse Engineer | backlog — after the checkpoint | remote is standard | writeups and crackmes count more than certificates here
Exploit Developer | backlog — after the checkpoint | remote is standard | narrow market, high pay, portfolio-gated
Vulnerability Researcher | backlog — after the checkpoint | remote is standard | the role this plan is really aimed at, long-term
Firmware Security Engineer | backlog — after the checkpoint | often remote | firmware analysis, secure boot, chain of trust
Embedded / IoT Security Engineer | backlog — after the checkpoint | hybrid | device audits and threat modeling; the lab is in the office
Product Security Engineer / PSIRT | backlog — after the checkpoint | remote or hybrid | vendor side: triage and fix what researchers report
Automotive Cybersecurity Engineer | backlog — after the checkpoint (+ ISO/SAE 21434, UN R155) | hybrid | large employer base in southern Poland
Hardware Security Consultant | backlog — after the checkpoint + portfolio | remote + travel | paid audits of other people's devices

> The remote gradient is the point: the closer a role sits to physical hardware, the less remote it is. Reverse engineering, vulnerability research and firmware analysis are the remote-friendly end, which is why the backlog keeps them in full — as the *second* career move, not the first application.

### Early checkpoint — month 4

Embedded Software Engineer (C) is the largest single row in the table above — 576 openings nationally — and the only one that needs no security knowledge, just solid C. Stage 1 (months 1–4: Modern C, the Missing Semester) closes at the end of January 2027, exactly where that bar is cleared. The plan's employability checkpoint at month 9 is aimed at SOC / Detection Engineer (L1) with SC-200 — the embedded C door is open from month 4 onward and does not wait on the backlog.

Apply for | Why it fits at month 4 | Format
:-- | :-- | :--:
Embedded Software Engineer (C) | 576 openings nationally, no security background required, and solid C is the entire bar | hybrid

> This is optional and runs alongside the plan, not instead of it — it does not require pausing Stage 2, and it changes nothing about the syllabus or the 15 h/week budget. What backs it is [January's own deliverable](plans/2027-01.md): a concurrent TCP server, a DNS resolver and a traceroute, three protocol programs built from raw sockets up, plus the Stage 1 review. That is what would go in front of an interviewer here — not a new artifact. If nothing comes of it, Stage 2 continues exactly as written. What the application travels through matters as much as what is in it — see [How people actually get hired](#how-people-actually-get-hired).

### How people actually get hired

The checkpoints say when to start applying. The hiring research is blunt about what applying is worth: cold applications are not the primary path in — referrals and warm contacts are — and that, not optimism, is why the networking habit starts in month 1, not at month 4.

The numbers are industry benchmarks rather than a census, but they agree on the shape. Cold applications convert at **0.1–2%**: most software engineers send 50–200 applications before an offer, and entry-level candidates often need 80–150 or more. A referral converts at roughly **30%** — referrals get interviews at 10–20 times the rate of a cold application, one is worth about forty cold ones, and an interview that comes from a referral is ~35% more likely to end in an offer. The structural numbers are blunter still: around 85% of jobs are filled through networking rather than job boards, and some 70% of those are never publicly posted. The queue you join by applying cold is not where most hiring happens.

The habit itself is a [standing rule](plans/README.md#standing-rules): 15–20 minutes a day, outside the 15 h/week budget, so it never competes with the programs for hours. Every part of it is what the outreach benchmarks say works:

- **Engage before you message.** Comment usefully on posts from people working in the target roles, long before you contact any of them. A first message to someone whose content you have engaged with gets roughly twice the reply rate of a cold one (8% → 14%).
- **Personalize, specifically.** A connection request that references something real about the recipient's work gets ~9–10% replies against 5–6% for a generic one; outreach built on specific shared context reaches ~27%.
- **Follow up once, then stop.** One follow-up after 3–5 days roughly triples the reply rate on an unanswered message (5% → 14%). A second follow-up is not in the data; it is just noise.

No hire percentage is promised here. That number is set by hiring managers, the economy and interview performance, not by a study plan. What the evidence supports is narrower and still large: the referral path converts at 5–40 times the cold path, which makes this the highest-leverage lever in the plan that costs no study hours. The Polish market is also moving the right way — junior competition has been easing for two years, [see the trend in the market snapshot](#market-snapshot-september-2026).

### Employability checkpoint — month 9

June 2027. The fixed curriculum is finished by the end of this month: C, networking end to end, Windows and AD fundamentals, the Sentinel and triage track, SC-200, and an own application you built, attacked and detected. This is the planned moment to start sending applications, not the end of the backlog. By June the [networking habit](#how-people-actually-get-hired) has eight months behind it: the people a referral would come from have been seeing your name since October, long before you had anything to ask of them.

**Lead with SOC / Detection Engineer (L1) — and only that.** This is no longer one option among four: it is the door the whole fixed schedule was rebuilt around (the September 2026 decision, [data in the snapshot](#market-snapshot-september-2026)). BNP Paribas and Aon both have live Kraków postings for it right now that explicitly say no experience is needed and training is provided; PwC runs SOC L1 seats in Kraków; 24/7 SOC operations hire juniors for shift triage because that is the seat seniors do not want. (BNP Paribas, Aon, PwC career postings, September 2026.) The fallback row below comes into play only if the market re-measured in week 3 says the junior SOC queue has closed.

Apply for | Why it fits at month 9 | Format
:-- | :-- | :--:
SOC Analyst / Detection Engineer (L1) — every title variant: Junior SOC Analyst, Cyber Security Analyst (SOC L1), CSIRT Analyst, Cybersecurity Operations Analyst | the plan's primary target: live zero-experience postings, and the Sentinel/ATT&CK/SC-200 track is its exact shape — shift seats are the most junior-shaped in the country | remote or hybrid
Junior QA / Software Tester (security flavour) — the measured fallback | the widest junior door in all of IT if SOC is shut; the foundation (HTTP, Linux, scripting, a built-attacked-detected app) covers most of its bar | hybrid or remote
Embedded Software Engineer (C) — the side door | 576 openings nationally, no security background required, and the Stage 1 protocol programs are the interview material | hybrid

> The case for the checkpoint is arithmetic, not ambition. Getting hired here turns the remaining backlog from unpaid study into paid study, puts real systems in front of you, and removes the worst failure mode of a fixed plan — reaching the end of it with no work history. If nothing lands, nothing is lost: you continue into the [backlog](#after-the-checkpoint) exactly as written, on your own schedule now.

### If the checkpoint itself doesn't land

If neither the month 4 nor the month 9 checkpoint produces an offer, the last resort is not more study — it is widening the search: hybrid roles, adjacent titles (QA with a security flavour, junior sysadmin with the C profile), and contract work. Testing is the widest of those side doors on current numbers — 6.75% of all postings on justjoin.it in 2025 — and the classic junior entry title for a profile that already reads C, Linux, HTTP and an app it built and broke itself. The scheduled SOC unit already covers the SIEM vocabulary, so the only remaining gap is interview practice and volume. Do not convert this into a third program of study; the market snapshot says the constraint is the entry gap, not your skills.

---

## Market snapshot (September 2026)

Measured on **2026-09-18**, so it can be compared against later. Counts come from a single board ([justjoin.it](https://justjoin.it/)), which keeps the columns comparable but is not a census of the market — nofluffjobs, theprotocol.it and pracuj.pl block automated reading, and a pracuj.pl spot-check turned up a Rzeszów opening that justjoin.it did not list.

Live offers | Security (this plan) | JavaScript (previous plan) | DevOps / cloud
:-- | --: | --: | --:
Poland, all | **845** | 716 | 1 376
Remote | **484** | 481 | 872
Kraków | **144** | 115 | 228
Rzeszów | 2 | 9 | 10
Junior, Poland | 24 | 37 | 44
Junior, remote | 5 | 30 | 16

Three things this data says, none of them obvious:

1. **Security is not a niche hiding from the web market — it is larger.** More openings nationally than JavaScript, and effectively tied on remote roles.
2. **Those 845 security roles are mostly infrastructure, IAM, GRC and SOC.** The low-level slice this plan originally targeted head-on is single digits nationally at any moment: roughly 3 vulnerability research, 4 embedded/firmware security, 3 reverse engineering. Narrow, but close to uncontested, and remote is the norm there.
3. **The binding constraint is the entry gap, not demand.** Junior offensive or low-level openings in all of Poland: **two**. Zero junior firmware security, zero junior RE, zero junior malware analyst — every vulnerability-research and RE title found was mid, senior, principal or expert. For comparison, a junior frontend opening draws about 146 applications, against an all-IT average of 47.

Trend context: the Polish IT market fell from about 175 600 ads in 2022 to 99 400 in 2024, recovered 8.4% in 2025, and January–May 2026 ran roughly 70% above the same months of 2025. The recovery is not in frontend, whose share of all ads slid from 5% (2024) to 3.4% (H1 2026). Cybersecurity sits in the top three deficit competencies reported by Polish employers.

**What the 2026 report season adds** (read 2026-09-19):

- **The entry gap by seniority.** Juniors: 4.79% of all justjoin.it postings in 2025 (mid 43.73%, senior 51.48%); No Fluff Jobs' H1 2026 count is one junior posting in twenty, with ~60% of open recruitments senior. Applications per posting: **47 for juniors, 24 for mid, 19 for senior**. ([Just Join IT Salary Report 2026](https://justjoin.it/raport-wynagrodzen/ogloszenia-o-prace-w-liczbach); No Fluff Jobs, "Kariera w IT 2026", via [antyweb](https://antyweb.pl/rynek-pracy-it-2026))
- **Cybersecurity is the #1 deficit competency, not merely top three.** 41% of Polish employers name it their largest skills shortage, ahead of AI/ML (33%) and IT project management (30%); NIS2 and DORA make the demand regulatory rather than cyclical. (SW Research for Scalo, via Rzeczpospolita, Dec 2025)
- **Junior pay, and where junior openings are moving.** Median junior: 9 020 PLN netto B2B / 8 000 PLN brutto UoP; junior SOC starts around 8 000–14 000 PLN. B2B junior postings grew 42% y/y while UoP junior postings fell 8.9% — the only shrinking category on the board. (Just Join IT 2026; EITT, Mar 2026)
- **A real but uneven recovery.** H1 2026 postings ran ~70% above H1 2025 (No Fluff Jobs); [czyjesteldorado.pl](https://czyjesteldorado.pl/raport-rynku-pracy-it) counted 29 234 active listings on 2026-09-19, +64% y/y, average pay 22 771 PLN (+6.9%). Frontend keeps sliding while backend (17.5% of offers) and data/BI (12%) lead. Competition per posting is easing across the board — the multi-year series is below — but the market is two-speed: seniors in ERP and architecture compete with four candidates, juniors in frontend with 146.

Junior competition, measured as a multi-year series rather than on the snapshot date: on No Fluff Jobs data, the average number of applications per junior IT posting fell from 44 (2024) to 24 (2025) to 21 (H1 2026). Competition for junior roles is easing, not worsening — fewer applicants per opening at the same time as there are more openings. The series and the single-day counts above are different measurements and both stand: 21 is a half-year junior average, 146 is what one popular junior frontend opening draws. The direction of the series is the part worth keeping.

> This is why [Target roles](#target-roles) starts at month 4 with a non-security job title, why the fixed schedule is cut to the minimum junior-market curriculum, and why [Portfolio and visibility](#portfolio-and-visibility) is not optional. There is no junior queue to join in the low-level niche — you arrive either sideways through embedded work, or with published proof.

---

## Why the profile is T-shaped

The thesis this plan runs on, stated plainly: **when the priority is fast employment, the safer strategy is a strong, specialization-agnostic operational foundation — a T-shaped profile — with the deep niche deferred until a job is paying for it.** The market data above is what forces it. What each part means here:

- **The horizontal bar — the agnostic operational foundation.** C and the UNIX toolchain, networking end to end, Linux and Windows, HTTP and the web stack, logs, debugging, written English, published work. Every checkpoint role draws on it, and so do the fallback titles ([QA with a security flavour](#if-the-checkpoint-itself-doesnt-land), junior sysadmin, backend C). It is also the layer AI fakes worst: recruiters report candidates leaning on AI tools getting disqualified for missing fundamentals, while agentic AI multiplies the output of experienced engineers and leaves juniors with marginal gains for now. The durable junior asset is the foundation, not the framework of the month.
- **The vertical bar — the legible specialization.** SOC operations: Windows and AD, Sentinel, MITRE ATT&CK, triage practice, SC-200, and the built-attacked-detected app — blue-team-tilted, on purpose. Cybersecurity is the [#1 deficit competency](#market-snapshot-september-2026) in the Polish market with regulatory underpinning (NIS2, DORA), and the September 2026 measurement says the junior queue exists on the operations side only. It is a revisitable decision in the spirit of [Deliberately skipped](#deliberately-skipped): if the re-measured market at the checkpoint points elsewhere, the vertical re-aims cheaply because the horizontal bar transfers whole.
- **Agnostic is not generic.** Juniors are hired into specific slots — SOC L1, junior QA, junior backend in a named stack — against ~47 competing applications. The horizontal bar without a readable vertical enters that queue with no story. The T is both bars, or it is nothing.
- **"Safer" does not mean "safe", and the schedule owns one real tension.** Four months of pure C before the first market-facing employability content is expensive under a literal fast-employment priority. The defense is the [early checkpoint](#early-checkpoint--month-4): embedded C is the widest side door (576 openings), and C is the one prerequisite this plan treats as having no workaround. The tension is accepted deliberately, not hidden.
- **The fastest lever costs no study hours.** Referrals convert at 5–40× cold applications; the [networking habit](#how-people-actually-get-hired) is the operational foundation of the strategy in a stricter sense than any syllabus item. No curriculum choice compensates for skipping it.

> One line: build the base everything else assumes, make it legible through one security-tilted vertical, and let the job you land pick the deep material from the [backlog](#after-the-checkpoint).

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. The blog goes up in Stage 2, around month 3 ([GitHub Pages](https://pages.github.com/) is enough), and the first post is a lab writeup rather than an introduction. In a niche with no junior openings, publishing *is* the application.

Milestone | Where | What it proves
:-- | :--: | :--
Blog live, ELF parser writeup published | fixed plan, month 3 | you can read a binary format field by field
DNS resolver writeup published | fixed plan, month 4 | you can build a protocol, not just consume a library
Traceroute writeup published | fixed plan, month 5 | you can explain, not just solve
LetsDefend incident report published | fixed plan, month 6 | you can run a triage end to end and write it up so a stranger can follow it
SC-200 passed | fixed plan, month 7 | the certificate the checkpoint leans on
**Own app built, attacked, detected — writeup published** | fixed plan, month 8 | build → attack → detect: you work both sides and can write the rule that catches you — the clearest single artifact for SOC L1
First CTF writeup published | backlog | you can explain an exploit, not just run one
First Bomb Lab or Attack Lab writeup | backlog (CS:APP) | you can read a binary you did not write
First own [Ghidra](https://github.com/NationalSecurityAgency/ghidra) script or plugin | backlog | tooling, not just tool use
Ten crackmes solved and documented | backlog | sustained RE practice
Full pwn.college module chain completed | backlog | exploitation depth
First firmware extracted from a real device | backlog | hardware access skills
Teardown writeup of a cheap IoT device | backlog | end-to-end methodology
First [CVE request submitted](https://www.cve.org/ResourcesSupport/ReportRequest) for a firmware bug | backlog | the strongest single line on a CV

> Cheap IoT firmware is full of real bugs. A first CVE is a realistic long-term goal once the embedded backlog is worked, not before.

**Companies that hire remotely in this space** (worth tracking from the checkpoint): [Securitum](https://securitum.pl/), [AFINE](https://afine.com/), [Trail of Bits](https://www.trailofbits.com/careers), [Doyensec](https://doyensec.com/careers.html), [Include Security](https://includesecurity.com/#careers), [NCC Group](https://www.nccgroup.com/). Expect the first job to be hybrid; full remote usually comes with experience.

---

## Certifications

Secondary to portfolio, but they still open doors in PL/EU recruiting.

Certification | When | Cost tier | Why
:-- | :--: | :--: | :--
[SC-200 — Microsoft Security Operations Analyst](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-200/) | month 7, in the fixed schedule | mid | the certificate the SOC L1 checkpoint leans on; Sentinel is its core, and the March–April track is its preparation
[SC-900 — Microsoft Security, Compliance, and Identity Fundamentals](https://learn.microsoft.com/en-us/credentials/certifications/exams/sc-900/) *(optional)* | month 6, as a warm-up if wanted | low | cheap vocabulary credential; skip it if the SC-200 prep is on track
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) | backlog — with the junior pentester move | low | cheap and fast, and the junior pentest credential — for the second move, after the hire
[OSCP / PEN-200 (OffSec)](https://www.offsec.com/courses/pen-200/) | backlog — after hire, market-driven | high | still the shortest route to an interview in PL/EU; a full-load ~3-month course with a 24-hour exam, so it shares a calendar with nothing
[OSED / EXP-301 (OffSec)](https://www.offsec.com/courses/exp-301/) | backlog — after OSCP, exploit-dev direction only | high | only worth it once you are committed to exploit dev

> OSCP used to be a month 14–18 calendar item. It is now a decision you make with a job and a re-measured market in front of you — the same three honest answers apply: go (it becomes the plan for a while), defer (it is a raise rather than a door), or drop (your roles reward the portfolio more). Write the answer down when the question becomes real.

---

## Home lab hardware

Optional until you start the [embedded backlog](#embedded-and-hardware); the whole list costs less than a single certification attempt.

Item | Approx. cost | Purpose
:-- | :--: | :--
[ESP32 dev board](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/index.html) or [STM32 Nucleo](https://www.st.com/en/evaluation-tools/nucleo-f411re.html) | 30–120 PLN | your own firmware to write and then break
USB–UART adapter (CP2102 / FT232) | 15–40 PLN | serial console on almost any embedded device
8-channel logic analyzer clone + [PulseView / sigrok](https://sigrok.org/wiki/PulseView) | 30–60 PLN | see SPI/I²C/UART traffic instead of guessing
[Bus Pirate](https://buspirate.com/) *(optional)* | ~200 PLN | one tool that speaks most buses
ST-Link V2 clone or [J-Link EDU Mini](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/) | 20–100 PLN | SWD/JTAG debugging and flash dumping
CH341A programmer + SOIC-8 clip + [flashrom](https://www.flashrom.org/) | 40–80 PLN | read SPI flash straight off the board
Used router / IP camera (marketplace) | 20–60 PLN | the actual target — buy two, one will die
[ChipWhisperer-Nano](https://www.newae.com/product-page/chipwhisperer-nano) | ~250–400 PLN | side-channel and fault injection at home
Soldering iron ([Pinecil](https://pine64.com/product/pinecil-smart-mini-portable-soldering-iron/) or similar) + multimeter | 150–300 PLN | test points, headers, desoldering flash chips
[RTL-SDR](https://www.rtl-sdr.com/) *(optional)* | ~120 PLN | wireless protocols, if RF turns out to interest you

---

## Deliberately skipped

Cut from the previous plan, listed here on purpose so the decisions can be revisited rather than quietly forgotten.

Item | Why it was cut
:-- | :--
[Calculus 1A / 1B / 1C (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.1x+2T2019/about) | About 32 weeks of calculus for a path whose relevant math is number theory and discrete math — Mathematics for CS covers what is needed.
[Class-based Program Design](https://course.ccs.neu.edu/cs2510sp22/index.html) | OOP design theory aimed at application development, not systems work.
[Programming Languages (CSE341)](https://courses.cs.washington.edu/courses/cse341/19au/) | Excellent course, wrong direction: ML/Racket/Ruby breadth instead of depth at the metal. Rust carries over the type-system lessons.
[Object-Oriented Design (CS3500)](https://course.ccs.neu.edu/cs3500f19/) | Same reason; together these three add up to roughly ten months of OOP/FP theory for web development.
[Software Architecture (Coursera)](https://www.coursera.org/learn/software-architecture) | Architecture-level material pays off much later, and not from a four-week survey.
[Cybersecurity Fundamentals (edX)](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals) | Broad survey; the SOC unit covers the vocabulary in a fraction of the time.
[Principles of Secure Coding (Coursera)](https://www.coursera.org/learn/secure-coding-principles) | Shallow next to the own-app build-and-break plus the PortSwigger track.
[Identifying Security Vulnerabilities (Coursera)](https://www.coursera.org/learn/identifying-security-vulnerabilities) | Same; its C/C++ variant is replaced by actually writing and breaking C.
[Greedy Algorithms, MST, Dynamic Programming (Coursera)](https://www.coursera.org/learn/algorithms-greedy) | Deferred to interview preparation.
[Shortest Paths Revisited, NP-Complete Problems (Coursera)](https://www.coursera.org/learn/algorithms-npcomplete) | Deferred to interview preparation.
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks × 15 h to become a web developer. Reduced to the one self-built app of the fixed schedule.
The pentest-first Stage 2 (full PortSwigger track + eJPT in the fixed schedule) | The September 2026 measurement: zero junior pentest openings in 45 live offers, while the junior security queue that does exist — 24 openings — is SOC operations. Not dropped: moved to the [backlog](#after-the-checkpoint) as the second move, after the hire.

---

## Team

Please update this section with your personal details.

- **[Your Name / GitHub]**: *add your GitHub profile link here*

---

## How to use

1. Work through Stage 1, then Stage 2, in order. The fixed schedule ends in month 9 — that is deliberate.
2. The employability content *is* Stage 2: Windows and AD, the SIEM and triage track, SC-200, and the own app. It costs the bulk of the five months after Stage 1, and it is the whole reason the month 9 checkpoint is possible.
3. Mark finished items with ✅ directly in the tables.
4. Publishing is part of the curriculum, not an extra — the blog post in month 3, the own-app writeup in month 8.
5. Stop at the [employability checkpoint](#employability-checkpoint--month-9) and actually apply. Carrying on studying is the comfortable option, not the right one.
6. After the checkpoint, work the [backlog](#after-the-checkpoint) in the order the job you landed demands — not in the order this file lists it.
7. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.

Month-by-month scope lives in [`plans/`](plans/). Stage 1: [October 2026](plans/2026-10.md), [November](plans/2026-11.md), [December](plans/2026-12.md), [January 2027](plans/2027-01.md). Stage 2 and the run to the checkpoint: [February](plans/2027-02.md), [March](plans/2027-03.md), [April](plans/2027-04.md), [May](plans/2027-05.md), and the checkpoint month itself, [June 2027](plans/2027-06.md). The fixed schedule ends there.

The deep material — architecture, reverse engineering, exploitation, embedded and firmware work — is unscheduled, and [`plans/README.md`](plans/README.md#what-the-fixed-schedule-holds) does the accounting: nine months at fifteen hours a week hold roughly 570 study hours, the minimum junior-market curriculum fits in them with room for the programs and the blog, and everything deeper is deferred with reasons and a pickup order. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.

