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
Hardware           | Die Hardware ist nicht älter als 5 Jahre sein (Stand 2020).
Betriebssystem     | Es sollen mindestens folgende Betriebssysteme unterstützt werden: Windows 7, Windows 10, Linux Mint 19.3.
Datenbank          | Es steht keine zentrale Datenbank zur Verfügung.
Programmiersprache | Es wird keine spezielle Programmiersprache erwartet.

#### Organisatorisch

Merkmale           | Beschreibung
-------------------|-------------
Termine            | Die Termine aus dem Vision&Scope Dokument Abschnitt [Projektpriorität](Vision-Scope-Dokument.md#Projektpriorität) müssen eingehalten werden.
Sprache            | Die Sprache aller Dokumente, sowie der technischen Dokumentation ist Deutsch.
Vorgehensweise     | Alle Aufgaben werden in einem GitHub Projekt erstellt und abgearbeitet. Fehler werden über entsprechende Bug-Tickets auf GitHub gemeldet. Verbesserungsvorschläge werden über entsprechende Feature-Tickets auf GitHub gemeldet.
Abnahme von Tests  | Eine erfolgreiche Abnahme ist dann gegeben, wenn durch den SonarCube keine gravierenden Mängel mehr festgestellt werden.

## Funktionale Anforderungen

### Übersicht der Epics

Die Funktionen der Anwendung sind in verschiedene Bereiche aufgeteilt. Diese Bereiche spiegeln sich in den nachstehenden
Epics wider:

**Bereiche der Anwendung**

Nr.| Epic                 | Beschreibung
---|----------------------|-------------
 1 | E-Mail und Postfach  | Alle Funktionalitäten, die mit dem Verbinden zu Postfächern oder dem Abrufen und Anzeigen von E-Mails zu tun haben.
 2 | Archivierung als PDF | Alle Funktionalitäten, die mit der Auswahl und der Archivierung von E-Mails als PDF zu tun haben.
 3 | Konfigurationen      | Alle Funktionalitäten, die mit Konfigurationen im Allgemeinen zu tun haben, ohne direkt zu den beiden anderen Bereichen zu gehören. 

### Übersicht der User Storys

Die Anforderungen an die **Mail to PDF** Anwendung, die den fachlichen Umfang betreffen, sind nachfolgend in der 
übrlichen Form aus Sicht der nutzenden Personen formuliert, sofern nicht anders angegeben:

_"Als <Stakeholder> möchte ich <Handlung durchführen>, um <gewünschtes Ergebnis zu erzielen>."_

Zu jeder User Story werden entsprechende Akzeptanzkriterien definiert, die die Spezifikation um konkrete Beispiele
ergänzen und für die Abnahme relevant sind. Dabei werden die Akzeptanzkriterien in einer natürlichsprachigen formalen
Sprache (Gherkin) formuliert, um diese als automatisierte Tests realisieren zu können.

#### E-Mail und Postfach

 User Story ID | Priorität | User Story | Akzeptanzkriterien
---------------|-----------|------------|-------------------
 E01.01        | 1         | Als Nutzer der Anwendung möchte ich nach dem Start der Anwendung eine Anmeldemaske für ein E-Mail Postfach sehen, um mich über diese Maske an einem Postfach anzumelden. | 1. Eingabefelder für Anmeldung am E-Mail Postfach stehen zur Verfügung. <hr/> 2. Nutzer meldet sich erfolgreich an einem E-Mail Postfach an.
 E01.02        | 5         | Als Nutzer der Anwendung möchte ich bei einer misslungenen Anmeldung einen Fehlerhinweis erhalten. | Nutzer bekommt einen Hinweis angezeigt, wenn die Anmeldung fehl schlägt.
 E01.03        | 3         | Als Nutzer der Anwendung möchte ich, dass nach erfolgreicher Anmeldung alle E-Mail Köpfe automatisch angezeigt werden. | Anzeige aller E-Mail Köpfe nach erfolgreicher Anmeldung 

#### Archivierung als PDF

 User Story ID | Priorität | User Story | Akzeptanzkriterien
---------------|-----------|------------|-------------------
 E02.01        | 1         | Als Nutzer der Anwendung möchte ich mehrere E-Mails markieren können, um beim Archivieren mehrerer E-Mails Zeit eingespart wird. | 1. Nutzer markiert mehrere E-Mails. <hr/> 2. Nutzer entfernt Markierung von bereits markierten E-Mails.
 E02.02        | 1         | Als Nutzer der Anwendung möchte ich alle markierten E-Mails als PDF exportieren können. | 1. Archivierung von mehreren E-Mails ohne Anhang in Abhängigkeit des vorkonfigurierten Dateinamen Templates. <hr/> 2. Archivierung mehrerer E-Mails mit Anhang in Abhängigkeit des vorkonfigurierten Dateinamen Templates. <hr/> 3. Export zweier E-Mails deren generierter Dateiname identisch ist und eine Laufende Nummer erzeugt wird.
 E02.03        | 3         | Als Nutzer der Anwendung erwarte ich bei entsprechender Konfiguration, dass erfolgreich archivierte E-Mails aus dem Postfach gelöscht werden. | Sofern in der Konfiguration das Löschen aktiviert ist, werden archivierte E-Mails gelöscht.

#### Konfigurationen

 User Story ID | Priorität | User Story | Akzeptanzkriterien
---------------|-----------|------------|-------------------
 E03.01        | 3         | Als Nutzer der Anwendung möchte ich Templates für Dateinamen der archivierten Dateien erstellen | Erstellung und Speicherung eines neuen Templates für Dateinamen.
 E03.02        | 1         | Als Nutzer der Anwendung möchte ich vorhandene Templates für Dateinamen der archivierten Dateien einsehen können | Anzeige vorhandener Templates für Dateinamen.
 E03.03        | 4         | Als Nutzer der Anwendung möchte ich vorhandene Templates für Dateinamen der archivierten Dateien löschen können | Löschen eines vorhandenen Templates.

### Übersicht der informellen Anwendungsfälle

Die User Storys dienen dazu die Welt des Kunden besser zu verstehen. Um aber einen besseren Einblick in die konkreten 
Arbeitsschritte für eine Aufgabe oder einen Kundenwunsch zu erhalten, werden Anwendungsfälle erstellt. Die 
Anwendungsfälle bilden einen kompletten Arbeitsprozess ab und kann daher mehrere User Storys abdecken. Jeder
Anwendungsfall wird im Anschluss durch ein UML Use Case Diagramm visualisiert.

#### E-Mail und Postfach

**Name:** Anmeldung an einem vorhanden E-Mail Postfach (US: E01.01, E01.03)<br />
**Nr.** IA01.01<br />
**Grundlegender Ablauf**<br />

- Nutzer startet die Anwendung Mail to PDF.
- Anwendung zeigt eine Anmeldemaske für ein E-Mail Postfach an.
- Nutzer meldet sich am E-Mail Postfach an mit Hostname, Benutzername und Passwort
- System zeigt automatisch alle E-Mail Köpfe an.

TODO Diagramm erstellen

**Name:** Archivierung von E-Mails als PDF (US: E02.01, E02.02, E02.03)<br />
**Nr.** IA02.01<br />
**Grundlegender Ablauf**<br />

- Nutzer wählt eine oder mehrere E-Mails aus
- Nutzer stößt über einen Button die Archivierung der E-Mails an
- Anwendung nimmt aus der Menge der markierten E-Mails die erste heraus und 

