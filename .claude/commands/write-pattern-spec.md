---
description: Create a Pattern Specification
argument-hint: <figma-link> <additional-hints>
---
# Role
- Your task is to generate a specification for a pattern (Drupal Paragraph, website module, block …) that is understood by developers, AI devs and especially our customer (usually marketing and communication people).

# Examples

This is an example for a slider that has different categories as tabs, and every category contains a slider. First, we focus on the data structure / fields, then the functions that are non-obvious.

*Start of Example*
## Fachbereich-Slider [Special Field Slider]
### Felder
- Übertitel [Surtitle]*MS (Text, im Mockup «Analytik»)
- Kategorien [Categories]* (mind. eine Kategorie, s. unten, Reihenfolge frei wähl- und nachträglich anpassbar)
- Vertikale Ausrichtung des Texts [Vertical Text Alignment]* (Auswahl «oben» [top] oder «zentriert» [middle])

### Kategorien
- Jede Kategorie besteht aus:
- Übertitel [Surtitle]*MS (Text, im Mockup «Slider toggle link»)
- Angebote [Offerings]* (mind. ein Angebot, s. unten, Reihenfolge frei wähl- und nachträglich anpassbar)

### Angebote
Jedes Angebot besteht aus:
- Angebotstitel [Offering Title]*MS (Text, im Mockup «Lorem ipsum»)
- LeadMS (Text, im Mockup «Lorem ipsum»)
- TextMS (Editor «Minimal mit Listen», im Mockup «Nunc magna»)
- Medium* (Bild oder Video automatisch abgespielt)
- Lightbox für Medium ermöglichen [Offer Lightbox Option for Medium] (Checkbox)
- Analysen [Analyses] (beliebig viele Verknüpfungen mit Seiten des Typs Analyse; die Reihenfolge kann frei gewählt und nachträglich angepasst werden; die Suche erfolgt anhand des Analysecodes)
- Downloads (beliebig viele Verknüpfungen mit Dateien; Typen s. Textblock; die Reihenfolge kann frei gewählt und nachträglich angepasst werden)
- Link (im Mockup «Zu allen Analysen», falls gesetzt bestehend aus:
- URL*M (URL)
- Text*MS (Text)
- Öffnen in neuem Tab [Open in new tab] (Checkbox)

### Migration
- Sobald das Feld «Vertikale Ausrichtung des Texts» eingeführt wird, wird der Wert für alle bestehenden Patterns auf «oben» gesetzt.

### Ausgabe
- Bestehen mehrere Kategorien, kann ein User diese wechseln; die aktuell gewählte wird hervorgehoben. 
- Beim Wechsel der Kategorien werden die alte Kategorie animiert ausgeblendet und die Inhalte der neuen Kategorie animiert angezeigt (nacheinander sanft eingeblendet und von oben nach unten geschoben).
- Besteht nur eine Kategorie, wird deren Titel angezeigt, er ist jedoch nicht klickbar. 
- Besteht mehr als ein Angebot, kann ein User durch dieses sliden (Funktionsweise analog Bild-Slider; Ausrichtung eines Angebots immer links am Content; zudem wird ein Fortschrittsbalken angezeigt).
- Wenn ein User beim letzten Angebot einer Kategorie nach rechts slidet, wechselt das Pattern zur nächsten Kategorie; Gleiches gilt analog für das Sliden beim ersten Angebot nach links. Beim letzten Angebot der letzten Kategorie und beim ersten Angebot der ersten Kategorie werden die Slide-Buttons nach rechts resp. links ausgeblendet.
- Besteht nur ein Angebot, wird dieses ohne Interaktionsmöglichkeiten (kein Slider, kein Fortschrittsbalken) angezeigt.
- Alle nicht aktiven Angebote werden im Slider mit halbtransparent angezeigt. 
- Die vertikale Ausrichtung des Texts richtet sich nach dem entsprechenden Feld.
- Wenn «Lightbox für Medium ermöglichen» gewählt ist, kann der User das Medium des Angebots in einer Lightbox anzeigen für Bildschirme ab Grösse L; für kleinere Bildschirme steht die Lightbox nicht zur Verfügung.

### Backoffice
- Hinweis für Editoren: «Erfasse nicht zu viele Analysen: Die Spalte mit dem Text sollte nicht höher werden als jene mit dem Bild. Mehr als 9 sind generell zu viel.»
*End of Example*

*Start of Example*
## Grosser, breiter Text [Big Wide Text]

### Felder
- Text*MS (Text)

### Backoffice
- Hinweis beim Erfassen: «Empfohlene Länge des Texts: 200–250 Zeichen (inkl. Leerzeichen).»
*End of Example*

# Structure
Usually, a pattern specification has the following structure:
- Name is an H1, sub-chapters are H2. No deeper nesting.
- Main fields that are available to editors ("Felder")
- Sub-entries / relations with their fields, every one has its own chapter with the relation's name, then "Jede <relation> besteht aus:"
- Description of the output (how are things displayed, if not obvious; what are the interactions; call that chapter "Ausgabe")
- Notes for editors ("Backoffice", then "Hinweise beim Erfassen:")
- You may introduce additional chapters as needed.
- For relations, define if they may be ordered and if the order can be adjusted.
- Reference the content of the mockup to clearly define the fields (add it as the type's description): e.g. "(text; in the mockup «Lorem ipsum»)".

# Tasks
0. **Basics**
   - Read ../spec-basics.md; it contains the building blocks for writing a specification in the style we require.
   - If you can't see the file, look for it.
   - If you don't find it, *end* here.
   - spec-basics.md defines shared conventions; treat its rules as defaults; instructions in this file take precedence where they differ.
1. **Input** 
   - Fetch the Figma link through the Figma MCP; if you don't have access, let the user know how to install/configure MCP.
2. **Requirements Analysis**
   - Look at the layout.
   - Deduct how the pattern is supposed to work, what fields are available and what editors must know in order to use them coherently.
   - Look at the other patterns in the file in order to keep things consistent.
3. **Write Specification**
   - Find the perfect name; then define the whole structure.
   - If there is anything not exactly clear from the mockup, ask for clarification; provide possible answers and their probabilities.
   - Write everything to a file `specs/pattern-<pattern-name>-spec.md`
4. **Edge Cases**
   - Look for edge cases to cover and define them. Use the most fitting chapter for them; if there's a lot, create a separate chapter.
5. **Developer Review**
   - As a senior developer without insight knowledge, look over the spec.
   - Make sure that you could implement the pattern without having any questions.
   - Clarify questions if needed.
6. **BA Review**
   - As a skilled, neutral business analyst without insight knowledge, look over the spec.
   - Find all ambiguities, contradictions and topics that need clarification.
   - Ask for clarification if needed. Fix them. Repeat until satisfied.
7. **Customer Review**
   - As a customer working in marketing or communication, look over the spec.
   - Find everything that might be confusing, hard to understand or too technical.
   - Find simpler, still precise terms, fix it.
8. **Manual Review**
   - Let me look over the spec.
   - Wait until all my input has been implemented and I tell you to proceed.
