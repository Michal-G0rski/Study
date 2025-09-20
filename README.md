<div align="center" style="text-align: center">
<img src="images/ossu-logo.webp" alt="Open Source Society logo"/>
<h3>Open Source Society University — Custom Path</h3>
<p>
  Tailored study plan for: web apps, security testing, and cloud (remote-ready developer / pentester track)
</p>
<p>
  <a href="https://github.com/sindresorhus/awesome">
    <img alt="Awesome" src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg"
  ></a>
  <a href="https://github.com/ossu/computer-science">
    <img alt="Open Source Society University - Computer Science" src="https://img.shields.io/badge/OSSU-computer--science-blue.svg"
  ></a>
</p>
</div>

# Contents

- [Summary](#summary)
- [Curriculum](#curriculum)
  - [Intro CS](#intro-cs)
  - [Core programming](#core-programming)
  - [Core math](#core-math)
  - [CS Tools](#cs-tools)
  - [Core systems](#core-systems)
  - [Core theory](#core-theory)
  - [Core security](#core-security)
  - [Core applications](#core-applications)
- [Final project](#final-project)
- [Team](#team)

# Summary

This is a trimmed, OSSU-linked study plan targeted at your goals (web apps → security testing → cloud).
I kept OSSU's course choices and durations/effort estimates and added **prerequisites** for each course as OSSU lists them. Use this `.md` as your personal study checklist: fork the OSSU repo and keep ✅ marks next to completed items.

---

## Curriculum

> Note: Duration / Effort / Prerequisites are taken from OSSU (links in each course). See **Sources** at the end.

### [Intro CS](https://github.com/ossu/computer-science#intro-cs)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Introduction to Computer Science and Programming using Python](https://github.com/ossu/computer-science/blob/master/coursepages/intro-cs/README.md) | 14 weeks | 6–10 hours/week | [High school algebra](https://ossu.dev/precollege-math)

### [Core programming](https://github.com/ossu/computer-science#core-programming)

**Topics covered**: functional programming, testing, design patterns, OOP, static/dynamic typing, ML & Lisp family exposure.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) | 13 weeks | 8–10 hours/week | none
[Class-based Program Design](https://course.ccs.neu.edu/cs2510sp22/index.html) | 13 weeks | 5–10 hours/week | Systematic Program Design, High School Math
[Programming Languages (CSE341)](https://courses.cs.washington.edu/courses/cse341/19au/) | 11 weeks | 4–8 hours/week | Systematic Program Design
[Object-Oriented Design (CS3500)](https://course.ccs.neu.edu/cs3500f19/) | 13 weeks | 5–10 hours/week | Class-Based Program Design
[Software Architecture (Coursera)](https://www.coursera.org/learn/software-architecture) | 4 weeks | 2–5 hours/week | Object-Oriented Design

### [Core math](https://github.com/ossu/computer-science#core-math)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Calculus 1A: Differentiation (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.1x+2T2019/about) (alt: OCW) | 13 weeks | 6–10 hours/week | High school math
[Calculus 1B: Integration (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.2x+3T2019/about) | 13 weeks | 5–10 hours/week | Calculus 1A
[Calculus 1C: Coordinate Systems & Infinite Series (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.3x+1T2020/about) | 6 weeks | 5–10 hours/week | Calculus 1B
[Mathematics for Computer Science (MIT OL)](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about) | 13 weeks | 5 hours/week | Calculus 1C

### [CS Tools](https://github.com/ossu/computer-science#cs-tools)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 12 hours/week | -

### [Core systems](https://github.com/ossu/computer-science#core-systems)

**You said you only need basic understanding** — OSSU picks these canonical courses.

Courses | Duration | Effort | Additional Text / Assignments | Prerequisites
:-- | :--: | :--: | :--: | :--:
[Build a Modern Computer from First Principles: From Nand to Tetris (Coursera)](https://www.coursera.org/learn/build-a-computer) (alt: [nand2tetris.org](https://www.nand2tetris.org/)) | 6 weeks | 7–13 hours/week | - | C-like programming language
[Build a Modern Computer from First Principles: Nand to Tetris Part II (Coursera)](https://www.coursera.org/learn/nand2tetris2) | 6 weeks | 12–18 hours/week | - | One of the recommended languages; Nand2Tetris Part I
[Operating Systems: Three Easy Pieces (OSSU page)](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md) | 10–12 weeks | 6–10 hours/week | - | Nand2Tetris Part II
[Computer Networking: a Top-Down Approach (online lectures)](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | | algebra, probability, basic CS

### [Core theory](https://github.com/ossu/computer-science#core-theory)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Divide and Conquer, Sorting and Searching, and Randomized Algorithms (Coursera)](https://www.coursera.org/learn/algorithms-divide-conquer) | 4 weeks | 4–8 hours/week | any programming language, Mathematics for Computer Science
[Graph Search, Shortest Paths, and Data Structures (Coursera)](https://www.coursera.org/learn/algorithms-graphs-data-structures) | 4 weeks | 4–8 hours/week | Divide & Conquer course
[Greedy Algorithms, Minimum Spanning Trees, and Dynamic Programming (Coursera)](https://www.coursera.org/learn/algorithms-greedy) | 4 weeks | 4–8 hours/week | Graphs course
[Shortest Paths Revisited, NP-Complete Problems (Coursera)](https://www.coursera.org/learn/algorithms-npcomplete) | 4 weeks | 4–8 hours/week | Greedy / DP course

### [Core security](https://github.com/ossu/computer-science#core-security)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Cybersecurity Fundamentals (edX)](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals) | 8 weeks | 10–12 hours/week | -
[Principles of Secure Coding (Coursera)](https://www.coursera.org/learn/secure-coding-principles) | 4 weeks | 4 hours/week | -
[Identifying Security Vulnerabilities (Coursera)](https://www.coursera.org/learn/identifying-security-vulnerabilities) | 4 weeks | 4 hours/week | -

**Choose one of the following (OSSU):**
[Identifying Security Vulnerabilities in C/C++ (Coursera)](https://www.coursera.org/learn/identifying-security-vulnerabilities-c-programming) — or — [Exploiting & Securing Vulnerabilities in Java (Coursera)](https://www.coursera.org/learn/exploiting-securing-vulnerabilities-java-applications)

### [Core applications](https://github.com/ossu/computer-science#core-applications)

(Only do the OSSU items that are relevant — OSSU lists DB & Fullstack resources)

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Databases: Modeling and Theory (edX)](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 weeks | 10 hours/week | Core programming
[Databases: Relational Databases and SQL (edX)](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 weeks | 10 hours/week | Core programming

---

## [Final project](https://github.com/ossu/computer-science#final-project)

Pick one — OSSU recommends these (I left the one you already chose):

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks | 15 hours/week | programming

---

## Team

*(you asked to include only your stuff — replace the placeholder below with your GitHub/name)*

- **[Your Name / GitHub]**: *add your GitHub profile link here*

---

## How to use

1. Fork the OSSU repo and create a personal checklist (add ✅ as you finish).
2. Work in ordered groups: Core programming + Core math first, then Core systems/theory/security.
3. When ready for hands-on security work, pair the Coursera security courses with practice on CTF platforms and WebGoat/OWASP Juice Shop.
