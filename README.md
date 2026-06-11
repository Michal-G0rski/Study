> **Cel:** pivot z roli IAM/analityka do technicznej roli audytowo-inżynierskiej (audyt techniczny, AppSec, security engineering), z otwartą furtką do dev.
> **Zasada nr 1:** praktyka jest głównym curriculum, teoria dochodzi *just-in-time* — wtedy, gdy konkretny problem jej wymaga.
> **Zasada nr 2:** najpierw piszę sam (z dokumentacją, bez LLM), potem LLM jako recenzent kodu.
> **Budżet czasowy:** ~10 h/tydzień (8 h praktyka + 2–3 h teoria).

---

## 📊 Status

| Faza | Status | Postęp |
|---|---|---|
| Faza 0 — Domknięcie | 🔄 W trakcie | ░░░░░░░░░░ 0% |
| Faza 1 — Fundament narzędziowy | ⬜ Nie rozpoczęte | ░░░░░░░░░░ 0% |
| Faza 1.5 — Projekt-pomost (Django + audyt) | ⬜ Nie rozpoczęte | ░░░░░░░░░░ 0% |
| Faza 2 — Główny tor: praktyka audytowa | ⬜ Nie rozpoczęte | ░░░░░░░░░░ 0% |
| Faza 3 — Teoria w tle (równolegle) | ⬜ Nie rozpoczęte | ░░░░░░░░░░ 0% |
| Faza 4 — Certyfikat + portfolio | ⬜ Nie rozpoczęte | ░░░░░░░░░░ 0% |
| Opcja — Pivot dev (warunkowa) | ⏸️ Wstrzymane | — |

Legenda: ✅ Ukończone · 🔄 W trakcie · ⬜ Nie rozpoczęte · ⏸️ Wstrzymane celowo

---

## Faza 0 — Domknięcie bieżących rzeczy (1–2 tygodnie)

| Zadanie | Czas | Status |
|---|---|---|
| Dokończyć **bieżący moduł** Systematic Program Design (i odłożyć resztę kursu bez wyrzutów sumienia) | ~1 tydz. | 🔄 |
| Test bazowy: wziąć jeden swój stary projekt w Pythonie i **napisać go od zera samodzielnie**, bez LLM i bez zaglądania do starego kodu | ~1 tydz. | ⬜ |

> Test bazowy pokaże, ile kodu z dotychczasowych projektów jest faktycznie "moje". To punkt odniesienia do mierzenia postępu.

---

## Faza 1 — Fundament narzędziowy (3–4 tygodnie)

