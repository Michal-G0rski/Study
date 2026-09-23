# Monthly plans

One file per calendar month. Each file says **what has to be worked through**, week by week and day by day — the reading, the exercises, the programs that have to exist by Sunday.

What these files deliberately do not contain: environment setup, toolchain installation, editor configuration, shell commands, links to open. That belongs to whatever you use to start a session, not to the plan.

The [main plan](../README.md) says what to learn and why. These files say what to do this week.

## How a week runs

Fifteen hours: **2.5 h a day, Monday to Saturday, Sunday off.** Sunday is the checkpoint — the "Done by Sunday" list either ticks or it does not.

## Standing rules

- The SOC track never slips two days running. In Stage 1 it is networking and Windows; in Stage 2 it is Sentinel, KQL, and the Purple-Team project. It is the one prerequisite in this plan with no workaround.
- When a week is short, the order things get dropped is: lectures first, then second-pass reading. **Never the programs.** Reading about this transfers badly; writing it transfers.
- A missed day moves to Sunday, at most once a month.
- Do not run ahead. Work scheduled for Thursday that you reach on Tuesday gets *read* on Tuesday and *done* on Thursday.
- One commit per study day. An empty day is visible in `git log` and that is the point.
- **The source's own order wins** — for the backlog material in the [main plan](../README.md#after-the-checkpoint) too, whenever you get to it: where a course's internal sequence disagrees with your plans, follow the course. Belts are earned sequentially on pwn.college, Arch1001's chapters are ordered, PortSwigger topics build on each other.
- **Job-search networking runs from month 1, outside the 15 hours: 15–20 minutes a day.** Comment usefully on posts from people actually working in the target roles before you ever message any of them; from month 4, send connection requests that reference something specific and real about the recipient's work — never a template — and if one goes unanswered, follow up once after 3–5 days, then stop. It lives outside the study budget on purpose, so it never competes with the programs for hours, and it starts in month 1 rather than at month 4 because the arithmetic is lopsided: cold applications convert at 0.1–2%, referrals at roughly 30%, with interviews at 10–20 times the rate. The [main plan](../README.md#how-people-actually-get-hired) carries the full numbers and the reasoning.

## Index

Month | Stage | The month in one line
:-- | :-- | :--
[October 2026](2026-10.md) | 1 — Foundations for SOC | Missing Semester, Linux CLI, networking ch. 1–3 + Wireshark labs
[November 2026](2026-11.md) | 1 — Foundations for SOC | Networking ch. 4–6 + first hostile capture, Python log parsing & threat intel
[December 2026](2026-12.md) | 1 — Foundations for SOC | Windows Fundamentals, PowerShell, Sysmon, AD basics
[January 2027](2027-01.md) | 1 — Foundations for SOC | Active Directory deep dive, Kerberos, attack mapping, consolidation week + market spot-check
[February 2027](2027-02.md) | 2 — SOC Operations | Sentinel concepts & KQL begin (Log Analytics demo environment); Wazuh installed
[March 2027](2027-03.md) | 2 — SOC Operations | Sentinel/KQL finishes; MITRE ATT&CK begins
[April 2027](2027-04.md) | 2 — SOC Operations | ATT&CK finishes, phishing/email-analysis module, incident #2, SC-200 booked
[May 2027](2027-05.md) | 2 — SOC Operations | SC-200 exam prep: Defender XDR, Defender for Cloud, Entra ID (Learn modules + docs, concept); Defender/Entra writeup
[June 2027](2027-06.md) | 2 — SOC Operations | Exam prep finishes, **SC-200 sat**, Purple-Team build begins
[July 2027](2027-07.md) | 2 — SOC Operations | Purple-Team: Attack → Detect twice over — KQL/Sigma, then native Wazuh
[August 2027](2027-08.md) | 2 + Checkpoint | Triage practice, interview vocab, CV, market re-measure, applications sent

The plan's fixed schedule ends with August 2027 and the checkpoint. There are no monthly files after that, on purpose — what comes next is the [backlog](../README.md#after-the-checkpoint), and it is driven by the job you land, not by a calendar someone wrote in advance.

## What the fixed schedule holds

The [main plan](../README.md) is a curriculum. This is a calendar. They do not fit each other, and this section is the honest accounting.

Eleven months at 15 h/week ≈ 680 hours. The fixed schedule spends them on:

