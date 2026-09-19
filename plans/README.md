# Monthly plans

One file per calendar month. Each file says **what has to be worked through**, week by week and day by day — the reading, the exercises, the programs that have to exist by Sunday.

What these files deliberately do not contain: environment setup, toolchain installation, editor configuration, shell commands, links to open. That belongs to whatever you use to start a session, not to the plan.

The [main plan](../README.md) says what to learn and why. These files say what to do this week.

## How a week runs

Fifteen hours: **2.5 h a day, Monday to Saturday, Sunday off.** Sunday is the checkpoint — the "Done by Sunday" list either ticks or it does not.

## Standing rules

- The C track never slips two days running. In Stage 1 it is Modern C; from Stage 2 on it is the networking and security work the month carries. It is the one prerequisite in this plan with no workaround.
- When a week is short, the order things get dropped is: lectures first, then second-pass reading. **Never the programs.** Reading about this transfers badly; writing it transfers.
- A missed day moves to Sunday, at most once a month.
- Do not run ahead. Work scheduled for Thursday that you reach on Tuesday gets *read* on Tuesday and *done* on Thursday.
- One commit per study day. An empty day is visible in `git log` and that is the point.
- **The source's own order wins** — for the backlog material in the [main plan](../README.md#after-the-checkpoint) too, whenever you get to it: where a course's internal sequence disagrees with your plans, follow the course. Belts are earned sequentially on pwn.college, Arch1001's chapters are ordered, PortSwigger topics build on each other.

## Index

Month | Stage | The month in one line
:-- | :-- | :--
[October 2026](2026-10.md) | 1 — Foundations | Modern C through Level 2, Missing Semester, mathematics starts
[November 2026](2026-11.md) | 1 — Foundations | Modern C finished; first binary-format work
[December 2026](2026-12.md) | 1 + 2 opens | networking starts, the blog goes live
[January 2027](2027-01.md) | 1 closes + 2 | networking through the link layer, mathematics into graphs, Stage 1 ends
[February 2027](2027-02.md) | 2 | the networking book finishes; PortSwigger opens at full width
[March 2027](2027-03.md) | 2 | the PortSwigger track closes
[April 2027](2027-04.md) | 2 | the eJPT exam sat
[May 2027](2027-05.md) | 2 | the own app built, then broken
[June 2027](2027-06.md) | 2 + checkpoint | SOC basics; **the checkpoint opens, first applications sent**

The plan's fixed schedule ends with June 2027 and the checkpoint. There are no monthly files after that, on purpose — what comes next is the [backlog](../README.md#after-the-checkpoint), and it is driven by the job you land, not by a calendar someone wrote in advance.

## What the fixed schedule holds

The [main plan](../README.md) is a curriculum. This is a calendar. They do not fit each other, and this section is the honest accounting of the gap rather than a pretence that there isn't one.

### The arithmetic

The fixed schedule runs from October 2026 to the end of June 2027: nine calendar months, at 2.5 hours a day, six days a week, minus the public holidays that land on study days (two December days, 1 January, 6 January, Easter Monday, 1 May, 3 and 27 May, 6 June). That comes to roughly **645 study hours**.

What has to fit in them: all of Modern C and the Stage 1 programs (done in ~325 hours over the first four months, exactly as originally planned), the rest of Kurose and Beej with three protocol programs, the mathematics tail, the full beginner-to-intermediate PortSwigger track, eJPT preparation and the exam itself, an own web application built and then broken with a published writeup, the SOC basics unit, and the checkpoint month's CV, market re-measurement and first applications. That fits — with the slack the old plan never had, because Nand to Tetris, CS:APP and OSTEP are no longer competing for the same hours.

The deep curriculum that does **not** fit — because it was never going to, and because the market research says it has no junior queue to wait in — is the [backlog](../README.md#after-the-checkpoint): roughly 1,050–1,200 hours of material even after aggressive trimming.

### What was deferred, and why

Nothing here was dropped by accident. Each is a decision with a reason, and each is picked up after the checkpoint, driven by the job.

- **Nand to Tetris Part I and II** — deferred from Stage 2. Part I is the highest-value single backlog item for embedded-C roles; Part II (compiler and OS) further still, since its stack-machine payoff is met in CS:APP chapter 3.
- **CS:APP with the four labs** — deferred, and it is the default first pick from the backlog. It is the single largest thing the old plan carried and everything in the exploitation and RE sections assumes it.
- **OSTEP** — deferred; the operating-systems material is met in CS:APP chapters 8, 9, 10 and 12.
- **The whole of the old Stage 3** — Arch1001, Arch2001, ARM, RE101, Ghidra, Practical Malware Analysis, crackmes. Junior RE openings measured at zero nationally in September 2026; this material is portfolio-gated, not schedule-gated.
- **The whole of the old Stage 4** minus the own-app project, which moved *up* into the fixed schedule (month 8) because it is the one offense item with junior market value. pwn.college, Nightmare, ROP Emporium and exploit.education are backlog.
- **The whole of the old Stage 5** — ESP32, buses, the Hardware Hacking Handbook, Practical IoT Hacking, OWASP FSTM, Microcorruption, ChipWhisperer. Junior firmware openings measured at zero.
- **The PortSwigger advanced track** — insecure deserialization, web cache poisoning, GraphQL, NoSQL, race conditions, WebSockets, clickjacking, CORS, web LLM attacks, API testing — deliberately not closed. Each stays free and is a week's work if a posting ever asks.
- **OSCP / PEN-200** — a decision, not a schedule item. It is a full-load commitment with a 24-hour exam; it cannot share a calendar with anything. Decide with a job and a re-measured market in front of you.
- **pwn.college's deeper belts** (System Security's kernel and microarchitecture modules) — among the deepest material on the platform, post-backlog-entry by design.
- **ChipWhisperer fault injection** and the hardware-bound side-channel labs — SCA101's simulated labs are the entry point; the rest needs the board and dedicated hours.
- **Practical Binary Analysis, exploit.education** — already optional in the old plan; still optional.

### The order to pick them up in

After the checkpoint, the job picks. The reasoning and the role-by-role order are in the [main plan](../README.md#the-order-to-pick-them-up-in); the one default worth repeating here: if nothing has landed and you want the single most-leveraged item, it is **CS:APP with the labs**.

It is not an unfinished plan. It is a nine-month plan that ends in applications, and a backlog that begins with a job.
