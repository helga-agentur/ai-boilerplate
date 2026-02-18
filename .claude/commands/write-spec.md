---
description: Create a Functional Specification for a Set of Features
argument-hint: <github-issue-url | requirements-as-text | miro-url>
---
# Role
- Your task is to generate a specification for a feature or a set of features for a website or web application.
- Your audience are developers, AI devs, and especially our customers (usually marketing and communication people).

# Example

The example uses project-specific chapter names; follow the structure defined below.

*Start of Example*
## Zusammenfassung
### Story
Als Player kann ich täglich ein neues Quiz erledigen, damit ich einen Grund habe, die App regelmässig zu besuchen.

### Mockups
Mockups auf [Figma](link)

### Kontext
Quiz bestehen derzeit bereits, aber mit anderem Umfang (keine Ablaufzeit, kein Gültigkeitsdatum, mehrere parallel etc.).
Die heutigen Quiz werden komplett ersetzt durch das Quiz des Tages.
Das «Quiz des Tages» wird folgend einfachheitshalber als «Quiz» bezeichnet.

### Erfassen
- [ ] Ein Superuser kann ein Quiz erfassen, bearbeiten und löschen.
- [ ] Ein Quiz ist während exakt einem Tag gültig (00:00–23:59 Uhr Serverzeit).
- [ ] Für einen Tag kann maximal ein Quiz erfasst werden.
- [ ] Ein Quiz verfügt über exakt eine Frage mit mind. zwei möglichen Antworten; exakt eine davon ist richtig.

Ein Quiz besteht aus:
- [ ] Gültigkeitsdatum* (Datum; dieses kann frühestens der nächste Tag sein)
- [ ] Frage*M (Text)
- [ ] Medium M (Bild oder Video [ohne Autoplay, mit Ton, ohne Loop, mit Controls])
- [ ] Antworten* (mind. 2 Antworten, s. unten)
- [ ] Antwortzeit in Sekunden* (positive Ganzzahl; Default: 60)
- [ ] Zu gewinnende Punkte* (positive Ganzzahl; Default: 50)
- [ ] Die bisherigen Felder Kurzbeschrieb und Alterslimite entfallen.

Eine Antwort besteht aus:
- [ ] Antwort*M (Text)

### Übersicht
- Das Quiz, dessen Gültigkeitsdatum der aktuelle Tag ist, gilt als aktuell.
- Ein Quiz gilt als spielbar, wenn es aktuell ist und der User den Start-Button für dieses Quiz noch nie geklickt hat.

- [ ] Auf der Home-Seite wird das aktuelle Quiz direkt nach dem Scoreboards angezeigt.
- [ ] Wenn das aktuelle Quiz nicht spielbar ist, wird dem User ein Hinweis angezeigt mit:
  - einem erläuternden Text und
  - einem Live-Countdown mit Stunden, Minuten und Sekunden bis zum Start des nächsten Quiz.
- [ ] Wenn das aktuelle Quiz spielbar ist, wird ihm dieses angezeigt mit:
  - der verbleibenden Zeit bis zum Ende des Tages in Stunden, Minuten und Sekunden, als Live-Countdown und
  - einem kurzen Beschrieb (für alle Quiz gleich, String-Translation)
  - einem Button für das Starten des Quiz.
- [ ] Mit dem Klick auf den Button wird das Quiz gestartet.
- [ ] Mit dem Starten des Quiz beginnt die Antwortzeit zu laufen.

### Quiz-Detail
- [ ] Startet ein User das Quiz, werden ihm in einem Overlay angezeigt:
  - die verbleibende Antwortzeit in Sekunden als Live-Countdown
  - die Frage
  - das Medium, falls gesetzt
  - alle Antworten in zufälliger Reihenfolge und
  - ein Button, um das Overlay zu schliessen.
- [ ] Das Overlay kann nur durch Klicken auf den Button geschlossen werden, nicht durch Klicken auf den Hintergrund oder die Esc-Taste (um ungewolltes Schliessen, welches das Quiz ohne Punkte beendet, zu verhindern).
- [ ] Wenn ein User die richtige Antwort wählt,
  - werden ihm die Punkte gutgeschrieben
  - werden im Overlay u.a. eine Erfolgsmeldung mit Animation angezeigt.
- [ ] Wenn ein User eine falsche Antwort wählt,
  - werden ihm keine Punkte gutgeschrieben
  - werden im Overlay u.a. ein Hinweis und die richtige Antwort angezeigt.
- [ ] Wenn die Antwortzeit abläuft, bevor der User eine Antwort gewählt hat,
  - werden ihm keine Punkte gutgeschrieben
  - wird ihm im Overlay eine entsprechende Meldung angezeigt
- [ ] Wenn ein User das Overlay schliesst, ohne das Quiz richtig beantwortet zu haben,
  - wird ihm eine Meldung angezeigt, dass das Quiz beim Schliessen beendet wird, er dieses nicht mehr neu starten kann und keine Punkte erhält
  - wenn der User das Schliessen abbricht, fährt das Quiz weiter;
  - beim Bestätigen der Meldung werden ihm keine Punkte gutgeschrieben.
