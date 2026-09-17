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
| 2 — Systems | networks, nand2tetris, CS:APP, OS | months 3–9 |
| 3 — Low-level and assembly | x86-64, ARM, reverse engineering | months 8–12 |
| 4 — Offense | pwn.college, web, CTFs | months 10–16 |
| 5 — Embedded and hardware | MCUs, firmware extraction, side-channel | months 13–18 |

To track progress, mark completed items with a ✅.

---

## Curriculum

> Duration and effort for the surviving OSSU courses are kept as published by OSSU. For the added material the estimates assume the 15 h/week pace.

### Stage 1 — Foundations

**Topics covered**: C and the memory model, the UNIX toolchain, discrete math and number theory.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) ✅ | 13 weeks | 8–10 hours/week | none
[Modern C — Jens Gustedt (free PDF)](https://inria.hal.science/hal-02383654) | 8 weeks | 10–12 hours/week | Systematic Program Design
[Effective C, 2nd ed. — Robert C. Seacord](https://nostarch.com/Effective_C_2E) *(alternative or complement to Modern C)* | 6 weeks | 8–10 hours/week | basic C
[Beej's Guide to C Programming](https://beej.us/guide/bgc/) *(reference, read alongside)* | ongoing | 2 hours/week | none
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 10–12 hours/week | none
[Mathematics for Computer Science (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about) | 13 weeks | 5 hours/week | high school math
[The Rust Programming Language](https://doc.rust-lang.org/book/) + [Rustlings](https://github.com/rust-lang/rustlings) | 6 weeks | 8–10 hours/week | C; best started after Stage 2

> Why C first: every later stage — CS:APP labs, pwn.college, Ghidra output, MCU firmware — assumes you read C the way you read your native language. This is the one prerequisite with no workaround.

### Stage 2 — Systems

**Topics covered**: networking, computer architecture from NAND up, the machine-level view of a program, operating systems.

Courses | Duration | Effort | Additional Text / Assignments | Prerequisites
:-- | :--: | :--: | :--: | :--:
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/) | basic CS, algebra
[Nand to Tetris Part I (Coursera)](https://www.coursera.org/learn/build-a-computer) (alt: [nand2tetris.org](https://www.nand2tetris.org/)) | 6 weeks | 7–13 hours/week | - | a C-like language
[Nand to Tetris Part II (Coursera)](https://www.coursera.org/learn/nand2tetris2) | 6 weeks | 12–18 hours/week | - | Nand to Tetris Part I
[Computer Systems: A Programmer's Perspective + CMU 15-213](https://www.cs.cmu.edu/~213/) | 12 weeks | 10–15 hours/week | [self-study guide](http://csapp.cs.cmu.edu/3e/students.html), [labs](http://csapp.cs.cmu.edu/3e/labs.html) — do **Data Lab, Bomb Lab, Attack Lab, Malloc Lab** | solid C
[Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) ([OSSU page](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md)) | 10–12 weeks | 6–10 hours/week | - | Nand to Tetris Part II

> Networking moved to the front of this stage: it is the base layer for firmware, IoT and web work alike. CS:APP with the CMU labs is the single highest-leverage addition to the old plan — Bomb Lab and Attack Lab are, in practice, a first course in reverse engineering and memory-corruption exploitation.

### Stage 3 — Low-level and assembly

**Topics covered**: x86-64 and ARM assembly, OS internals at the instruction level, static and dynamic reverse engineering.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[OpenSecurityTraining2 — Architecture 1001: x86-64 Assembly](https://ost2.fyi/Arch1001) | 6 weeks | 6–8 hours/week | C, CS:APP
[OpenSecurityTraining2 — Architecture 2001: x86-64 OS Internals](https://ost2.fyi/Arch2001) | 6 weeks | 6–8 hours/week | Arch1001
[OpenSecurityTraining2 — ARM assembly track](https://ost2.fyi/) | 4 weeks | 6–8 hours/week | Arch1001
[Reverse Engineering 101 — Malware Unicorn](https://malwareunicorn.org/workshops/re101.html) | 2 weeks | 8 hours/week | assembly
[Ghidra](https://ghidra-sre.org/) ([source](https://github.com/NationalSecurityAgency/ghidra)) — tooling, scripting, own plugins | 4 weeks | 6–8 hours/week | assembly
[Practical Malware Analysis](https://nostarch.com/malware) | 8 weeks | 6–8 hours/week | assembly, Ghidra
[Practical Binary Analysis](https://nostarch.com/binaryanalysis) *(optional, deeper tooling)* | 6 weeks | 6–8 hours/week | assembly, C
[crackmes.one](https://crackmes.one/) — graded RE practice | ongoing | 3–5 hours/week | Ghidra basics

> ARM matters as much as x86-64 here: nearly every device you will later pull firmware off is ARM or MIPS. The free OST2 material is a class above the paid intro security courses that used to occupy this slot.

### Stage 4 — Offense

**Topics covered**: memory corruption, ROP, kernel exploitation, web attack surface.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[pwn.college](https://pwn.college/) — full track, from shell basics to kernel exploitation | 16 weeks | 10–15 hours/week | C, assembly, Linux
[Nightmare — binary exploitation course](https://guyinatuxedo.github.io/) | 6 weeks | 5–8 hours/week | assembly, gdb
[ROP Emporium](https://ropemporium.com/) | 3 weeks | 5 hours/week | stack overflows
[exploit.education](https://exploit.education/) | 4 weeks | 5 hours/week | C, assembly
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | 6–8 weeks | 5 hours/week | HTTP basics
[OWASP Top 10](https://owasp.org/www-project-top-ten/) | 2 weeks | 3–4 hours/week | none
Own web application (one project, any stack) — build it, then attack it | 4 weeks | 8 hours/week | programming

> pwn.college replaces the entire old "Core security" section. The own-app project replaces Fullstack Open: you need to understand how web apps are built, but you are not training to be a web developer.

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
[ChipWhisperer](https://chipwhisperer.readthedocs.io/en/latest/) — side-channel analysis and fault injection ([tutorials](https://learn.chipwhisperer.io/)) | 4 weeks | 6–8 hours/week | MCU basics, Python

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
[picoCTF](https://picoctf.org/) | Stage 2 | 3–5 hours/week | basic Linux
[crackmes.one](https://crackmes.one/) | Stage 3 | 3–5 hours/week | Ghidra basics
[pwn.college](https://pwn.college/) | Stage 3–4 | 10–15 hours/week | C, assembly
[Web Security Academy (PortSwigger)](https://portswigger.net/web-security) | Stage 4 | 5 hours/week | HTTP basics
[HackTheBox](https://www.hackthebox.com/) | Stage 4 | 3–5 hours/week | networking, OS
[TryHackMe](https://tryhackme.com/) | Stage 4 | 3–5 hours/week | networking, OS
[Microcorruption](https://microcorruption.com/) | Stage 5 | 4–6 hours/week | assembly

---

## Portfolio and visibility

Portfolio beats certificates in this field. Every milestone below is a public artifact — a blog post, a repo, or an advisory. Set the blog up early ([GitHub Pages](https://pages.github.com/) is enough) and write as you go.

Milestone | Target stage | What it proves
:-- | :--: | :--
First CTF writeup published | Stage 2–3 | you can explain, not just solve
First own [Ghidra](https://github.com/NationalSecurityAgency/ghidra) script or plugin | Stage 3 | tooling, not just tool use
Ten crackmes solved and documented | Stage 3 | sustained RE practice
Full pwn.college module chain completed | Stage 4 | exploitation depth
First firmware extracted from a real device | Stage 5 | hardware access skills
Teardown writeup of a cheap IoT device | Stage 5 | end-to-end methodology
First [CVE request submitted](https://www.cve.org/ResourcesSupport/ReportRequest) for a firmware bug | Stage 5 | the strongest single line on a CV

> Cheap IoT firmware is full of real bugs. A first CVE is a realistic goal inside this plan, not an aspiration for later.

**Companies that hire remotely in this space** (worth tracking from month 12): [Securitum](https://securitum.pl/), [AFINE](https://afine.com/), [Trail of Bits](https://www.trailofbits.com/careers), [Doyensec](https://doyensec.com/careers.html), [Include Security](https://www.includesecurity.com/careers/), [NCC Group](https://www.nccgroup.com/). Expect the first job to be hybrid; full remote usually comes with experience.

---

## Certifications

Secondary to portfolio, but they still open doors in PL/EU recruiting.

Certification | When | Cost tier | Why
:-- | :--: | :--: | :--
[eJPT (INE)](https://security.ine.com/certifications/ejpt-certification/) | as Stage 4 starts | low | cheap warm-up, proves basic methodology
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
[ChipWhisperer-Nano](https://www.newae.com/chipwhisperer) | ~250–400 PLN | side-channel and fault injection at home
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
2. Mark finished items with ✅ directly in the tables.
3. From Stage 3 on, keep at least a third of your time hands-on — reading about exploitation does not transfer.
4. Publish something after every stage. The blog is part of the curriculum, not an extra.
5. Revisit [Deliberately skipped](#deliberately-skipped) once a year; some of it becomes worth doing after the first job.