- **Stage 1 (months 1–4, ~252.5 h):** Missing Semester, Kurose networking (ch. 1–6) with the book's Wireshark labs and a first hostile capture (run through Suricata/Zeek for a first IDS pass), Python for log parsing & threat intel, Windows Fundamentals and the core event IDs, PowerShell (Script Block Logging included), Sysmon, Linux log triage (auth.log, journald, auditd), Active Directory, Kerberos, three AD attacks reproduced and detected, a consolidation week before Stage 2 opens.
- **Stage 2 (months 5–11, ~425 h):** KQL fluency (practised free in the Log Analytics demo environment and a free Azure Data Explorer cluster, no personal Azure subscription), Sentinel analytics-rule/workbook/hunting concepts, a detection library built in parallel in self-hosted [Wazuh](https://wazuh.com/), MITRE ATT&CK mapping, LetsDefend incidents (3 full end-to-end, each worked through the NIST 800-61/PICERL lifecycle and mapped to the Cyber Kill Chain and Pyramid of Pain), CVE/CVSS reading (CVSS v3.1 vectors and severity bands), traffic-analysis PCAP exercises, a phishing/email-analysis module (SPF/DKIM/DMARC, urlscan.io and sandboxed sample analysis, PyTriage extended with `.eml` parsing), Defender XDR / Defender for Cloud / Entra ID studied as concept from free Learn modules and docs (no live tenant), SC-200 certificate, Purple-Team project (Instrument → Attack → Detect, with detections written twice — KQL/Sigma and native Wazuh).
- **Artifacts produced:** PyTriage CLI with `.eml` parsing (GitHub + blog writeup), Windows cheat sheet (blog), AD attack mapping (blog), KQL + Wazuh detection library (blog + GitHub), MITRE ATT&CK page (blog), phishing triage playbook (blog), Defender XDR/Entra investigation writeup (blog), 3 incident reports (blog), Purple-Team flagship writeup across two detection engines (blog + GitHub with KQL, Sigma and Wazuh rules), SC-200 certificate. The blog carries eight technical writeups; the incident reports and the certificate sit alongside them.

The deep curriculum that does **not** fit — because it was never going to, and because the market research says it has no junior queue to wait in — is the [backlog](../README.md#after-the-checkpoint): roughly 1000+ hours of material even after aggressive trimming.

### What was deferred, and why

Nothing here was dropped by accident. Each is a decision with a reason, and each is picked up after the checkpoint, driven by the job.

- **C, Effective C, assembly** — deferred. The fixed schedule spends zero hours on them. They are the prerequisite for CS:APP, pwn.college, Ghidra, and firmware work. They live in the backlog.
- **Mathematics for Computer Science (MIT 6.042J)** — deferred from Stage 1. None of the target junior postings (SOC, QA, Detection Engineer) name discrete math or number theory, so the roughly 5 hours/week it used to take go to Python/KQL instead. It is not gone — Cryptopals still assumes it.
- **Nand to Tetris Part I and II** — deferred. Part I is the highest-value single backlog item for embedded-C roles; Part II (compiler and OS) further still, since its stack-machine payoff is met in CS:APP chapter 3.
- **CS:APP with the four labs** — deferred, and it is the default first pick from the backlog. It is the single largest thing the old plan carried and everything in the exploitation and RE sections assumes it.
- **OSTEP** — deferred; the operating-systems material is met in CS:APP chapters 8, 9, 10 and 12.
- **The whole of the old low-level Stages** — Arch1001, Arch2001, ARM, RE101, Ghidra, Practical Malware Analysis, crackmes. Junior RE openings measured at zero nationally in September 2026; this material is portfolio-gated, not schedule-gated.
- **The whole of the old firmware/embedded Stages** — ESP32, buses, Hardware Hacking Handbook, Practical IoT Hacking, OWASP FSTM, Microcorruption, ChipWhisperer. Junior firmware openings measured at zero.
- **The whole PortSwigger track, and eJPT with it** — deferred from Stage 2 in September 2026. Zero junior pentest openings measured on 45 live offers; the junior queue that exists is SOC operations. The beginner-to-intermediate half is the junior pentester's grounding and the advanced half — insecure deserialization, web cache poisoning, GraphQL, NoSQL, race conditions, WebSockets, clickjacking, CORS, web LLM attacks, API testing — sits above it. Each topic stays free and is a week's work if a posting ever asks.
- **OSCP / PEN-200** — a decision, not a schedule item. It is a full-load commitment with a 24-hour exam; it cannot share a calendar with anything. Decide with a job and a re-measured market in front of you.
- **pwn.college's deeper belts** (System Security's kernel and microarchitecture modules) — among the deepest material on the platform, post-backlog-entry by design.
- **ChipWhisperer fault injection** and the hardware-bound side-channel labs — SCA101's simulated labs are the entry point; the rest needs the board and dedicated hours.
- **Practical Binary Analysis, exploit.education** — already optional in the old plan; still optional.
- **Splunk (Free tier)** — not scheduled. The detection library already exists in two engines (KQL/Sigma and Wazuh), which answers the "is this just a Microsoft-tools plan?" question without adding a third paid-adjacent tool on a calendar that does not need one. Splunk Free (500 MB/day, no expiration, no card required) is a same-day addition if a specific posting names it — translating the existing KQL library to SPL is a few hours' work, not a new module.

### The order to pick them up in

After the checkpoint, the job picks. The reasoning and the role-by-role order are in the [main plan](../README.md#the-order-to-pick-them-up-in); the one default worth repeating here: if nothing has landed and you want the single most-leveraged item, it is **CS:APP with the labs**.

It is not an unfinished plan. It is an eleven-month plan that ends in applications, and a backlog that begins with a job.
