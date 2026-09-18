# Monthly plans

One file per calendar month. Each file says **what has to be worked through**, week by week and day by day — the reading, the exercises, the programs that have to exist by Sunday.

What these files deliberately do not contain: environment setup, toolchain installation, editor configuration, shell commands, links to open. That belongs to whatever you use to start a session, not to the plan.

The [main plan](../README.md) says what to learn across eighteen months and why. These files say what to do this week.

## How a week runs

Fifteen hours: **2.5 h a day, Monday to Saturday, Sunday off.** Sunday is the checkpoint — the "Done by Sunday" list either ticks or it does not.

## Standing rules

- The C track never slips two days running. In Stage 1 it is Modern C; after that it is whatever C work the month carries. It is the one prerequisite in this plan with no workaround.
- When a week is short, the order things get dropped is: lectures first, then second-pass reading, then mathematics. **Never the programs.** Reading about this transfers badly; writing it transfers.
- A missed day moves to Sunday, at most once a month.
- Do not run ahead. Work scheduled for Thursday that you reach on Tuesday gets *read* on Tuesday and *done* on Thursday.
- One commit per study day. An empty day is visible in `git log` and that is the point.
- From Stage 3 on, the source's own order wins. Where a day row and a course disagree about sequence, follow the course; the day rows are the workload, not a re-ordering of it.

## Index

Month | Stage | The month in one line
:-- | :-- | :--
[October 2026](2026-10.md) | 1 — Foundations | Modern C through Level 2, Missing Semester, mathematics starts
[November 2026](2026-11.md) | 1 — Foundations | Modern C finished; first binary-format work
[December 2026](2026-12.md) | 1 + 2 opens | networking starts, the blog goes live
[January 2027](2027-01.md) | 1 closes + 2 | networking through the link layer, mathematics into graphs, Stage 1 ends
[February 2027](2027-02.md) | 2 + employability | the networking book finishes, nand2tetris starts, PortSwigger opens
[March 2027](2027-03.md) | 2 — Systems | Nand to Tetris Part I finished; PortSwigger deepens; eJPT booked
[April 2027](2027-04.md) | 2 + employability | CS:APP opens with the Data Lab; the eJPT exam sat
[May 2027](2027-05.md) | 2 — Systems | CS:APP chapter 3 and the Bomb Lab; the PortSwigger track closes
[June 2027](2027-06.md) | 2 + checkpoint | CS:APP chapter 7 and the Attack Lab; the checkpoint opens, first applications sent
[July 2027](2027-07.md) | 2 + checkpoint | virtual memory and the Malloc Lab; the first CTF writeup
[August 2027](2027-08.md) | 2 closes, 3 opens | CS:APP finishes; Arch1001 opens
[September 2027](2027-09.md) | 3 — Low-level | Arch1001 finished; your own x86-64 reference
[October 2027](2027-10.md) | 3 + 4 opens | Ghidra and the first script; pwn.college opens
[November 2027](2027-11.md) | 4 — Offense | ARM; the first pwn.college belt; ten crackmes
[December 2027](2027-12.md) | 4 + 5 opens | Program Security and RE101; the ESP32 arrives
[January 2028](2028-01.md) | 4 + 5 | ROP for real; the first firmware extraction; the OSCP decision
[February 2028](2028-02.md) | 4 + 5 | the second belt; firmware analysis; Microcorruption
[March 2028](2028-03.md) | 5 — the last month | build it and break it; a teardown, a CVE attempt, the review

The plan ends in March 2028 mid-curriculum, and on purpose. The arithmetic below says why, and records everything that was deferred to make eighteen months fit fifteen hours a week.

## What eighteen months actually holds

The [main plan](../README.md) is a curriculum. This is a calendar. They do not fit each other, and this section is the honest accounting of the gap rather than a pretence that there isn't one.

### The arithmetic

The thirteen months from March 2027 to March 2028 supply, after every public holiday is deducted, **830 study hours** — 2.5 hours a day, six days a week, minus the days the calendar takes back. The five months before them add roughly 325 more. Call it **1,150 hours** across the whole eighteen.

The sources the main plan names, worked at the depth they deserve, come to somewhere between **1,050 and 1,200 hours after trimming** — and that trimming is already aggressive. Nand to Tetris is two courses. CS:APP is a semester with seven labs. pwn.college is four belts, each a course in itself. OST2 is three courses. Stage 5 is three books, two hardware platforms and a firmware methodology. Add the certifications, the portfolio, and the applications, and the untrimmed total is closer to double the hours available.