| Kurs / zasób | Zakres | Czas | Status |
|---|---|---|---|
| [The Missing Semester (MIT)](https://missing.csail.mit.edu/) | terminal, shell, git, debugowanie, skrypty | 2 tyg. | ⬜ |
| Python — własne mini-projekty (patrz niżej) | pisanie samodzielne, LLM tylko jako recenzent | ciągłe | ⬜ |

### Projekty Python (małe, brzydkie, w 100% zrozumiane)

| Projekt | Czego uczy | Status |
|---|---|---|
| Parser logów IAM (z realnych danych z pracy) | pliki, regex, **słowniki vs listy**, pandas | ⬜ |
| Prosty skaner portów / narzędzie sieciowe | sockets, podstawy sieci | ⬜ |
| Klient do wybranego API (requests) | HTTP, JSON, autoryzacja | ⬜ |
| Automatyzacja z pracy przeniesiona z Power Platform na Pythona | pandas, API — nauka na firmowym czasie, wpis do CV | ⬜ |
| **Mini-backend (FastAPI/Flask):** API z rejestracją, logowaniem, sesjami i jednym zasobem (np. notatki) | jak backend działa od środka: auth, sesje, walidacja, baza — perspektywa budującego, nie tylko audytującego | ⬜ |

> **Granica zakresu:** backend bez frontendu (albo minimalny HTML). Żadnego Reacta, CSS, deploymentu — to nie nauka web devu, tylko zrozumienie mechanizmów, które potem audytuję.

> **Zasada pracy:** każdy projekt piszę najpierw sam z dokumentacją. Dopiero po skończeniu pytam LLM: "co zrobiłem źle, co bym poprawił". Odwrócenie ról: z generatora na nauczyciela.

### Definition of Done — każdy projekt (higiena od dnia 1, nie osobna faza)

- [ ] **Testy w pytest:** happy path + 2–3 złośliwe edge case'y (pusty input, zły typ, za duży rozmiar). Nie celuję w pokrycie — celuję w pytanie "gdzie to się łamie?". To trening myślenia audytora, nie tylko dobra praktyka.
- [ ] **Git:** sensowne, małe commity z opisami (nie jeden commit "final version").
- [ ] **README:** co robi, jak uruchomić, czego się nauczyłem.
- [ ] **Struktura:** venv + requirements.txt, kod w funkcjach, nie jeden płaski skrypt.

> Nawyk testowania przenoszę wprost z SPD — przepis HtDF (przykłady przed implementacją) to ta sama filozofia co pytest. Bez ortodoksji: garść świadomych testów > 100% pokrycia dla metryki.

---

## Faza 1.5 — Projekt-pomost: zbuduj aplikację, którą potem zaudytujesz (3–4 tygodnie)

> Most między "piszę kod" a "audytuję kod". Buduję małą aplikację webową od środka, żeby zrozumieć, **gdzie mieszkają podatności** — bo sam podejmuję decyzje o auth, sesjach, ORM i formularzach.

| Zadanie | Zakres | Status |
|---|---|---|
| Mała aplikacja w **Django** (np. tracker z logowaniem i 2–3 rolami użytkowników) | modele, widoki, auth, ORM, formularze, CSRF — **batteries included** | ⬜ |
| Frontend: **tylko szablony Django** (bez React/CSS-polish — najniższy ROI dla celu audytowego) | minimalny interfejs, nie produkt | ⬜ |
| Świadomie wprowadzić klasyczne podatności (IDOR, brak autoryzacji na endpoincie, niezabezpieczony upload) | "jak powstaje błąd", od strony autora | ⬜ |
| Zaudytować własną aplikację: znaleźć te podatności od zewnątrz → wskazać je w źródłach → naprawić | domyka pętlę z Fazą 2 pkt 3 | ⬜ |
| Wrzucić do repo parę "dziurawa → naprawiona" (osobne commity/branche) | gotowy wpis do portfolio | ⬜ |

> **Skala:** jedna mała aplikacja, nie SaaS. Chodzi o zrozumienie warstw, nie o produkt.
> **Frontend w React** dodaję tylko, jeśli przechylam się ku opcji pivot dev — wtedy cienki frontend jako wpis do CV. Nie wcześniej.

---

## Faza 2 — Główny tor: praktyka audytowa (od ~miesiąca 2, ciągłe)

| Zasób | Rola | Tempo | Status |
|---|---|---|---|
| [PortSwigger Web Security Academy](https://portswigger.net/web-security) | główny tor — logika aplikacji webowych, de facto standard rekrutacyjny | 2–3 laby/tydz. | ⬜ |
| TryHackMe → HackTheBox | maszyny, konfiguracje, sieci — umiejętności pokazywalne na rozmowie | 1 maszyna/tydz. | ⬜ |
| [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/) / DVWA | **czytanie kodu pod kątem usterek**: znajdź podatność z zewnątrz → znajdź ją w źródłach | 1 ćwiczenie/2 tyg. | ⬜ |
| Publiczne CVE w projektach open source na GitHubie | commit naprawiający + kod sprzed naprawy = lekcja "jak wygląda błąd w naturze" | 1–2/mies. | ⬜ |
| **Audyt własnego mini-backendu** (z Fazy 1): zaatakuj technikami z PortSwiggera, znajdź swoje błędy, napraw, opisz w README; opcjonalnie branch z celowymi podatnościami "przed/po" | obie strony lustra naraz — projekt portfolio "zbudowałem → zaatakowałem → naprawiłem" | jednorazowo, po zbudowaniu | ⬜ |

> Punkt 3 i 4 to most między audytem a dev — mało kto to ćwiczy, a to dokładnie profil "audytor, który czyta i pisze kod".

---

## Faza 3 — Teoria w tle (równolegle, 2–3 h/tydzień, NIE więcej)

| Zasób | Zakres | Uwagi | Status |
|---|---|---|---|
| Jeden porządny kurs **struktur danych i algorytmów w Pythonie** | listy, słowniki, hashowanie, drzewa, grafy, złożoność — poziom praktyczny | jeden kurs, nie cała ścieżka OSSU | ⬜ |
| Kurose & Ross — *Computer Networking: A Top-Down Approach* | sieci — fundament dla audytora | wolne tempo, rozdział na 2–3 tyg. | ⬜ |
| [OSTEP](https://pages.cs.wisc.edu/~remzi/OSTEP/) — wybiórczo | procesy, pamięć, uprawnienia | tylko rozdziały, których wymaga praktyka | ⬜ |

### Rytuał "fundamenty z praktyki"

Przy każdym projekcie z Fazy 1–2 zadaję sobie pytanie i zapisuję odpowiedź w notatkach repo:

- [ ] Jaka struktura danych tu pracuje i dlaczego ta, a nie inna?
- [ ] Jaka jest złożoność tego, co napisałem? Co się stanie przy 100× większych danych?
- [ ] Co tu może pójść źle z punktu widzenia bezpieczeństwa?

> To jest nauka fundamentów w odwrotnej kolejności niż na studiach: najpierw problem, potem teoria, która go tłumaczy. Wiedza wciągnięta *just-in-time* zostaje; wykuta na zapas — wyparowuje.

---

## Faza 4 — Certyfikat + portfolio (miesiące 4–9)

| Zadanie | Uwagi | Status |
|---|---|---|
| eJPT | rozgrzewka, niski próg wejścia | ⬜ |
| PNPT **lub** OSCP | główny otwieracz drzwi na rynku EU/PL | ⬜ |
| Write-upy z maszyn na GitHubie | pisane samodzielnie — write-up to dowód zrozumienia | ⬜ |
| Własne narzędzia Python w publicznych repo | parser logów, skaner, klienty API — z README i testami | ⬜ |
| Aktualizacja CV: "automatyzacja procesów IAM w Pythonie" zamiast "PowerAutomate" | pivot wewnętrzny w obecnej firmie jako pierwsza opcja | ⬜ |

---

## ⏸️ Opcja warunkowa — Pivot dev

**Decyzja odłożona celowo.** Ścieżka wyżej buduje ~60–70% kompetencji mid-developera w obszarach tooling / automatyzacja / security engineering. Jeśli za 12–18 miesięcy rynek dev będzie lepszą opcją:

| Zadanie | Czas | Status |
|---|---|---|
| Skoncentrowana teoria algorytmiczna pod rozmowy (LeetCode easy/medium) | 2–3 mies. | ⏸️ |
| 1–2 pierwsze kursy algorytmiczne Stanforda (zamiast wszystkich czterech) | opcjonalnie | ⏸️ |

---

## ❌ Wyrzucone z planu (świadomie)

| Co | Dlaczego |
|---|---|
| Calculus 1A/1B/1C + Mathematics for CS (~45 tyg.) | przygotowanie pod dyplom CS — dyplom już mam; żaden audytor tego nie używa w pracy |
| Class-based Program Design → OOD → Software Architecture | ścieżka pod karierę SWE w dużym stylu, nie pod mój cel; architektura przyjdzie z czytania realnego kodu (Faza 2, pkt 3–4) |
| Reszta Systematic Program Design | wartościowy dydaktycznie, ale poza ścieżką krytyczną — doszlifuję po zdobyciu pracy |
| 4 kursy algorytmiczne Stanforda jako obowiązkowe | zredukowane do opcji warunkowej przy pivocie dev |
| Robienie kursów "po łebkach, żeby odznaczyć" | lepiej 30% planu porządnie niż 100% powierzchownie — odznaczone kursy nikogo nie obchodzą |

---

## 📐 Tygodniowy szablon (~10 h)

| Dzień | Aktywność | Czas |
|---|---|---|
| 2× w tygodniu | PortSwigger / THM / HTB | 2 × 2 h |
| 1× w tygodniu | Projekt Python (samodzielnie) | 2–3 h |
| 1× w tygodniu | Teoria (struktury danych / Kurose-Ross / OSTEP) | 2–3 h |
| Na bieżąco w pracy | Python zamiast Power Platform, gdzie się da | gratis |

---

*Ostatnia aktualizacja: czerwiec 2026*
