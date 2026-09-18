<h3>Low-Level Security Path — from OSSU to firmware, RE and exploitation</h3>
<p>
  A tailored study plan for embedded / firmware security, reverse engineering and binary exploitation.
  Built for someone who wants deep low-level skills, remote work, and a job adjacent to offensive security.
</p>
<p>
  <a href="https://github.com/ossu/computer-science">
    <img alt="Open Source Society University - Computer Science" src="https://img.shields.io/badge/OSSU-derived-blue.svg">
  </a>
  <a href="https://pwn.college/">
    <img alt="pwn.college" src="https://img.shields.io/badge/backbone-pwn.college-red.svg">
  </a>
</p>

# Contents

- [Summary](#summary)
- [Curriculum](#curriculum)
  - [Stage 1 — Foundations](#stage-1--foundations)
  - [Stage 2 — Systems](#stage-2--systems)
  - [Stage 3 — Low-level and assembly](#stage-3--low-level-and-assembly)
  - [Stage 4 — Offense](#stage-4--offense)
  - [Stage 5 — Embedded and hardware](#stage-5--embedded-and-hardware)
  - [Extras (optional)](#extras-optional)
- [Hands-on Practice](#hands-on-practice)
- [Target roles](#target-roles)
  - [Employability checkpoint — months 9–10](#employability-checkpoint--months-910)
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

**Assumed pace:** 15 hours/week. **Estimated total time: ~18 months.** Stages overlap, so the week counts below sum to more than the calendar time.

| Stage | Focus | Calendar |
| :-- | :-- | :--: |
| 1 — Foundations | C, tooling, discrete math | months 1–4 |
| 2 — Systems | networks, nand2tetris, CS:APP, OS | months 3–11 |
| 3 — Low-level and assembly | x86-64, ARM, reverse engineering | months 11–13 |
| 4 — Offense | pwn.college, ROP, kernel exploitation, CTFs | months 13–17 |
| 5 — Embedded and hardware | MCUs, firmware extraction, side-channel | months 15–18 |

> These are the calendar's real numbers, not the syllabus's original ones — CS:APP alone pushes Stage 2 three months past where a stage-by-stage read of the curriculum would put it. The [full arithmetic](plans/README.md#what-eighteen-months-actually-holds) is in the plans folder; this table is kept in sync with it rather than with the untrimmed curriculum above.

Two tracks run alongside the stages rather than inside them, because this niche has no junior queue to wait in — see [Market snapshot](#market-snapshot-september-2026).

| Parallel track | Runs | Purpose |
| :-- | :--: | :-- |
| Employability | months 5–10 | web security track, then eJPT — something to apply with long before Stage 5 |
| Portfolio | from month 3 | one public artifact per stage, starting with a CS:APP lab writeup |

Both feed the [employability checkpoint](#employability-checkpoint--months-910) at months 9–10: the planned point to start applying, roughly halfway through.

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
[The Rust Programming Language](https://doc.rust-lang.org/book/) + [Rustlings](https://github.com/rust-lang/rustlings) | 6 weeks | 8–10 hours/week | C; best started after Stage 2

> Why C first: every later stage — CS:APP labs, pwn.college, Ghidra output, MCU firmware — assumes you read C the way you read your native language. This is the one prerequisite with no workaround.

### Stage 2 — Systems

**Topics covered**: networking, computer architecture from NAND up, the machine-level view of a program, operating systems, web attack surface.

Courses | Duration | Effort | Additional Text / Assignments | Prerequisites
:-- | :--: | :--: | :--: | :--:
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/) | basic CS, algebra
[Nand to Tetris Part I (Coursera)](https://www.coursera.org/learn/build-a-computer) (alt: [nand2tetris.org](https://www.nand2tetris.org/)) | 6 weeks | 7–13 hours/week | - | a C-like language
[Nand to Tetris Part II (Coursera)](https://www.coursera.org/learn/nand2tetris2) | 6 weeks | 12–18 hours/week | - | Nand to Tetris Part I
[Computer Systems: A Programmer's Perspective + CMU 15-213](https://www.cs.cmu.edu/~213/) | 12 weeks | 10–15 hours/week | [self-study guide](http://csapp.cs.cmu.edu/3e/students.html), [labs](http://csapp.cs.cmu.edu/3e/labs.html) — do **Data Lab, Bomb Lab, Attack Lab, Malloc Lab** | solid C
[Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) ([OSSU page](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md)) | 10–12 weeks | 6–10 hours/week | - | Nand to Tetris Part II
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) *(employability track, months 5–7)* | 6–8 weeks | 5 hours/week | [OWASP Top 10](https://owasp.org/www-project-top-ten/) | HTTP basics

> Networking moved to the front of this stage: it is the base layer for firmware, IoT and web work alike. CS:APP with the CMU labs is the single highest-leverage addition to the old plan — Bomb Lab and Attack Lab are, in practice, a first course in reverse engineering and memory-corruption exploitation.

> The web security track sits here instead of in Stage 4 for one reason: it is the only part of this plan that maps onto a job title someone will hire a beginner for. Five hours a week from month 5, closed out with [eJPT](#certifications) around month 7, and the checkpoint at month 9–10 has something to stand on. It takes nothing away from the low-level work — that is the part with no competition, and it keeps its full depth.

### Stage 3 — Low-level and assembly

**Topics covered**: x86-64 and ARM assembly, OS internals at the instruction level, static and dynamic reverse engineering.

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

> ARM matters as much as x86-64 here: nearly every device you will later pull firmware off is ARM or MIPS. The free OST2 material is a class above the paid intro security courses that used to occupy this slot.

### Stage 4 — Offense

**Topics covered**: memory corruption, ROP, kernel exploitation, attacking an application you built yourself.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[pwn.college](https://pwn.college/) — full track, from shell basics to kernel exploitation | 16 weeks | 10–15 hours/week | C, assembly, Linux
[Nightmare — binary exploitation course](https://guyinatuxedo.github.io/) | 6 weeks | 5–8 hours/week | assembly, gdb
[ROP Emporium](https://ropemporium.com/) | 3 weeks | 5 hours/week | stack overflows
[exploit.education](https://exploit.education/) | 4 weeks | 5 hours/week | C, assembly
Own web application (one project, any stack) — build it, then attack it | 4 weeks | 8 hours/week | programming, [PortSwigger track](#stage-2--systems)

> pwn.college replaces the entire old "Core security" section. The own-app project replaces Fullstack Open: you need to understand how web apps are built, but you are not training to be a web developer.

> The PortSwigger Academy and the OWASP Top 10 used to sit in this stage; they now run in Stage 2 as the employability track. By the time you get here they are finished, which turns the own-app project into the place you apply them rather than the place you first meet them.

### Stage 5 — Embedded and hardware

**Topics covered**: MCU programming, buses and debug interfaces, firmware extraction and analysis, physical attacks.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[ESP-IDF (ESP32) in C](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/index.html) — or [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) with a [Nucleo board](https://www.st.com/en/evaluation-tools/nucleo-f411re.html) | 6 weeks | 8–10 hours/week | C
UART / SPI / I²C / JTAG / SWD in practice — sniff and drive real buses | 4 weeks | 6–8 hours/week | MCU basics
[The Hardware Hacking Handbook](https://nostarch.com/hardwarehacking) | 6 weeks | 6–8 hours/week | electronics basics, C
[Practical IoT Hacking](https://nostarch.com/practical-iot-hacking) | 5 weeks | 6–8 hours/week | networking, Linux
[OWASP Firmware Security Testing Methodology](https://github.com/scriptingxss/owasp-fstm) + [binwalk](https://github.com/ReFirmLabs/binwalk) + [EMBA](https://github.com/e-m-b-a/emba) — dump and analyze firmware from a cheap router or IP camera | 4 weeks | 8 hours/week | Linux, RE basics
[Microcorruption](https://microcorruption.com/) — embedded (MSP430) exploitation CTF | 3 weeks | 4–6 hours/week | assembly
[ChipWhisperer](https://chipwhisperer.readthedocs.io/en/latest/) — side-channel analysis and fault injection ([Jupyter tutorials](https://github.com/newaetech/chipwhisperer-jupyter)) | 4 weeks | 6–8 hours/week | MCU basics, Python

> This is where "hardware" becomes something you can actually do at home. A ChipWhisperer-Nano plus a used router is a complete physical-attack lab for the price of a mid-range keyboard.

### Extras (optional)

Kept because they are short and genuinely useful, not because the path depends on them.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Divide and Conquer, Sorting and Searching (Coursera)](https://www.coursera.org/learn/algorithms-divide-conquer) | 4 weeks | 4–8 hours/week | any language, Mathematics for CS
[Graph Search, Shortest Paths, and Data Structures (Coursera)](https://www.coursera.org/learn/algorithms-graphs-data-structures) | 4 weeks | 4–8 hours/week | Divide & Conquer
[Cryptopals Crypto Challenges](https://cryptopals.com/) | ongoing | 3–5 hours/week | any language
[Databases: Modeling and Theory (edX)](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 weeks | 10 hours/week | programming
[Databases: Relational Databases and SQL (edX)](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 weeks | 10 hours/week | programming

---

## Hands-on Practice

Run these in parallel with the curriculum, not after it. From Stage 3 onward, at least a third of study time should be hands-on.

Platform | When to start | Effort | Prerequisites
:-- | :--: | :--: | :--:
[picoCTF / CyLab Security Academy](https://cylabacademy.org) | Stage 2 | 3–5 hours/week | basic Linux
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | Stage 2 | 5 hours/week | HTTP basics
[TryHackMe](https://tryhackme.com/) | Stage 2–3 | 3–5 hours/week | networking, OS
[crackmes.one](https://crackmes.one/) | Stage 3 | 3–5 hours/week | Ghidra basics
[pwn.college](https://pwn.college/) | Stage 3–4 | 10–15 hours/week | C, assembly
[HackTheBox](https://www.hackthebox.com/) | Stage 4 | 3–5 hours/week | networking, OS
[Microcorruption](https://microcorruption.com/) | Stage 5 | 4–6 hours/week | assembly

---

## Target roles

The stages are ordered so that each one opens a door before the plan is finished. You do not have to reach Stage 5 to be employable — Stage 4 already qualifies you for the roles that fund the rest.

Role title (as it appears in job ads) | Unlocked after | Remote in PL? | Notes
:-- | :--: | :--: | :--
Embedded Software Engineer (C) | Stage 2 | hybrid | not a security role, but the widest side door — you get paid while finishing the plan
Malware Analyst / Threat Intelligence Analyst | Stage 3 | usually remote | RE skills are the whole job; juniors do get hired
Junior Penetration Tester | Stage 4 (+ eJPT) | usually remote | broadest entry point into security in PL/EU
Application Security Engineer | Stage 4 | usually remote | PortSwigger track plus your own built-and-broken app
Reverse Engineer | Stage 3–4 + portfolio | remote is standard | writeups and crackmes count more than certificates here
Exploit Developer | Stage 4 (+ OSED) | remote is standard | narrow market, high pay, portfolio-gated
Vulnerability Researcher | Stage 4–5 | remote is standard | the role this plan is really aimed at
Firmware Security Engineer | Stage 5 | often remote | firmware analysis, secure boot, chain of trust
Embedded / IoT Security Engineer | Stage 5 | hybrid | device audits and threat modeling; the lab is in the office
Product Security Engineer / PSIRT | Stage 5 | remote or hybrid | vendor side: triage and fix what researchers report
Automotive Cybersecurity Engineer | Stage 5 (+ ISO/SAE 21434, UN R155) | hybrid | large employer base in southern Poland
Hardware Security Consultant | Stage 5 + portfolio | remote + travel | paid audits of other people's devices

> The remote gradient is the point: the closer a role sits to physical hardware, the less remote it is. Reverse engineering, vulnerability research and firmware analysis are the remote-friendly end, which is why Stage 5 comes last — the hardware stays your home lab and your writeup material, not your commute.

### Employability checkpoint — months 9–10

Roughly halfway. By this point you hold C, networking, the CS:APP labs, the PortSwigger track, eJPT and two or three published writeups — a hirable profile already. This is the planned moment to start sending applications, not the end of Stage 5.

Apply for | Why it fits at month 9 | Format
:-- | :-- | :--:
Embedded Software Engineer (C) | 576 openings nationally, 103 in Kraków, and no security experience required | hybrid
Junior Penetration Tester | eJPT plus a finished PortSwigger track is the expected junior profile | usually remote
SOC / Detection Engineer (L1) | the largest genuinely junior slice of the security market | remote or hybrid

> The case for the checkpoint is arithmetic, not ambition. Getting hired here turns the remaining eight months from unpaid study into paid study, puts real systems in front of you, and removes the worst failure mode of an 18-month plan — finishing it with no work history. If nothing lands, nothing is lost: you continue into Stage 4 exactly as written.

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
2. **Those 845 security roles are mostly infrastructure, IAM, GRC and SOC.** The low-level slice this plan targets is single digits nationally at any moment: roughly 3 vulnerability research, 4 embedded/firmware security, 3 reverse engineering. Narrow, but close to uncontested, and remote is the norm there.
3. **The binding constraint is the entry gap, not demand.** Junior offensive or low-level openings in all of Poland: **two**. Zero junior firmware security, zero junior RE, zero junior malware analyst — every vulnerability-research and RE title found was mid, senior, principal or expert. For comparison, a junior frontend opening draws about 146 applications, against an all-IT average of 47.

Trend context: the Polish IT market fell from about 175 600 ads in 2022 to 99 400 in 2024, recovered 8.4% in 2025, and January–May 2026 ran roughly 70% above the same months of 2025. The recovery is not in frontend, whose share of all ads slid from 5% (2024) to 3.4% (H1 2026). Cybersecurity sits in the top three deficit competencies reported by Polish employers.

> This is why [Target roles](#target-roles) starts at Stage 2 with a non-security job title, and why [Portfolio and visibility](#portfolio-and-visibility) is not optional. There is no junior queue to join in this niche — you arrive either sideways through embedded work, or with published proof.

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. The blog goes up in Stage 2, around month 3 ([GitHub Pages](https://pages.github.com/) is enough), and the first post is a lab writeup rather than an introduction. In a niche with no junior openings, publishing *is* the application.

Milestone | Target stage | What it proves
:-- | :--: | :--
Blog live, first Bomb Lab or Attack Lab writeup published | Stage 2 | you can read a binary and explain what it does
First CTF writeup published | Stage 2 | you can explain, not just solve
First own [Ghidra](https://github.com/NationalSecurityAgency/ghidra) script or plugin | Stage 3 | tooling, not just tool use
Ten crackmes solved and documented | Stage 3 | sustained RE practice
Full pwn.college module chain completed | Stage 4 | exploitation depth
First firmware extracted from a real device | Stage 5 | hardware access skills
Teardown writeup of a cheap IoT device | Stage 5 | end-to-end methodology
First [CVE request submitted](https://www.cve.org/ResourcesSupport/ReportRequest) for a firmware bug | Stage 5 | the strongest single line on a CV

> Cheap IoT firmware is full of real bugs. A first CVE is a realistic goal inside this plan, not an aspiration for later.

**Companies that hire remotely in this space** (worth tracking from month 9, the [checkpoint](#employability-checkpoint--months-910)): [Securitum](https://securitum.pl/), [AFINE](https://afine.com/), [Trail of Bits](https://www.trailofbits.com/careers), [Doyensec](https://doyensec.com/careers.html), [Include Security](https://includesecurity.com/#careers), [NCC Group](https://www.nccgroup.com/). Expect the first job to be hybrid; full remote usually comes with experience.

---

## Certifications

Secondary to portfolio, but they still open doors in PL/EU recruiting.

Certification | When | Cost tier | Why
:-- | :--: | :--: | :--
[eJPT (INE)](https://ine.com/security/certifications/ejpt-certification/) | months 6–7, alongside Stage 2 | low | cheap and fast, and the one credential the month 9–10 checkpoint leans on
[OSCP / PEN-200 (OffSec)](https://www.offsec.com/courses/pen-200/) | around month 14–18 | high | still the shortest route to an interview in PL/EU
[OSED / EXP-301 (OffSec)](https://www.offsec.com/courses/exp-301/) | after OSCP | high | only worth it once you are committed to exploit dev

---

## Home lab hardware

Everything here is optional until Stage 5, and the whole list costs less than a single certification attempt.

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
[Cybersecurity Fundamentals (edX)](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals) | Broad survey; pwn.college teaches more in its first two weeks.
[Principles of Secure Coding (Coursera)](https://www.coursera.org/learn/secure-coding-principles) | Shallow next to the CS:APP Attack Lab plus real exploitation practice.
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

1. Work through the stages in order; the overlap between them is expected and planned for (see the calendar table in [Summary](#summary)).
2. Run the employability track — PortSwigger, then eJPT — alongside Stage 2. It costs about 5 hours a week, and it is the whole reason the month 9–10 checkpoint is possible.
3. Mark finished items with ✅ directly in the tables.
4. From Stage 3 on, keep at least a third of your time hands-on — reading about exploitation does not transfer.
5. Publish something after every stage, starting in Stage 2. The blog is part of the curriculum, not an extra.
6. Stop at the [employability checkpoint](#employability-checkpoint--months-910) and actually apply. Carrying on studying is the comfortable option, not the right one.
7. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.

Month-by-month scope lives in [`plans/`](plans/). The stages say what to learn across eighteen months; a monthly plan says what has to be worked through in a given week, and nothing else.

All eighteen months are written. Stage 1: [October 2026](plans/2026-10.md), [November](plans/2026-11.md), [December](plans/2026-12.md), [January 2027](plans/2027-01.md). Stage 2 and the employability track: [February](plans/2027-02.md), [March](plans/2027-03.md), [April](plans/2027-04.md), [May](plans/2027-05.md), [June](plans/2027-06.md), [July](plans/2027-07.md). CS:APP closes and Stage 3 opens in [August](plans/2027-08.md); Arch1001 finishes in [September](plans/2027-09.md). Stage 4 opens with Ghidra and pwn.college in [October](plans/2027-10.md), runs through [November](plans/2027-11.md), [December](plans/2027-12.md), [January 2028](plans/2028-01.md) and [February](plans/2028-02.md), and the plan closes with a build-and-break month in [March 2028](plans/2028-03.md).

The plans deliberately outrun the calendar, and [`plans/README.md`](plans/README.md#what-eighteen-months-actually-holds) does the arithmetic: eighteen months at fifteen hours a week hold roughly 1,150 study hours against a curriculum of well over that, so the stages land a few months later than the bands above, and a named list of material is deferred with reasons. That is the point of the [checkpoint](#employability-checkpoint--months-910) — by month 18 the aim is a job and a portfolio, not a finished syllabus.