So the curriculum does not fit, it was never going to fit, and the plan's own answer is the [employability checkpoint at months 9–10](../README.md#employability-checkpoint--months-910): **get hired mid-plan, and the second half becomes paid study instead of a race to finish a syllabus.** By month 18 the intended outcome is a job and a portfolio, not a completed curriculum. That is not the plan falling short of its goal. That is the goal.

### What that costs in timing

Because the hours are real, the stages land later than the main plan's published bands:

- **Stage 3 opens in month 11 (August 2027)**, not month 8. CS:APP is the reason — it is the largest single thing in the plan and it earns its months.
- **Stage 4 opens in month 13 (October 2027)**, not month 10, once Ghidra is in hand.
- **Stage 5 opens in month 15 (December 2027)** — inside its month 13–18 band, but at reduced depth, and it closes the plan rather than completing itself.

This is stated so it is not discovered. A plan that silently runs three months behind its own headings is worse than one that says where it stands.

### What was deferred, and why

Nothing here was dropped by accident. Each of these is a decision with a reason, and each is a candidate for the months after month 18.

- **Nand to Tetris Part II** (the compiler and OS half) — deferred entirely. The stack-machine and translation payoff is met in CS:APP chapter 3 and again across Stage 4. Part I, the hardware half, is kept and finishes in March 2027.
- **OSTEP** — deferred with Part II, since it followed it. The operating-systems material is relocated into CS:APP chapters 8, 9, 10 and 12, which the plan reads in full.
- **CS:APP chapter 4** (processor architecture) — not scheduled. Nand to Tetris project 5 builds a CPU, and CMU no longer lectures the chapter.
- **CS:APP chapter 5** (optimising performance) — not scheduled. A genuine trade, not a duplicate: it is about making code fast, and this path is about making code do what it was not meant to.
- **CS:APP chapter 11** (network programming) — not scheduled. Done the hard way already in December–January: Kurose and Beej, plus a TCP server, a DNS resolver that builds its own packets, and a traceroute that reads ICMP.
- **The Cache Lab** — dropped; its reading, sections 6.4–6.7, is kept in full. It is a performance lab, and the cache *reading* is what the Stage 5 side-channel work needs, not the matrix-transpose optimisation.
- **The PortSwigger advanced track** — insecure deserialization, web cache poisoning, GraphQL, NoSQL, race conditions, WebSockets, clickjacking, CORS, web LLM attacks, API testing — deliberately not closed. None is on the path to the target roles; each stays free and is a week's work if a posting ever asks.
- **OST2 Arch2001** (x86-64 OS internals) — not scheduled anywhere. Its published sub-lessons carry question counts in the hundreds; it is far heavier than its chapter count suggests, and its subject is met in CS:APP chapter 9 and in pwn.college's kernel modules. Its prerequisite, Arch1001, is done, so it is ready to pick up first after month 18 if kernel work is the direction.
- **Practical Malware Analysis** — reduced to the RE101 workshop in December, which covers the primer in the hours available. The full book is post-plan.
- **exploit.education** — deferred; it overlaps pwn.college's early modules, which are scheduled instead.
- **Practical Binary Analysis** — already optional in the main plan; left optional.
- **OSCP / PEN-200** — not scheduled, and made an explicit [decision point in January 2028](2028-01.md). PEN-200 is a roughly three-month full-load commitment with a 24-hour exam; it cannot share a calendar with a live Stage 4 and Stage 5 at fifteen hours a week. The decision — go, defer, or drop — is driven by the re-measured market and by whether a job has landed.
- **pwn.college System Security's later belts** (kernel security, microarchitecture exploitation, system exploitation) — opened in February, not finished. Among the deepest material on the platform, and post-plan by design.
- **ChipWhisperer fault injection** and the trace-based side-channel labs — post-plan. SCA101's simulated power-analysis labs are done in March; the hardware-bound work needs the board and the hours the plan does not have.

### The order to pick them up in

After month 18, if study continues, the sequence that wastes the least: **finish the pwn.college belts** (System Security, then Software Exploitation) because they are already open and sequential; **Arch2001** if the work is going kernel-wards; **OSCP** if it was deferred and the market rewards it; **ChipWhisperer fault injection** if the work is going hardware-wards; and the **PortSwigger advanced topics** one at a time, on demand, when a role names one.

It is not an unfinished plan. It is the start of the next one.
