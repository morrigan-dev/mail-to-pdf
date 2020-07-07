<p align="center">
<a href="Domaenenanalyse.md"><img src="images/menu_01_inactive.png"></a><a href="Vision-Scope-Dokument.md"><img src="images/menu_02_inactive.png"></a><a href="Anforderungen.md"><img src="images/menu_03_active.png"></a><a href="Analyse.md"><img src="images/menu_04_semi_inactive.png"></a><a href="Entwurf.md"><img src="images/menu_05_inactive.png"></a><a href="Realisierung.md"><img src="images/menu_06_inactive.png"></a><a href="Test.md"><img src="images/menu_07_inactive.png"></a>
</p>

# Anforderungen

## Nicht-Funktionale Anforderungen

### Qualitätsanforderungen

Bei der Betrachtung der Qualitätsanforderungen werden die Merkmale wie sie im IEEE 1061-1998 Stanard aufgeführt sind
berücksichtigt. Dabei wird jedem Merkmal eine Wichtigkeit zugeordnet, sowie eine Beschreibung, wie geplant ist das
Merkmal zu erfüllen.

Der Bereich der Wichtigkeit geht von 0 _(absolut unwichtig -> wird nicht berücksichtigt)_ 
bis 10 _(extrem wichtig -> wird zwingend berücksichtigt)_.
 

Merkmal              | Wichtigkeit | Beschreibung
---------------------|-------------|-------------
Portabilität         | 2           | Primär soll als Betriebssystem Windows 7 und 10, sowie Ubuntu 18.04 (Linux) unterstützt werden. 
Performance          | 3           | Die E-Mails sollen in einer überschaubaren Zeit als PDFs archiviert werden. Dabei ist ein maximaler Wert von 10 Sekunden pro E-Mail nach dem Anstoßen der Archivierung einzuhalten.
Wiederverwendbarkeit | 0           | Es wird keinen Wert auf Wiederverwendbarkeit gelegt. 
Zuverlässigkeit      | 8           | Es wird eine hohe Zuverlässigkeit erwartet. Von 1.000 E-Mails, darf maximal eine E-Mail fehlerhaft gespeichert werden.
Wartbarkeit          | 9           | Die Quellcode muss verständlich und gut strukturiert erstellt werden. Jede öffentliche Java Methode ist mit JavaDoc zu dokumentieren. 
Effizienz            | 0           | Die Anwendung darf so viel Ressourcen für die Aufgabe beziehen wie es benötigt.
Integrität           | 5           | Der Zugriff auf die E-Mail Postfächer geschieht über sichere Protokolle. Darüber hinaus sind keine weiteren Maßnahmen zur Sicherheit und dem Schutz vor unbefugtem Zugriff zu treffen.
Verfügbarkeit        | 10          | Das System soll als reine Client-Anwendung realisiert werden und steht somit nach Auslieferung zu 100% der Zeit zur Verfügung.
Benutzbarkeit        | 8           | Die Anwendung soll einfach und intuitiv bedienbar sein, sodass die Benutzung innerhalb weniger Minuten von einem erfahrenen EDV Anwender erlernt werden kann.
Interoperabilität    | 3           | Die Anwendung muss in der Lage sein mit verschiedenen Postfächern über IMAP E-Mails abzurufen und integrierte Bibliotheken zur Erzeugung von PDF Dokumenten nutzen können. 
Erweiterbarkeit      | 8           | Die Anwendung soll möglichst modular aufgebaut werden, sodass eine Erweiterung um neue Features möglich ist. Metrik: Neuer einfacher Dialog -> Max. 1 PT, Neuer mittlerer Dialog -> Max. 4 PT, Neuer komplexer Dialog -> Max. 8 PT
Robustheit           | 7           | Offensichtliche Fehleingaben sollen von der Anwendung erkannt und dem Benutzer gemeldet werden. Bei unerwarteten Fehlern, sollen diese ebenfalls protokolliert und gemeldet werden. Nur in sehr seltenen Fällen darf die komplette Anwendung abstützen.
Testbarkeit          | 10          | Die Anwendung und ihre Bestandteile müssen so erstellt werden, dass diese vollständig automatisiert testbar sind. Außerdem muss SonarCube für die statische Code Analyse eingesetzt werden und eine Testabdeckung bei den Modultest von mindestens 90% vorliegen.

### Randbedingungen

#### Technisch

Merkmale           | Beschreibung
-------------------|-------------
Hardware           | Die Hardware sollte nicht älter als 5 Jahre sein (Stand 2020).
Betriebssystem     | Es sollen mindestens folgende Betriebssysteme unterstützt werden: Windows 7, Windows 10, Linux Mint 19.3.
Datenbank          | Es soll eine embedded H2 Datenbank zum Einsatz kommen, um die Templates und die Einstellungen zu speichern.
Programmiersprache | Die Anwendung wird mit Java realisiert.
Bibliotheken       | Für den Zugriff auf die E-Mail Postfächer, sowie für die Erstellung von PDFs sollen geeigente Bibliotheken genutzt werden, um den Entwicklungsaufwand zu reduzieren. Für die Benutzeroberfläche soll JavaFX genutzt werden.
Versionsverwaltung | Als Versionsverwaltung wird GitHub eingesetzt
Testwerkzeuge      | Folgende Testwerkzeuge sollen eingesetzt werden: JUnit für reine Modultests, Cucumber und Serenity für Akzeptanztests.

#### Organisatorisch

Merkmale           | Beschreibung
-------------------|-------------
Termine            | Die Termine aus dem Vision&Scope Dokument Abschnitt [Projektpriorität](Vision-Scope-Dokument.md#Projektpriorität) müssen eingehalten werden.
Sprache            | Die Sprache aller Dokumente, sowie der JavaDoc Kommentar ist Deutsch.
Vorgehensweise     | Alle Aufgaben werden in einem GitHub Projekt erstellt und abgearbeitet. Fehler werden über entsprechende Bug-Tickets auf GitHub gemeldet. Verbesserungsvorschläge werden über entsprechende Feature-Tickets auf GitHub gemeldet.
Abnahme von Tests  | Eine erfolgreiche Abnahme ist dann gegeben, wenn durch den SonarCube keine gravierenden Mängel mehr festgestellt werden.