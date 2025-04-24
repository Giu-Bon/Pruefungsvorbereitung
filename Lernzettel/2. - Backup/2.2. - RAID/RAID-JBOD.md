# Lernzettel: RAID & JBOD

---

## Was ist RAID?

**RAID** = *Redundant Array of Independent Disks*  
Verbund aus mindestens zwei Speichermedien (HDDs/SSDs), die ein gemeinsames logisches Laufwerk bilden.

### Hauptziele:

- **Redundanz:** Schutz vor Datenverlust durch Plattenausfall
- **Performance:** Erhöhter Datendurchsatz durch parallele Zugriffe

### Hinweis:

RAID ist **kein Ersatz für ein Backup**!

---



 ---

## RAID-Arten: Hardware vs. Software

| Merkmal      | Hardware-RAID                 | Software-RAID                          |
| ------------ | ----------------------------- | -------------------------------------- |
| Verwaltung   | Dedizierter RAID-Controller   | Betriebssystem                         |
| Performance  | Sehr hoch (eigener Cache/CPU) | Abhängig von Systemlast                |
| CPU-Last     | Entlastet Hauptprozessor      | Höhere CPU-Belastung                   |
| Kosten       | Höher (Hardware erforderlich) | Günstiger (nur Software)               |
| Einrichtung  | Komplex (Firmware/BIOS)       | Einfach (z. B. mdadm, Storage Manager) |
| Flexibilität | Eingeschränkt durch Hardware  | Höher durch OS-Unterstützung           |

---

## Was ist JBOD?

**JBOD** = *Just A Bunch of Disks*  
Einfacher Verbund einzelner Festplatten **ohne Redundanz** oder Leistungssteigerung.



### Hauptmerkmale:

- Kein Striping, kein Mirroring
- Platten erscheinen dem OS einzeln
- Flexible Nutzung unterschiedlicher Festplatten
- Speicherplatz lässt sich einfach erweitern

---

## RAID-Level

### RAID 0

