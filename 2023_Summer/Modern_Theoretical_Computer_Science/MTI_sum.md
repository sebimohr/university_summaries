# Moderne Theoretische Informatik - Zusammenfassung

## 2 - NP (in polynomieller Zeit nicht deterministisch lösbare Probleme)

### Probleme in NP

Haben schwer zu findende Lösungen, Korrektheit ist aber leicht zu überprüfen.
Folgende Probleme existieren in NP:

- k-Färbbarkeit von Graphen (k-Color)
- Hamilton'scher Pfad
- Erfüllbarkeit logischer Formeln (SAT)
- Graph Isomorphismus

### Reduzierbarkeit von NP-Probleme

Probleme sollen aufeinander reduzierbar sein, heißt: Problem A & B existieren, Lösung für Problem B existiert, Eingabe von A wird auf Eingabe von B abgebildet $ \rightarrow $ Lösung für A gefunden:
$ A \leq_p B $

#### NP-Vollständigkeit

Sprache B ist NP-vollständig, wenn gilt:

- $ B \in NP $
- $ \forall A \in NP: A \leq_p B $

Alle NP-vollständigen Probleme sind Elemente von __NPC__.

In NPC existieren:

- Graphprobleme: Längster Pfad, Graphfärbbarkeit
- Optimierungsprobleme: Bin Packing, Traveling Salesman
- Formale Sprachen: Längste gemeinsame Teilsequenz
- Spiele und Puzzles: Super Mario Bros, Minesweeper
- __SAT__ (Erfüllbarkeit logischer Ausdrücke)

*Zur Lösung wichtig:* Approximationsverfahren, da sehr wahrscheinlich keine effiziente Lösung für Probleme in NPC existiert.

__Satz von Cook und Levin:__ Für jedes Problem $ A \in NP $ gilt $ A \leq_p SAT $

__Satz von Ladner:__ $ P \neq NP \Rightarrow NP - P \neq NPC $

#### NP-Optimierungsproblem

__NPO__ Optimierungsprobleme bestehen aus 4-Tupel $ F = (I_F, S_F, m_F, opt) $

- I:    Menge von Eingabeinstanzen (z.B. Menge der Graphen)
- S:    Funktion, die Eingabeinstanzen auf Lösungswörter abbildet (z.B. Bildung der Teilgraphen aus Graph)
- m:    eine Zielfunktion, die das Maß der Lösung berechnet (z.B. Zählen der Knoten in Teilgraphen)
- opt:  Optimierungsziel (max / min) (z.B. maximal viele Cliquen in Menge aller Graphen I)

#### NP-Intermediate

Alle Probleme von NP, die weder in P, noch in NPC enthalten sind, nennt man __NPI__ oder NP-Intermediate Probleme.

## 3 - Möglichkeiten udn Grenzen randomisierter Algorithmen

### Min-Cut

__Definition__: ungerichteter, ungewichteter Graph soll in zwei Teile aufgespalten werden, so dass möglichst wenige Kanten durchtrennt werden.

__Karger'scher Algorithmus__:

- zufällige Kante mit Knoten *{u, v}* auswählen
- Knoten *{u, v}* zu neuem Knoten *<u.v>* zusammensetzen
- Kanten zwischen *u* und *v* entfernen
- wiederholen, bis 2 Teile übrig sind

Erfolgreicher Durchlauf: Minimale Verbindung zwischen 2 Knoten

Fehlerhafter Durchlauf: 2 Knoten sind mit mehr als der minimalen Kantenmenge verbunden

![Karger'scher Algorithmus](image.png)

### Elementare Wahrscheinlichkeitstheorie

__Elementar-Ergebnisse:__ Alle in einem Zufallsprozess möglicherweise vorkommenden Ergebnisse $ \Omega $

__Ereignisse:__ Menge $F$ aller erlaubten Ereignisse, jedes Ereignis $F_i$ hat eine Wahrscheinlichkeit $ P(F_i) $

### Probabilistische Methode

Probabilistische Methode liefert Existenzbeweis für Objekte mit bestimmten Eigenschaften. Wenn die Wahrscheinlichkeit für die Wahl eines Objekts aus einem Ereignisraum > 0 ist, existiert das Objekt.

Vorgehensweise:

- Ereignisraum mit geeigneten Objekten konstruieren
- Zeigen, dass gewünschtes Objekt mit Wahrscheinlichkeit > 0 auftritt

### Monte Carlo / Las Vegas Algorithmen

Monte Carlo:

- vorab bestimmte Laufzeit
- Fehlerhaftes Resultat mit $ P > 0 $, Fehler kann ein- oder zweiseitig sein

Las Vegas:

- variierende Laufzeit
- __niemals__ fehlerhaftes Resultat
