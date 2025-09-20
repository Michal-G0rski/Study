<div align="center" style="text-align: center">
<img src="https://raw.githubusercontent.com/ossu/computer-science/master/images/ossu-logo.webp" alt="Open Source Society logo" width="200"/>
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
  - [Advanced programming](#advanced-programming)
  - [Advanced theory](#advanced-theory)
  - [Advanced information security](#advanced-information-security)
  - [Advanced math](#advanced-math)
- [Final project](#final-project)
- [How to use](#how-to-use)
- [Team](#team)

# Summary

This is a customized study plan based on the OSSU curriculum, targeted at your specific goals: web applications, security testing, and cloud computing. It trims the full curriculum to focus on relevant areas and provides Python-based alternatives for certain topics as requested.

This plan uses the course structure, duration, and effort estimates from the official OSSU repository. You can use this document as your personal study checklist. It's recommended to fork the [OSSU repo](https://github.com/ossu/computer-science) and mark your progress there.

---

## Curriculum

> **Note**: Duration, Effort, and Prerequisites are taken from the OSSU repository.

### Intro CS

This course provides a gentle but solid introduction to computer science and programming.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Introduction to Computer Science and Programming using Python](https://github.com/ossu/computer-science/blob/master/coursepages/intro-cs/README.md) | 14 weeks | 6–10 hours/week | High school algebra | OSSU Discord

### Core programming

**Topics covered**: functional programming, testing, design patterns, object-oriented programming (OOP), static/dynamic typing.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Systematic Program Design](https://github.com/ossu/computer-science/blob/master/coursepages/spd/README.md) | 13 weeks | 8–10 hours/week | none | OSSU Discord
**[Python Alternative]** Object-Oriented Programming | 10-13 weeks | 5–10 hours/week | Systematic Program Design | This replaces `Class-based Program Design` and `Object-Oriented Design`. Recommended Resource: Book **"Object-Oriented Python: Master OOP by Building Games and GUIs"** by Irv Kalb. Free alternative: [Real Python's OOP Tutorial](https://realpython.com/python3-object-oriented-programming/).
[Programming Languages](https://github.com/ossu/computer-science/blob/master/coursepages/pl/README.md) | 11 weeks | 4–8 hours/week | Systematic Program Design | OSSU Discord
[Software Architecture](https://www.coursera.org/learn/software-architecture) | 4 weeks | 2–5 hours/week | Object-Oriented Programming knowledge | OSSU Discord

### Core math

**Topics covered**: calculus, discrete mathematics, mathematical proofs, basic statistics, and probability.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Calculus 1A: Differentiation](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.1x+2T2019/about) | 13 weeks | 6–10 hours/week | High school math | OSSU Discord
[Calculus 1B: Integration](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.2x+3T2019/about) | 13 weeks | 5–10 hours/week | Calculus 1A | OSSU Discord
[Calculus 1C: Coordinate Systems & Infinite Series](https://openlearninglibrary.mit.edu/courses/course-v1:MITx+18.01.3x+1T2020/about) | 6 weeks | 5–10 hours/week | Calculus 1B | OSSU Discord
[Mathematics for Computer Science](https://openlearninglibrary.mit.edu/courses/course-v1:OCW+6.042J+2T2019/about) | 13 weeks | 5 hours/week | Calculus 1C | OSSU Discord

### CS Tools

**Topics covered**: terminals and shell scripting, vim, command line environments, and version control.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) | 2 weeks | 12 hours/week | - | OSSU Discord

### Core systems

**Topics covered**: boolean algebra, gate logic, memory, computer architecture, assembly, virtual machines, compilers, operating systems, and network protocols.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Build a Modern Computer from First Principles: From Nand to Tetris](https://www.coursera.org/learn/build-a-computer) | 6 weeks | 7–13 hours/week | C-like programming language | OSSU Discord
[Build a Modern Computer from First Principles: Nand to Tetris Part II](https://www.coursera.org/learn/nand2tetris2) | 6 weeks | 12–18 hours/week | Nand to Tetris Part I | OSSU Discord
[Operating Systems: Three Easy Pieces](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/README.md) | 10–12 weeks | 6–10 hours/week | Nand to Tetris Part II | OSSU Discord
[Computer Networking: a Top-Down Approach](https://gaia.cs.umass.edu/kurose_ross/online_lectures.htm) | 8 weeks | 4–12 hours/week | algebra, probability, basic CS | OSSU Discord

### Core theory

**Topics covered**: divide and conquer, sorting and searching, graph search, data structures, greedy algorithms, dynamic programming, and NP-completeness.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Divide and Conquer, Sorting and Searching, and Randomized Algorithms](https://www.coursera.org/learn/algorithms-divide-conquer) | 4 weeks | 4–8 hours/week | any programming language, Math for CS | OSSU Discord
[Graph Search, Shortest Paths, and Data Structures](https://www.coursera.org/learn/algorithms-graphs-data-structures) | 4 weeks | 4–8 hours/week | Previous course | OSSU Discord
[Greedy Algorithms, Minimum Spanning Trees, and Dynamic Programming](https://www.coursera.org/learn/algorithms-greedy) | 4 weeks | 4–8 hours/week | Previous course | OSSU Discord
[Shortest Paths Revisited, NP-Complete Problems](https://www.coursera.org/learn/algorithms-npcomplete) | 4 weeks | 4–8 hours/week | Previous course | OSSU Discord

### Core security

**Topics covered**: Confidentiality, Integrity, Availability, Secure Design, Defensive Programming, Threats and Attacks, Network Security, and Cryptography.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Cybersecurity Fundamentals](https://www.edx.org/learn/cybersecurity/rochester-institute-of-technology-cybersecurity-fundamentals) | 8 weeks | 10–12 hours/week | - | OSSU Discord
[Principles of Secure Coding](https://www.coursera.org/learn/secure-coding-principles) | 4 weeks | 4 hours/week | - | OSSU Discord
[Identifying Security Vulnerabilities](https://www.coursera.org/learn/identifying-security-vulnerabilities) | 4 weeks | 4 hours/week | - | OSSU Discord

### Core applications

**Topics covered**: Agile methodology, REST, relational databases, transaction processing, and data modeling.

Courses | Duration | Effort | Prerequisites | Discussion
:-- | :--: | :--: | :--: | :--:
[Databases: Modeling and Theory](https://www.edx.org/learn/databases/stanford-university-databases-modeling-and-theory) | 2 weeks | 10 hours/week | Core programming | OSSU Discord
[Databases: Relational Databases and SQL](https://www.edx.org/learn/relational-databases/stanford-university-databases-relational-databases-and-sql) | 2 weeks | 10 hours/week | Core programming | OSSU Discord
[Databases: Semistructured Data](https://www.edx.org/learn/databases/stanford-university-databases-semistructured-data) | 2 weeks | 10 hours/week | Core programming | OSSU Discord

### Advanced programming

**Topics covered**: debugging, goal-oriented programming, software testing, and parallel computing.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Software Debugging](https://www.udacity.com/course/software-debugging--cs259) | 8 weeks | 6 hours/week | Python, OOP
[Software Testing](https://www.udacity.com/course/software-testing--cs258) | 4 weeks | 6 hours/week | Python, programming experience

### Advanced theory

**Topics covered**: formal languages, Turing machines, and computability.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Theory of Computation](https://ocw.mit.edu/courses/18-404j-theory-of-computation-fall-2020/) | 13 weeks | 10 hours/week | Math for CS, logic, algorithms

### Advanced information security

A deep dive into security topics critical for penetration testing.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Web Security Fundamentals](https://www.edx.org/learn/cybersecurity/ku-leuven-web-security-fundamentals) | 5 weeks | 4-6 hours/week | Basic web technologies
[Security Governance & Compliance](https://www.coursera.org/learn/security-governance-compliance) | 3 weeks | 3 hours/week | -
[Digital Forensics Concepts](https://www.coursera.org/learn/digital-forensics-concepts) | 3 weeks | 2-3 hours/week | Core Security
[Secure Software Development: Requirements, Design, and Reuse](https://www.coursera.org/learn/secure-software-development-requirements-design-reuse) | 7 weeks | 1-2 hours/week | Core Programming and Security
[Secure Software Development: Implementation](https://www.coursera.org/learn/secure-software-development-implementation) | 7 weeks | 1-2 hours/week | Previous course
[Secure Software Development: Verification and More](https://www.coursera.org/learn/secure-software-development-verification-specialized-topics) | 7 weeks | 1-2 hours/week | Previous course

### Advanced math

**Topics covered**: linear algebra, formal logic, and probability.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Essence of Linear Algebra](https://www.3blue1brown.com/topics/linear-algebra) | - | - | High school math
[Linear Algebra](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/) | 14 weeks | 12 hours/week | Essence of Linear Algebra
[Introduction to Formal Logic](https://forallx.openlogicproject.org/) | 10 weeks | 4-8 hours/week | Set Theory
[Probability](https://projects.iq.harvard.edu/stat110/home) | 15 weeks | 5-10 hours/week | Calculus

---

## Final project

This project will validate and consolidate your knowledge by building a full-stack web application.

Courses | Duration | Effort | Prerequisites
:-- | :--: | :--: | :--:
[Fullstack Open](https://fullstackopen.com/en/) | 12 weeks | 15 hours/week | Strong programming skills

---

## How to use

1.  **Fork the OSSU repo**: Use it to track your progress by adding a ✅ next to completed items.
2.  **Follow the sequence**: The curriculum is structured logically. It's best to follow the order, especially for the "Core" sections. You can, however, take math courses in parallel with other subjects.
3.  **Be practical**: As you complete sections, apply your knowledge. For instance, after `Core security`, practice on platforms like HackTheBox, TryHackMe, or OWASP Juice Shop to build hands-on pentesting skills.
4.  **Add Cloud**: After `Core systems`, consider adding a foundational cloud course like **AWS Cloud Practitioner Essentials** or **Azure Fundamentals (AZ-900)** to meet your cloud goal.
5.  **Join the community**: Engage with other learners on the [OSSU Discord](https://discord.gg/ossu) for support and discussion.

## Team

- **[Your Name / GitHub]**: *add your GitHub profile link here*
