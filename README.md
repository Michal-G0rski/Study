<h3>Low-Level Security Path — from OSSU to firmware, RE and exploitation</h3>
<p>
  A tailored study plan for embedded / firmware security, reverse engineering and binary exploitation.
  Built for someone who wants deep low-level skills, remote work, and a job adjacent to offensive security.
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
  - [Early checkpoint — month 4](#early-checkpoint--month-4)
  - [How people actually get hired](#how-people-actually-get-hired)
  - [Employability checkpoint — month 9](#employability-checkpoint--month-9)
  - [If the checkpoint itself doesn't land](#if-the-checkpoint-itself-doesnt-land)
- [Market snapshot (September 2026)](#market-snapshot-september-2026)
- [Portfolio and visibility](#portfolio-and-visibility)
- [Certifications](#certifications)
- [Home lab hardware](#home-lab-hardware)
- [Deliberately skipped](#deliberately-skipped)
- [Team](#team)
- [How to use](#how-to-use)

# Summary

This plan replaces the previous OSSU-derived web/cloud path. The target is **embedded and firmware security with a strong reverse-engineering component**: firmware analysis, binary exploitation, protocol and hardware attacks.

The reasoning behind the switch: classic hardware work (PCB, bring-up, FPGA, embedded development) is lab work and rarely remote, especially at entry level. Low-level *security* keeps the hardware mindset but the actual work happens on binaries, firmware images and protocols — which is done remotely. And the reason this niche resists automation is not "hardware": it is that the ground truth lives in memory state, on a logic analyzer, or in an undocumented protocol, not in plausible-looking high-level code.

The [market research](#market-snapshot-september-2026) forced a second structural decision: the original target roles — Reverse Engineer, Malware Analyst, Vulnerability Researcher — have effectively **zero junior openings** (two junior offensive/low-level roles in all of Poland; every RE/VR/malware title found was mid, senior, principal or expert). So the fixed, scheduled curriculum is cut to the minimum that has real junior market demand — **C, networking, PortSwigger, eJPT, an own built-and-broken web app, and SOC basics** — and it ends at the [checkpoint in month 9](#employability-checkpoint--month-9), not month 18. Everything deeper (assembly, reverse engineering, exploitation, embedded and firmware work) still exists in this repo, as an [unscheduled backlog](#after-the-checkpoint) you drive by whatever job you actually land, not by a calendar.

**Assumed pace:** 15 hours/week. **Fixed schedule: 9 months (October 2026 – end of June 2027).**

| Stage | Focus | Calendar |
| :-- | :-- | :--: |
| 1 — Foundations | C, tooling, discrete math | months 1–4 |
| 2 — Networking and employability | Kurose/Beej, PortSwigger, eJPT, own app, SOC basics | months 3–9 |

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

**Topics covered**: C and the memory model, the UNIX toolchain, discrete math and number theory.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) ✅ | 13 weeks | 8–10 hours/week | none
[Modern C — Jens Gustedt (free PDF)](https://gustedt.gitlabpages.inria.fr/modern-c/) | 8 weeks | 10–12 hours/week | Systematic Program Design
[Effective C, 2nd ed. — Robert C. Seacord](https://nostarch.com/effective-c-2nd-edition) *(alternative or complement to Modern C)* | 6 weeks | 8–10 hours/week | basic C
[Beej's Guide to C Programming](https://beej.us/guide/bgc/) *(reference, read alongside)* | ongoing | 2 hours/week | none
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 10–12 hours/week | none
[Mathematics for Computer Science (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about) | 13 weeks | 5 hours/week | high school math
[The Rust Programming Language](https://doc.rust-lang.org/book/) + [Rustlings](https://github.com/rust-lang/rustlings) | 6 weeks | 8–10 hours/week | C; best started after the checkpoint

> Why C first: every later stage — CS:APP labs, pwn.college, Ghidra output, MCU firmware — assumes you read C the way you read your native language. This is the one prerequisite with no workaround.

### Stage 2 — Networking and employability

**Topics covered**: the network stack end to end, web attack surface, a first certificate, an application you build and then break yourself, and the SOC vocabulary.

Courses | Duration | Effort | Additional Text / Assignments | Prerequisites
:-- | :--: | :--: | :--: | :--:
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/) | basic CS, algebra
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | ~12 weeks | 5–12.5 hours/week | [OWASP Top 10](https://owasp.org/www-project-top-ten/) | HTTP basics
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) — the exam, month 7 | ~2 weeks focused | 10–15 hours/week | the PortSwigger track as grounding | networking, PortSwigger
Own web application (one project, any stack) — build it, then attack it | 4 weeks | 8–12 hours/week | — | programming, [PortSwigger track](#stage-2--networking-and-employability)
SOC basics — [Microsoft Sentinel learning path](https://learn.microsoft.com/en-us/training/paths/sc-200-configure-azure-sentinel-environment/), MITRE ATT&CK, alert triage vocabulary | 1–2 weeks | 10–15 hours/week | — | networking, Linux

> Networking moved to the front of this stage: it is the base layer for firmware, IoT and web work alike, and it is assumed by both eJPT and every security role in the [target table](#target-roles).

> The own-app project used to sit at the end of the old Stage 4. It now runs in month 8, directly after PortSwigger and eJPT: it is where the Academy's skills get applied rather than rehearsed, it makes Application Security Engineer reachable at the checkpoint, and its writeup is the portfolio piece an appsec employer reads to the end.

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
[pwn.college](https://pwn.college/) — full track, from shell basics to kernel exploitation | 16 weeks | 10–15 hours/week | C, assembly, Linux
[Nightmare — binary exploitation course](https://guyinatuxedo.github.io/) | 6 weeks | 5–8 hours/week | assembly, gdb
[ROP Emporium](https://ropemporium.com/) | 3 weeks | 5 hours/week | stack overflows
[exploit.education](https://exploit.education/) | 4 weeks | 5 hours/week | C, assembly

> pwn.college's Core Material must be earned belt-by-belt, in order — you cannot skip to the exploitation dojos because the early ones look easy. **ROP Emporium** ships in x86, x86-64, ARMv5 and MIPS: do the full eight-rung ladder (ret2win → ret2csu) in x86-64, then repeat the early rungs on ARMv5 and MIPS — and note that **ret2csu has no 32-bit x86 build**, so the full ladder only exists in 64-bit. **Dynamic Allocator Misuse** in pwn.college assumes you built an allocator: keep your Malloc Lab source open next to it. The own web application moved out of this section into Stage 2 — it is the one offense item with junior market value.

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
[Divide and Conquer, Sorting and Searching (Coursera)](https://www.coursera.org/learn/algorithms-divide-conquer) | 4 weeks | 4–8 hours/week | any language, Mathematics for CS
[Graph Search, Shortest Paths, and Data Structures (Coursera)](https://www.coursera.org/learn/algorithms-graphs-data-structures) | 4 weeks | 4–8 hours/week | Divide & Conquer
[Cryptopals Crypto Challenges](https://cryptopals.com/) | ongoing | 3–5 hours/week | any language
[Databases: Modeling and Theory (edX)](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 weeks | 10 hours/week | programming
[Databases: Relational Databases and SQL (edX)](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 weeks | 10 hours/week | programming

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
[picoCTF / CyLab Security Academy](https://cylabacademy.org) | Stage 2, alongside eJPT prep | 3–5 hours/week | basic Linux
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | Stage 2 | 5–12.5 hours/week | HTTP basics
[TryHackMe](https://www.tryhackme.com/) | Stage 2, alongside eJPT prep | 3–5 hours/week | networking, OS
[crackmes.one](https://crackmes.one/) | backlog | 3–5 hours/week | Ghidra basics
[pwn.college](https://pwn.college/) | backlog | 10–15 hours/week | C, assembly
[HackTheBox](https://www.hackthebox.com/) | backlog | 3–5 hours/week | networking, OS
[Microcorruption](https://microcorruption.com/) | backlog | 4–6 hours/week | assembly

---

## Target roles

The fixed schedule is ordered so that each month opens a door. The deep roles below are reachable, but through the backlog and a portfolio, not through the calendar.

Role title (as it appears in job ads) | Unlocked after | Remote in PL? | Notes
:-- | :--: | :--: | :--:
Embedded Software Engineer (C) | [Early checkpoint (month 4)](#early-checkpoint--month-4) | hybrid | not a security role, but the widest side door — you get paid while working the backlog
SOC / Detection Engineer (L1) | [Checkpoint (month 9)](#employability-checkpoint--month-9) | remote or hybrid | the largest genuinely junior slice of the security market
Junior Penetration Tester | [Checkpoint (month 9)](#employability-checkpoint--month-9) | usually remote | eJPT plus a finished PortSwigger track is the expected junior profile
Application Security Engineer | [Checkpoint (month 9)](#employability-checkpoint--month-9) | usually remote | PortSwigger track plus your own built-and-broken app, both in the fixed schedule
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

Embedded Software Engineer (C) is the largest single row in the table above — 576 openings nationally — and the only one that needs no security knowledge, just solid C. Stage 1 (months 1–4: Systematic Program Design, Modern C, the Missing Semester, discrete math) closes at the end of January 2027, exactly where that bar is cleared. The plan's other checkpoint sits at month 9, waiting on PortSwigger and eJPT; that leaves this door unused for five months for no reason tied to the C work itself.

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

June 2027. The fixed curriculum is finished by the end of this month: C, networking end to end, the PortSwigger track, eJPT, an own application you built and then broke, and the SOC basics. This is the planned moment to start sending applications, not the end of the backlog. By June the [networking habit](#how-people-actually-get-hired) has eight months behind it: the people a referral would come from have been seeing your name since October, long before you had anything to ask of them.

Apply for | Why it fits at month 9 | Format
:-- | :-- | :--:
Embedded Software Engineer (C) | 576 openings nationally, 103 in Kraków, and no security experience required | hybrid
Junior Penetration Tester | eJPT plus a finished PortSwigger track is the expected junior profile | usually remote
Application Security Engineer | the PortSwigger track plus an own built-and-broken app with a published writeup | usually remote
SOC / Detection Engineer (L1) | the largest genuinely junior slice of the security market, and the scheduled Sentinel/ATT&CK unit covers its vocabulary | remote or hybrid

> The case for the checkpoint is arithmetic, not ambition. Getting hired here turns the remaining backlog from unpaid study into paid study, puts real systems in front of you, and removes the worst failure mode of a fixed plan — reaching the end of it with no work history. If nothing lands, nothing is lost: you continue into the [backlog](#after-the-checkpoint) exactly as written, on your own schedule now.

### If the checkpoint itself doesn't land

If neither the month 4 nor the month 9 checkpoint produces an offer, the last resort is not more study — it is widening the search: hybrid roles, adjacent titles (QA with a security flavour, junior sysadmin with the C profile), and contract work. The scheduled SOC unit already covers the SIEM vocabulary, so the only remaining gap is interview practice and volume. Do not convert this into a third program of study; the market snapshot says the constraint is the entry gap, not your skills.

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

Junior competition, measured as a multi-year series rather than on the snapshot date: on Just Join IT data, the average number of applications per junior IT posting fell from 44 (2024) to 24 (2025) to 21 (H1 2026). Competition for junior roles is easing, not worsening — fewer applicants per opening at the same time as there are more openings. The series and the single-day counts above are different measurements and both stand: 21 is a half-year junior average, 146 is what one popular junior frontend opening draws. The direction of the series is the part worth keeping.

> This is why [Target roles](#target-roles) starts at month 4 with a non-security job title, why the fixed schedule is cut to the minimum junior-market curriculum, and why [Portfolio and visibility](#portfolio-and-visibility) is not optional. There is no junior queue to join in the low-level niche — you arrive either sideways through embedded work, or with published proof.

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. The blog goes up in Stage 2, around month 3 ([GitHub Pages](https://pages.github.com/) is enough), and the first post is a lab writeup rather than an introduction. In a niche with no junior openings, publishing *is* the application.

Milestone | Where | What it proves
:-- | :--: | :--
Blog live, ELF parser writeup published | fixed plan, month 3 | you can read a binary format field by field
DNS resolver writeup published | fixed plan, month 4 | you can build a protocol, not just consume a library
Traceroute writeup published | fixed plan, month 5 | you can explain, not just solve
eJPT passed | fixed plan, month 7 | the certificate the checkpoint leans on
**Own app built and broken, writeup published** | fixed plan, month 8 | you work both sides — the clearest single artifact for appsec roles
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
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) | month 7, in the fixed schedule | low | cheap and fast, and the one credential the month 9 checkpoint leans on
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
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks × 15 h to become a web developer. Reduced to one self-built app plus the PortSwigger Academy.

---

## Team

Please update this section with your personal details.

- **[Your Name / GitHub]**: *add your GitHub profile link here*

---

## How to use

1. Work through Stage 1, then Stage 2, in order. The fixed schedule ends in month 9 — that is deliberate.
2. The employability content *is* Stage 2: PortSwigger, eJPT, the own app, the SOC unit. It costs the bulk of the five months after Stage 1, and it is the whole reason the month 9 checkpoint is possible.
3. Mark finished items with ✅ directly in the tables.
4. Publishing is part of the curriculum, not an extra — the blog post in month 3, the own-app writeup in month 8.
5. Stop at the [employability checkpoint](#employability-checkpoint--month-9) and actually apply. Carrying on studying is the comfortable option, not the right one.
6. After the checkpoint, work the [backlog](#after-the-checkpoint) in the order the job you landed demands — not in the order this file lists it.
7. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.

Month-by-month scope lives in [`plans/`](plans/). Stage 1: [October 2026](plans/2026-10.md), [November](plans/2026-11.md), [December](plans/2026-12.md), [January 2027](plans/2027-01.md). Stage 2 and the run to the checkpoint: [February](plans/2027-02.md), [March](plans/2027-03.md), [April](plans/2027-04.md), [May](plans/2027-05.md), and the checkpoint month itself, [June 2027](plans/2027-06.md). The fixed schedule ends there.

The deep material — architecture, reverse engineering, exploitation, embedded and firmware work — is unscheduled, and [`plans/README.md`](plans/README.md#what-the-fixed-schedule-holds) does the accounting: nine months at fifteen hours a week hold roughly 645 study hours, the minimum junior-market curriculum fits in them with room for the programs and the blog, and everything deeper is deferred with reasons and a pickup order. The aim of the fixed schedule is a job and a portfolio. The backlog is the career.
