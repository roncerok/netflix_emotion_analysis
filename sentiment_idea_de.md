## So funktioniert es

**Schritt 1: Beschreibung in einzelne Wörter aufteilen**
"A lonely man fights a dark and terrifying enemy"
→ [A, lonely, man, fights, a, dark, and, terrifying, enemy]

**Schritt 2: Jedes Wort im Wörterbuch nachschlagen**
- "A" → nicht gefunden, wird übersprungen
- "lonely" → gefunden: sad=1, happy=0, angry=0
- "man" → nicht gefunden, wird übersprungen
- "fights" → gefunden: sad=0, happy=0, angry=1
- "a" → nicht gefunden, wird übersprungen
- "dark" → gefunden: sad=1, happy=0, angry=0
- "and" → nicht gefunden, wird übersprungen
- "terrifying" → gefunden: sad=1, happy=0, angry=0
- "enemy" → nicht gefunden, wird übersprungen

**Schritt 3: Alle Werte für diesen Film addieren**

| Wort       | sad | happy | angry |
|------------|-----|-------|-------|
| lonely     | 1   | 0     | 0     |
| fights     | 0   | 0     | 1     |
| dark       | 1   | 0     | 0     |
| terrifying | 1   | 0     | 0     |
| **Gesamt** | **3** | **0** | **1** |

**Schritt 4: Für jeden Film wiederholen, nach Jahr gruppieren**
- Film 1 (2020): sad=3, happy=0, angry=1
- Film 2 (2020): sad=1, happy=2, angry=0
- Film 3 (2020): sad=0, happy=1, angry=3
- **2020 gesamt: sad=4, happy=3, angry=4**

**Schritt 5: Jahre vergleichen**
| Jahr | sad | happy | angry |
|------|-----|-------|-------|
| 2019 | 312 | 287   | 201   |
| 2020 | 398 | 301   | 289   |
| 2021 | 275 | 265   | 198   |

→ Größere Zahl = mehr emotionale Wörter dieser Art in den Filmbeschreibungen des jeweiligen Jahres