![raid 0](https://www.booleanworld.com/wp-content/uploads/2018/03/raid-0.png?ezimgfmt=rs:322x399/rscb20/ng:webp/ngcb20)

_Quelle: [RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)_

- Kein echtes RAID (keine Redundanz)
- **Striping** (Datenblockverteilung auf mehrere Platten)
- Höherer Durchsatz, aber bei Ausfall Datenverlust
- Anwendungsbereich: Leselastige Szenarien
  
  

### RAID 1

![raid 1](https://www.booleanworld.com/wp-content/uploads/2018/03/raid-1.png?ezimgfmt=rs:322x399/rscb20/ng:webp/ngcb20)

*Quelle: [RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)*

- **Mirroring** (Spiegelung)
- Volle Redundanz, einfache Wiederherstellung
- Kapazität nur so groß wie kleinste Platte
- Anwendungsbereich: Einfache, ausfallsichere Systeme

### RAID 5

![raid 5](https://www.booleanworld.com/wp-content/uploads/2018/03/raid-5.png?ezimgfmt=rs:682x399/rscb20/ng:webp/ngcb20)

*Quelle: [RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)*

- **Striping + verteilte Parität**
- Mindestens 3 Platten
- Gute Leseleistung, günstige Redundanz
- Einsatz: Fileserver

### RAID 6

![raid 6](https://www.booleanworld.com/wp-content/uploads/2018/03/raid-6.png?ezimgfmt=rs:720x381/rscb20/ng:webp/ngcb20)

*Quelle: [RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)*

- Wie RAID 5, aber **doppelte Parität**
- Bis zu 2 Platten dürfen ausfallen
- Höhere Sicherheit bei großen Datenmengen
  
  

### RAID 10

![raid 10](https://www.booleanworld.com/wp-content/uploads/2018/03/raid-10.png?ezimgfmt=rs:682x469/rscb20/ng:webp/ngcb20)

*Quelle: [RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)*

- Kombination aus **RAID 0 über RAID 1**
- Mind. 4 Platten
- Schneller und sicher, ideal für hohe I/O-Last





## Vergleich: RAID 0 vs. JBOD

| Merkmal             | RAID 0                                      | JBOD                                     |
| ------------------- | ------------------------------------------- | ---------------------------------------- |
| Redundanz           | Keine                                       | Keine                                    |
| Datenverteilung     | Striping (Blockweise auf alle Platten)      | Keine – Platten einzeln nutzbar          |
| Performance         | Hoch durch parallelen Zugriff               | Normalgeschwindigkeit                    |
| Speichererweiterung | Eingeschränkt                               | Einfach möglich                          |
| Datensicherheit     | Sehr gering (1 Defekt = Datenverlust)       | Gering (Einzellaufwerke können versagen) |
| Verwaltung          | Komplexer (RAID-Software/-Controller nötig) | Einfach (Platten direkt zugreifbar)      |
| Einsatzzweck        | Temporäre Daten, Medienbearbeitung          | Archivierung, einfache Backups           |

---

## Zusammengefasst

- **RAID** ist ideal, wenn **Ausfallsicherheit** oder **Performance** entscheidend sind.
- **JBOD** eignet sich für einfache Setups ohne Anforderungen an Sicherheit oder Geschwindigkeit.
- RAID ersetzt **nicht** die Notwendigkeit eines echten Backups.







# Vergleichstabelle: JBOD und RAID-Level

| Merkmal                 | JBOD               | RAID 0             | RAID 1            | RAID 2               | RAID 3             | RAID 4            | RAID 5            | RAID 6                 | RAID 10             | RAID 50                  | RAID 60               |
| ----------------------- | ------------------ | ------------------ | ----------------- | -------------------- | ------------------ | ----------------- | ----------------- | ---------------------- | ------------------- | ------------------------ | --------------------- |
| Striping                | Nein               | Ja (Block)         | Nein              | Ja (Bit)             | Ja (Byte)          | Ja (Block)        | Ja (Block)        | Ja (Block)             | Ja (Block + Mirror) | RAID 0 über RAID 5       | RAID 0 über RAID 6    |
| Parität                 | Nein               | Nein               | Nein              | Ja (Hamming)         | Ja (dediziert)     | Ja (dediziert)    | Ja (verteilt)     | Ja (doppelt verteilt)  | Nein                | Ja (verteilt)            | Ja (doppelt verteilt) |
| Redundanz               | Nein               | Nein               | Hoch              | Hoch                 | Mittel             | Mittel            | Hoch              | Sehr hoch              | Hoch                | Hoch                     | Sehr hoch             |
| Min. Anzahl Platten     | 1                  | 2                  | 2                 | ≥3                   | 3                  | 3                 | 3                 | 4                      | 4                   | 6                        | 8                     |
| Lesegeschwindigkeit     | Normal             | Sehr hoch          | Hoch              | Niedrig              | Hoch               | Hoch              | Hoch              | Hoch                   | Sehr hoch           | Sehr hoch                | Sehr hoch             |
| Schreibgeschwindigkeit  | Normal             | Hoch               | Mittel            | Niedrig              | Niedrig            | Niedrig           | Mittel            | Niedrig                | Hoch                | Hoch                     | Mittel                |
| Ausfallsicherheit       | Keine              | Keine              | Sehr hoch         | Hoch                 | Mittel             | Mittel            | Hoch              | Sehr hoch              | Hoch                | Hoch                     | Sehr hoch             |
| Datenverlust bei Defekt | Nur betroffene HDD | Kompletter Verlust | Nein (1 Laufwerk) | Nein (1–2 Laufwerke) | Nein (1 Laufwerk)  | Nein (1 Laufwerk) | Nein (1 Laufwerk) | Nein (bis 2 Laufwerke) | Nein (einzeln)      | Nein (1/Array)           | Nein (2/Array)        |
| Erweiterbarkeit         | Hoch               | Gering             | Gering            | Niedrig              | Niedrig            | Niedrig           | Mittel            | Mittel                 | Mittel              | Eingeschränkt            | Eingeschränkt         |
| Komplexität             | Sehr niedrig       | Niedrig            | Niedrig           | Hoch                 | Mittel             | Mittel            | Mittel            | Hoch                   | Hoch                | Hoch                     | Sehr hoch             |
| Typische Nutzung        | Archiv, Backup     | Temporäre Daten    | Wichtige Daten    | Forschung, obsolet   | Video-/Mediaserver | Legacy-Systeme    | Server, NAS       | Hochverfügbarkeit      | Datenbanken, VM     | Datenbanken, Filesysteme | Enterprise Backup     |
| Heute noch genutzt?     | Ja                 | Ja                 | Eingeschränkt     | Nein                 | Selten             | Selten            | Ja                | Ja                     | Ja                  | Selten                   | Selten                |





## Gekürzt:

| Merkmal                     | JBOD                         | RAID 0                   | RAID 5                              | RAID 6                              | RAID 10                              |
| --------------------------- | ---------------------------- | ------------------------ | ----------------------------------- | ----------------------------------- | ------------------------------------ |
| **Striping**                | Nein                         | Ja                       | Ja                                  | Ja                                  | Ja                                   |
| **Parität**                 | Nein                         | Nein                     | Ja (eine Paritätsplatte)            | Ja (zwei Paritätsplatten)           | Nein                                 |
| **Redundanz**               | Nein                         | Nein                     | Ja                                  | Ja                                  | Ja                                   |
| **Min. Anzahl Platten**     | 1                            | 2                        | 3                                   | 4                                   | 4 (mind. 2 Mirrors, je 2 Disks)      |
| **Lesegeschwindigkeit**     | Normal (wie Einzelplatte)    | Hoch                     | Hoch                                | Hoch                                | Sehr hoch (parallel lesbar)          |
| **Schreibgeschwindigkeit**  | Normal                       | Sehr hoch                | Mittel                              | Niedriger als RAID 5                | Hoch                                 |
| **Ausfallsicherheit**       | Keine                        | Keine                    | 1 Platte                            | 2 Platten                           | 1 pro Mirror                         |
| **Datenverlust bei Defekt** | Hoch (alle Daten weg)        | Hoch (alle Daten weg)    | Mittel (bei 1 Plattenverlust)       | Gering (2 Platten dürfen ausfallen) | Gering (abhängig von Ausfall-Mirror) |
| **Erweiterbarkeit**         | Einfach (wie Einzellaufwerk) | Schwierig                | Möglich, aber komplex               | Sehr komplex                        | Kaum möglich                         |
| **Vorteil**                 | Einfach, günstig             | Maximale Geschwindigkeit | Gute Balance zw. Performance & Red. | Sehr hohe Sicherheit                | Hohe Performance & Redundanz         |
| **Nachteil**                | Keine Redundanz              | Keine Sicherheit         | Komplex, Rebuild dauert lange       | Sehr komplex, teurer                | Hoher Speicherbedarf                 |
| **Komplexität**             | Niedrig                      | Niedrig                  | Mittel                              | Hoch                                | Hoch                                 |
| **Typische Nutzung**        | Einzelplatz-PCs              | Temporäre Daten / Gaming | Server, Datenbanken, NAS            | Backup-Systeme, kritische Server    | Datenbankserver, Virtualisierung     |
| **Heute noch genutzt?**     | Ja                           | Ja                       | Ja                                  | Ja                                  | Ja                                   |





## EXTRA:

## RAID 2 – Bit-Level Striping mit Hamming-Code

### Funktionsweise:

- Daten werden auf **Bit-Ebene** über mehrere Festplatten verteilt.

- Es kommen **Hamming-Codes** zur Fehlerkorrektur zum Einsatz.

- Benötigt mehrere Festplatten nur für Fehlerkorrektur (ECC).

### Eigenschaften:

- Sehr hohe Redundanz und theoretisch hohe Fehlererkennung.

- Erfordert eine sehr präzise Synchronisation der Laufwerke.

### Warum nicht mehr genutzt?

- Extrem aufwendig, ineffizient, teuer.

- Moderne Festplatten besitzen eingebaute ECC-Funktionen.

- RAID 5 bietet besseren Nutzen bei geringerer Komplexität.

---

## RAID 3 – Byte-Level Striping mit dedizierter Paritätsplatte

### Funktionsweise:

- Daten werden **byteweise** gestreift.

- Eine **eigene Festplatte** speichert ausschließlich Paritätsdaten.

### Eigenschaften:

- Guter Durchsatz bei großen, sequentiellen Daten (z. B. Videos).

- Kein paralleler Zugriff durch Einzelparitätsplatte – sie wird zum **Flaschenhals**.

### Warum selten?

- Dedizierte Paritätsplatte überlastet bei hoher I/O-Last.

- RAID 5 bietet **verteilte Parität** → keine Engstelle.

---

## RAID 4 – Block-Level Striping mit dedizierter Paritätsplatte

### Funktionsweise:

- Wie RAID 3, aber auf **Block-Ebene** statt Byte-Ebene.

- Ebenfalls mit **einer festen Paritätsplatte**.

### Eigenschaften:

- Ermöglicht **unabhängige Lesezugriffe**, da ganze Blöcke unabhängig gelesen werden können.

- Schreibzugriffe weiterhin begrenzt durch Paritätsplatte.

### Warum ersetzt?

- Ähnliche Limitierungen wie RAID 3.

- RAID 5 verbessert das Konzept durch **verteilte Parität** → höhere Parallelität, bessere Lastverteilung.



### RAID 50

- **RAID 0 über mehrere RAID 5**
- Mind. 6 Platten
- Hoher Durchsatz, Einsatz bei Datenbanken

### RAID 60

- **RAID 0 über mehrere RAID 6**
- Mind. 8 Platten
- Sehr hohe Ausfallsicherheit, ideal für Backups/Archive









Quelle Bilder:

[RAID levels 0, 1, 4, 5, 6, 10 explained - Boolean World](https://www.booleanworld.com/raid-levels-explained/)