- [ ] Wenn ein User das Browser-Fenster neu lädt oder verlässt (z.B. Zurück-Button),
  - werden ihm keine Punkte gutgeschrieben

### Punktevergabe
- [ ] Der User kann das Quiz spätestens nicht mehr beantworten, sobald die Antwortzeit abgelaufen ist oder wenn sie noch nicht gestartet hat; er kann die Antwortzeit nicht unterbrechen, pausieren oder verlängern.
- [ ] Ein User kann ein Quiz, dessen Datum in der Vergangenheit oder Zukunft liegt, nicht beantworten.
- [ ] Ein Quiz kann pro User maximal einmal beantwortet werden. Die Punkte werden pro User und Quiz maximal einmal vergeben.

### Optionen
- [ ] Nach dem Beantworten eines Quiz (richtig und falsch) wird einem User angezeigt, wie viele Prozent der User dieses bisher richtig beantwortet haben.
- [ ] Alle jeweils aktuellen Quiz des Tages können als Pattern auf Inhaltsseiten (z.B. der Front für nicht angemeldete User) eingebunden werden. Sobald ein User auf den Starten-Button klickt (und bevor ihm die Antworten angezeigt werden), wird er zur Anmeldung/Registration weitergeleitet. Er kann das Quiz danach auf der Home-Seite erneut starten.

### «Punkte sammeln»
- [ ] Die Quiz werden unter dem Menueintrag «Punkte sammeln» gleich angezeigt wie auf dem Home-Screen.

### Rückbau
- [ ] Die bisherige Funktionalität von Quiz wird komplett abgelöst durch jene von Quiz des Tages.
- [ ] Nicht mehr benötigte Funktionen, Assets etc. werden komplett zurückgebaut.
*End of Example*

# Content
- Your main focus is to create a list of clearly defined features that can be checked by developers when implemented (Definition of Done)
- Use a checkbox for every requirement that a developer has to implement.
- When something is not obvious, give a short explanation / reason why this solution was chosen (so that readers can follow your decision).

# Structure
Use the following structure / chapters in your output; if there's a good reason to deviate, you may:
1. User Story (try to create one issue per story; break things down into smaller issues / tasks when things start to grow complex)
2. Context: Provide all relevant context so that a person who does not know the project or requirements still understands the issue.
3. Input: What fields / data structures are available to editors? What role / what type of editor is allowed to create, edit and delete content?
4. Output: How are the fields displayed? How do they play together? What are the interactions between them and the user?
5. Additional Requirements: Additional functional requirements / definitions that went missing above; only in this chapter if they don't fit somewhere above.
6. Non-functional Requirements: Performance, security, scalability, usability, maintainability – only if not obvious.
7. Edge Cases: Define and propose solutions that have not been handled above. If possible, handle above.
8. Flows: Create ASCII-based flow diagrams for the most relevant cases (only if helpful).
9. Migrations: If functionality does (partially) exist, what do we remove, how do we transfer the data?
10. Options: Optional functionality that is estimated separately and that a customer can pick only when desired; only use when provided in the input.

# Tasks
0. **Basics**
   - Read ../spec-basics.md; it contains the building blocks for writing a specification in the style we require.
   - If you can't see the file, *end* here.
   - spec-basics.md defines shared conventions; treat its rules as defaults; instructions in this file take precedence where they differ.
1. **Input** 
   - Read the input provided and check all links that it contains.
2. **Requirements Analysis**
   - As a requirements engineer, analyze the input and identify the requirements.
   - Extract the user story and let me review and improve it. *Stop* while I'm doing so.
   - If there is anything not exactly clear from the input, ask for clarification: 
      - suggest better options if you see any.
      - provide possible solutions/answers and let the user chose (instead of asking open questions)
   - Make sure that you know everything needed to cover the user story completely.
   - Look for edge cases to cover and define them and their proposed solution.
   - Ask until no questions remain; *wait* with writing until everything is clear.
3. **Write Specification**
  - Write the specification.
  - Follow the structure provided above.
  - Ensure that you have exactly followed the instructions above.
  - Write everything to a file `specs/spec-<feature-name>.md`.
4. **Developer Review**
   - As a senior developer without insight knowledge, look over the spec.
   - Make sure that you could implement the pattern without having any questions.
   - Clarify questions if needed.
5. **BA Review**
   - As a skilled, neutral business analyst without insight knowledge, look over the spec.
   - Find all ambiguities, contradictions and topics that need clarification.
   - Ask for clarification if needed. Fix them. Repeat until satisfied.
6. **Customer Review**
   - As a customer working in marketing or communication, look over the spec.
   - Find everything that might be confusing, hard to understand or too technical.
   - Find simpler, still precise terms, fix it.
7. **User Review**
   - As a user actually using the app (as an ned user and as an editor), look over the spec.
   - Are all flows complete? Do you get stuck? Is something hard to understand, non-obvious?
   - How could your experience be improved?
   - If you see possible improvements, suggest them. *Wait* until answered.
8. **Manual Review**
   - Let me look over the spec.
   - Wait until all my input has been implemented and I tell you to proceed.
