<p align="center">
<a href="Domaenenanalyse.md"><img src="images/menu_01_inactive.png"></a><a href="Vision-Scope-Dokument.md"><img src="images/menu_02_active.png"></a><a href="Anforderungen.md"><img src="images/menu_03_semi_inactive.png"></a><a href="Analyse.md"><img src="images/menu_04_inactive.png"></a><a href="Entwurf.md"><img src="images/menu_05_inactive.png"></a><a href="Realisierung.md"><img src="images/menu_06_inactive.png"></a><a href="Test.md"><img src="images/menu_07_inactive.png"></a>
</p>

# Vision & Scope Dokument

## Geschäftsanforderungen

### Hintergrund

Sowohl beruflich als auch privat sammeln sich im Laufe der Zeit so einige E-Mails an. Manche dieser E-Mails können 
gelöscht, andere müssen archiviert werden. In vielen Fällen soll eine E-Mail Korrepondenz künftig noch einmal auffindbar
sein und möglich leicht einsehbar sein. Ein gutes Format sind hier PDF Dokumente. Mit Anwendungen wie [PDFCreator](https://www.pdfforge.org/de/pdfcreator)
können zwar E-Mails in PDFs konvertiert werden, jedoch ist der manuelle Aufwand alle E-Mails der vergangenen Jahre
manuell zu archivieren sehr hoch. Dieses Problem soll der **Mail to PDF** Konverter angehen. Mit dieser Anwendug ist es 
möglich sich mit einem beliebigen Postfach zu verbinden, flexibel nur die E-Mails auszuwählen, die archiviert werden 
sollen und mit einem Knopfdruck alle ausgewählten E-Mails in PDFs zu konvertieren und an einem Zielort zu speichern.
Dabei können für die Datennamen der PDFs dynamische Vorlagemuster verwendet werden, sodass beispielsweise im Dateinamen
das Empfangs- oder Sendedatum der E-Mail enthalten ist, sodass eine chronologische Sortierung des Archiv ermöglicht 
wird. Bei Bedarf ist die Anwendung nach der erfolgreichen Archivierung ebenfalls in der Lage die gesicherten E-Mails
aus dem Postfach zu löschen.

### Geschäftsmöglichkeit

Bislang müssten entweder teure kommerzielle Produkte für die Aufgabe genutzt werden oder ein hoher manueller Aufwand
aufgebracht werden und alle E-Mails einzeln angepasst und gespeichert werden. So wird z.B. jede E-Mail mit dem
[PDFCreator](https://www.pdfforge.org/de/pdfcreator) als PDF gedruckt. Dabei wird der Dateiname nach folgendem Muster
angepasst: Empfangsdatum - Betreff[_Fortlaufende Nummer].pdf<br />
Ebenfalls müssen alle Anhänge manuell gespeichert werden. Auch hier müssen die Dateinamen an die dazugehörigen 
PDF-Dokumente angeglichen werden, damit die Zuordnung der Anhänge zu den E-Mail Texten gewährleistet ist.<br />
Zusätzlich muss der Anwender darauf achten, das er eine fortlaufende Nummerierung in den Dateinamen einfügt, sofern
mehrere E-Mails zum gleichen Empfangsdatum und mit gleichem Betreff empfangen wurden.

All dies ist eine ermüdende und sehr zeitaufwändige Tätigkeit. Je nach Anwender kann es hier zu einem E-Mail Umfang 
zwischen 10 und 50 E-Mails täglich kommen. Bei einer durchschnittlichen Bearbeitungszeit für eine Archivierung einer 
einzelnen E-Mail von 15 Sekunden kommen hier im günstigen Fall 1,25 Stunden und im schlechtesten Fall 6,25 Stunden
heraus, wobei die Ermüdungserscheinungen der Anwender durch die monotone Arbeit ebenfalls weitere Auswirkungen haben.  

### Geschäftsziele und Erfolgskriterien

Nach Fertigstellung der **Mail to PDF** Anwendung, soll ein messbarer Nutzen durch die Anwendung der neuen Software 
entstehen. Dabei soll der Nutzer im Aufwand für die Archivierung der E-Mails als PDF und die Sicherung der Anhänge
bestehen. Angestrebt ist hier eine Reduzierung der Bearbeitungszeit pro E-Mail auf maximal 3 Sekunden.  

### Erfordernisse von Kunde oder Markt

Der Nutzer soll künftig mit Hilfe von Vorlagen und Einstellungsmöglichkeiten seine gewünschten Archivierungsparameter 
einstellen können und dann auf alle E-Mails anwenden können. Dabei soll er auch auf unterschiedliche Postfächer
zugreifen können und verschiedene Einstellungen nutzen können. 

### Geschäftsrisiken

Durch eine unsachgemäße Benutzer ist es denkbar, dass E-Mails gelöscht werden ohne dabei sicher archiviert worden zu 
sein. So wäre es denkbar, dass auf einem Linux basierten System der Nutzer /dev0 als Ziel auswählt. Die Software
sollte daher die gängisten Fehlbedienungen erkennen können und den Nutzer zumindest auf das Risiko hinweisen.

## Vision der Lösung

### Vision

Für den Nutzer, der auf einfache und schnelle Art seine E-Mails als PDF archivieren möchte, ist **Mail to PDF** ideal.
Die Anwendung ermöglich auf einfache und schnelle Art E-Mails aus beliebigen Postfächern als PDF zu exportieren und
gehört damit zu den Verwaltungsanwendungen, sowohl im privaten als auch im geschäftlichen Bereich. Bisherige manuelle
und zeitaufwändige Arbeitsschritte entfallen mit **Mail to PDF**. Mit dieser Anwendung können beliebige Postfächer
jederzeit aufgeräumt werden und bleiben damit übersichtlich.

### Wichtigste Features

(FU1) Verbindung mit E-Mail Postfach herstellen
(FU2) E-Mail Header abfragen und anzeigen
(FU3) Auswahlmöglichkeit von mehreren E-Mails
(FU4) Möglichkeit einer Archivierung als PDF von markierten E-Mails
(FU5) Möglichkeit einer Archivierung von Anhängen von markierten E-Mails
(FU6) Erstellung von Templates für Dateinamen für exportierte PDFs und Anhänge
(FU7) Löschen von E-Mails, die erfolgreich archiviert wurden

### Annahmen und Abhängigkeiten

(AN1) Mit **Mail to PDF** wird die Archivierung von E-Mails bedeutend schneller.
(AN2) Künftig wird die Archivierung einfacher und fehlerfreier
(AN3) Die Anwendung wird nur auf einem PC eingesetzt werden

## Fokus und Grenzen

### Umfang des ersten Release

Im ersten Release wird ein Prototyp für den Zugriff auf die E-Mails und den Export als PDF erstellt. Dabei wird noch 
keine Benutzeroberfläche erstellt, sondern eine kleine Consolen Anwendung implementiert, um die grundsätzliche
Funktionalität in einem kleinen Szenario zu erproben. Es werden auch keine Templates und keine Löschung der E-Mails
implementiert.<br />
Im ersten Release sind folgende Features enthalten:

* (FU1) Eingabe der Zugansgdaten über Commandozeile
* (FU2) Es werden fix die ersten 5 E-Mail Header abgerufen
* (FU4) Es werden fix die ersten 5 E-Mails als PDF archiviert
* (FU5) Sofern unter den ersten 5 E-Mails ein Anhang dabei ist wird dieser gespeichert
* (FU6) Es wird ein Default Template hinterlegt, welches genutzt wird

### Umfang der folgenden Releases

Feature | Release 2 | Release 3 | Release 4 
--------|-----------|-----------|----------
FU1     | X         |           |           
FU2     | X         |           |           
FU3     | X         |           |           
FU4     |           | X         |           
FU5     |           | X         |           
FU6     |           |           | X         
FU7     |           |           | X         

### Begrenzungen und Ausschlüsse

Die Anwendung wird als Archivierungswerkzeug eingesetzt. Auch wenn der Zugriff auf verschiedene Postfächer möglich ist,
soll es in keinster Weise als E-Mail Client fungieren. Ebenso wenig können mehrere Postfächer gleichzeitig verwaltet
werden, da diese nicht gespeichert und auch nicht parallel verbunden werden können.

## Geschäftskontext

### Stakeholder

Stakeholder | Nutzen                                         | Einstellung                | Hauptinteresse | Randbedingungen
------------|------------------------------------------------|----------------------------|----------------|----------------
Endnutzer   | Unterstützung bei der Archivierung von E-Mails | Hoher Automatisierungsgrad | Zeitersparnis  | Einfache Bedienung

### Projektpriorität

**Feature**

fix: Alle notwendigen Features müssen zum jeweiligen Release fertig sein, da das System sonst nicht einsetzbar ist
und der Zeitplan für die Gesamteinführung nicht eingehalten werden kann.

**Qualität**

fix: Die Kernfunktionalitäten (E-Mails anrufen, PDF exportieren) muss funktionieren. Fehler in der Darstellung auf der
Benutzeroberfläche können vertretbar sein und zu einem späteten Zeitpunkt behoben werden. Gleiches gilt für Fehler, die
keinen Einfluss auf die Kernfunktionalität haben.

**Termin**

fix: Aufgrund Äußerer Rahmenbedingungen sind folgende Fertigstellungszeitpunkte zwingend einzuhalten.

* Release 1: Fertigstellung bis spätestens 12.07.2020
* Release 2: Fertigstellung bis spätestens 17.07.2020
* Release 3: Fertigstellung bis spätestens 22.07.2020
* Release 4: Fertigstellung bis spätestens 27.07.2020

**Kosten**

anpassbar: Buget ergibt sich durch die Einsparung über die nächsten 500 Tage bei einer Person mit täglich 50 E-Mails,
3 Sekunden statt 15 Sekunden Bearbeitungszeit für eine E-Mail und einer Projektlaufzeit von 26 Tagen á 4 Stunden pro
Tag.

**Team**

Keine Prioritäten

### Technische Anwendungsumgebung

**Mail to PDF** wird plattformunabhängig sein und somit auf Windows, Linux und iOS lauffähig sein. Als Basis wird hier
die Java Virtual Runtime genutzt, die für alle üblichen Betriebssysteme zur Verfügung steht. 
