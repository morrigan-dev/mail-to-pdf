# Übersicht aller UML 2 Diagramme

## Einsetzbarkeit in Phasen

Im folgenden werden die verschiedenen UML Diagramme den Phasen des Wasserfall Modells zugeordnet.

Diagramm               | Anforderungen | Analyse | Entwurf | Realisierung | Test
-----------------------|:-------------:|:-------:|:-------:|:------------:|:---:
Anwendungsfalldiagramm | X             | X       |         |              |
Klassendiagramm        |               | X       | X       | X            |
Zustandsdiagramm       |               | X       | X       | X            |
Sequenzdiagramm        |               | X       | X       | X            | X
Aktivitätsdiagramm     |               | X       | X       | x            | X

## Einsetzbarkeit Thematisch

Diagramm               | Einsatzgebiet
-----------------------|--------------
Anwendungsfalldiagramm |
Klassendiagramm        |
Zustandsdiagramm       |
Sequenzdiagramm        |
Aktivitätsdiagramm     | <ul><li>Schwerpunkt auf prozedurale Verarbeitungsaspekte, also Reihenfolge von Aktivitäten.</li><li>Spezifikation von Kontroll- und/oder Datenflüssen</li><li>Analyse Phase:<br/>→ Standardablauf in einem Anwendungsfall<br />→ Geschäftsprozess</li><li>Designphase:<br />→ Darstellung von Systemverhalten</li><li>Realisierungsphase:<br />→ Ablauf innerhalb einer Methode (Nur die wichtigsten Aspekte!)<br />→ Visualisierung komplexer Algorithmen</li><li>Testphase:<br />→ Ableitung von Testfällen</li></ul>

## Anwendungsfalldiagramm

### Verfügbare Elemente

Element                 | Symbol                                                       | Beschreibung
------------------------|:------------------------------------------------------------:|-------------
**Akteur**              | ![Akteur](images/uml/anwendungsfalldiagramm-akteur.png) ![Akteur](images/uml/anwendungsfalldiagramm-akteur2.png) | _Wer benutzt das System?_<br />Ein Aktuer kann sein <br /><ul><li>ein Benutzer</li><li>eine Softwate (z.B. Webservice, Andere Programme)</li><li>eine Hardwarekomponente</li></ul>. Dabei wird immer nur eine Rolle von Benutzern dargestellt. Niemals eine einzelne Person selbst. Beide Symbole sind gleichwertig und können für menschliche und nicht-menschliche Akteure genutzt werden. Es wird bei Aktueren zwischen primären und passiven Akteuren unterschieden.
**Anwendungsfall**      | ![Akteur](images/uml/anwendungsfalldiagramm-anwendungsfall.png) | _Was machen die Akteure?_<br />Folge von Schitten, um ein fachliches Ziel zu erreichen, ohne technische Details. Dabei ist es wichtig, dass der beschriebene Anwendungsfall auch einen Nutzen erzeugt.
**Assoziation**         | ![Akteur](images/uml/anwendungsfalldiagramm-assoziation.png)    | _Wer steht mit wem in Beziehung?_<br />Beziehungen geben an, welche Akteure zu welchen Anwendungfällen gehören und diese auslösen. Dabei können diese Beziehungen Multiplizitäten besitzen. Sind keine angegeben, wird implizit * angenommen, also beliebig viele. In dem Beispiel hier fliegen genau zwei Piloten ein Flugzeug. Der Flug ansich kann jedoch beliebig häufig durchgeführt werden. In der Regel wird auf Seite des Anwendungsfalls nie eine Multiplizität angegeben.
**«include» Beziehung** | ![System](images/uml/anwendungsfalldiagramm-include.png)        | **A → »base use case«**<br />Ein Basis-Anwendungsfall benötigt "B", um die Funktionalität sicher zu stellen.<br />**B → »included use case«**<br />Ein inkludierter Anwendungsfall kann auch separat ausgeführt werden.
**«extend» Beziehung**  | ![System](images/uml/anwendungsfalldiagramm-extend.png)         | **A → »base use case«**<br />Das Verhalten von "B" kann in "A" eingefügt werden. "A" kann aber auch nur alleine ausgeführt werden. Die Nutzung von "B" ist also optional. In den Anwendungsfällen können Erweiterungsstellen (extension points) definiert werden. Die Ausführung des extending use cases wird dann an eine Bedingung geknüpft, die in Form einer Notiz an die Beziehungslinie annotiert wird. In der Praxis wird dies aber nur sehr selten gemacht. <br />**B → »extending use case«**<br />Kann ebenfalls für sich alleine ausgeführt werden.
**Generalisierung bei Anwendungsfällen** | ![System](images/uml/anwendungsfalldiagramm-af-generalisierung.png) | Anwendungsfälle können von anderen Anwendungsfälle erben. Dabei werden auch alle Beziehungen geerbt. Der übergeordnete Anwendungsfall kann dabei als abstrakt ({abstract}) definiert werden.
**Generalisierung bei Akteuren** | ![System](images/uml/anwendungsfalldiagramm-akteur-generalisierung.png) | Aktuere können ebenfalls von anderen Aktueren erben. In diesem Fall nutzen die Spezialisierungen alle Anwendungsfälle, die auch durch die Generalisierung genutzt werden. In dem Beispiel kann X nur von A genutzt werden. Während Y sowohl von B als auch von A genutzt werden kann. XOR Beziehungen werden ebenfalls mit Generalisierung realisiert, indem die beiden "Oder" Aktuere von einem weiteren Akteur erbt, der dann abstrakt sein kan und einen Anwendungsfall nutzt.  
**System**              | ![System](images/uml/anwendungsfalldiagramm-system.png)         | _Was wird beschrieben?_<br />Gibt das System an mit dem ein Akteur interagiert und in dem die Anwendungsfälle ablaufen.
**Notiz**               | ![System](images/uml/anwendungsfalldiagramm-notiz.png)          | Notizen sind möglich sollten aber auf keinen Fall den Anwendungsfall beschreiben, da die Beschreibung von Anwendungsfällen viel zu lange ist für eine Notiz.

### Übungen

**Aufgabe 1: "Rechner herunterfahren"**

Sie fahren Ihren Rechner herunter, indem Sie "Start -> "Herunterfahren" wählen.<br />
Das System beendet dann alle Programme und fährt herunter.<br />
Manchmal kommt es vor, dass ein Programm abstürzt und das System nicht heruntergefahren werden kann. Dann erhält der 
User den "Sofort beenden" Dialog.

_Lösung_

![Rechner herunterfahren Use Case Diagramm](images/uml/rechner-herunterfahren.png)

**Aufgabe 2: Geldautomat**

Ein Kunde kann am Geldautomat seinen Kontostand abfragen oder Geld abheben (ab 50 Euro in 50-Euro-Schritten).<br />
Der Kunde braucht eine Bankkarte und eine PIN (personal identification number), um das System nutzen zu können.<br />
Das System verbindet sich mit einem zentralen Bankserver um Details zu Kunde und Konto zu erfahren (Kontostand, korrekte Geheimzahl etc.).<br />
Der Geldautomat stellt keine Quittungen aus.<br />
Der Geldautomat wird von professionellem Servicepersonal gewartet.

_Lösung_

![Geldautomat Use Case Diagramm](images/uml/geldautomat.png)


## Klassendiagramm

### Verfügbare Elemente

Element                 | Symbol                                                       | Beschreibung
------------------------|:------------------------------------------------------------:|-------------


## Zustandsdiagramm

### Verfügbare Elemente

Element             | Symbol                                                        | Beschreibung
--------------------|:-------------------------------------------------------------:|-------------
Startzustand        | ![Startzustand](images/uml/zustandsdiagramm-startzustand.png) | Jedes Zustandsdiagramm besitzt genau ein Startzustand, der als Einstieg dient und direkt in einen Folgezustand führt. Er ist somit ein Pseudozustand in dem nicht verweilt werden kann.
Zustand             | ![Zustand](images/uml/zustandsdiagramm-zustand.png)           | Ein Zustand bildet eine Situation ab, in der spezielle Bedingungen gelten. Ein Zustand kann Aktivitäten besitzen, wie <ul><li><b>Eintrittsaktivität</b> (entry)</li><li><b>Austrittsaktivität</b> (exit)</li><li><b>Andauernde Aktivität</b> (do)</li><li><b>Weitere Aktivitäten</b> (eventname)</li></ul>
Zustandsübergänge   | ![Transition](images/uml/zustandsdiagramm-transition.png)     | Zuständsübergänge (Transitions) gibt an von welchem Zustand mit welchem Ereignis (Event) man in einen anderen Zustandgelangt. Die Übergänge können Bedingungen (Guards) besitzen, sodass nur dann der Übergange erfolgt, wenn die Bedingung zu true ausgewertet wird. Außerdem können bei Übergängen noch Aktionen (Effekte) ausgeführt werden. Es gibt verschiedene Ereignistypen bei Zustandsübergängen. <ul><li><b>CallEvent</b> → Empfang einer Nachricht (Operationsaufruf)</li><li><b>SignalEvent</b> → Empfang eines Signals (mouseover)</li><li><b>ChangeEvent</b> → Eine Bedingung wird wahr (when(x<y))</li><li><b>TimeEvent</b> → Zeitablauf oder Zeitpunkt (after(5 sec))</li></ul>
Entscheidungsknoten | ![Entscheidungsknoten](images/uml/zustandsdiagramm-entscheidungsknoten.png) | Entscheidungsknoten können dafür genutzt werden mehrere Verzweigungen mittels einer Bedingung zu ermöglichen. Es gibt jedoch ein Problem, wenn die Bedingungen nicht alle Möglichkeiten abdecken. In so einem Fall würde man in dem Entscheidungsknoten hängen bleiben. Daher sollte immer die äquivalente Schreibweise in wie  folgendem Beispiel gezeigt genutzt werden!<br /> ![Entscheidungsknoten Alternative](images/uml/zustandsdiagramm-Entscheidungsknoten-alternative.png) 
Endzustand          | ![Endzustand](images/uml/zustandsdiagramm-endzustand.png)     | Ein Endzustand kann angegeben werden um das Ende eines Lebenszyklus anzugeben (=Destruktor). Er ist ein Zustand in dem verweilt werden kann.
Terminierungsknoten | ![Terminierungsknoten](images/uml/zustandsdiagramm-terminierungsknoten.png) | Das modellierte Objekt hört auf zu existieren.
Flacher/tiefer History-Zustand | ![History-zustand](images/uml/zustandsdiagramm-history-zustand.png) | Die History-Zustände geben eine Art Rücksprungadresse an. Es wird sich also der interne Zustand gemerkt und beim nächsten Betreten des Zustands werden die internen Gegebenheiten wiederhergestellt. Dabei wird zwischen flacher und tiefer History unterschieden. Bei der flachen wird nur die erste Ebene gemerkt. Mit einer Zahl oder einem Stern können weitere bis alle internen Ebenen gemerkt werden.
Parallelisierungsknoten | ![Parallelisierungsknoten](images/uml/zustandsdiagramm-parallelisierungsknoten.png) | Aufspaltung des Knotrollflusses in mehrere parallele Zustände.
Synchronisierungsknoten | ![Synchronisierungsknoten](images/uml/zustandsdiagramm-synchronisierungsknoten.png) | Zusammenführung des Kontrollflusses von mehreren parallelen Zuständen.

### Ausführungsreihenfolge von Aktivitäten

![Ausführungsreihenvolge von Aktivitäten](images/uml/zustandsdiagramm-aktivitaeten-ausfuehrungsreihenfolge.png)

Event   | Zustand | Variable | Anmerkung
--------|---------|----------|----------
"Start" | A       | x=2      |
e       | A       | x=2      | Es wird immer erst die Bedingung geprüft von einer Überwachungsbedingung. Die exit Aktivität wird also nicht ausgeführt!
n       | A       | x=4      |
e       | B       | x=7      | Erst jetzt ist die Überwachungsbedingung true, sodass nun folgende Reihenfolge ausgeführt wird: <ol><li>Ausführung der exit Aktion (x++)</li><li>Ausführung der Übergangsaktivität (x*2)</li><li>Ausführung der Eintrittsaktivität (x=x-3)</li></ol>


## Aktivitätsdiagramm

Aktivitätsdiagramme werden für die Darstellung prozeduraler Verarbeitungsaspekte genutzt, um die Reihenfolge von Aktionen zu visualisieren.

### Verfügbare Elemente

Element                 | Symbol                                                         | Beschreibung
------------------------|:--------------------------------------------------------------:|-------------
Aktivität               | ![Aktivität](images/uml/aktivitaetsdiagramm-aktivitaet.png)    | Eine Aktivität ist ein gerichteter Graph und enthält Knoten (Aktionen) und Kanten (Kontroll- und Datenflüsse).
Aktionsknoten           | ![Aktion](images/uml/aktivitaetsdiagramm-aktion.png)           | Elementarer Baustein für ein beliebiges Verhalten, der atomar sein muss. Die Aktion kann aber eine gewisse Dauer in Anspruch nehmen und in diesem Zeitfenster kann eine Aktion abgebrochen werden.
Objektknoten            | ![Objektknoten](images/uml/aktivitaetsdiagramm-objektknoten-pins.png) | Objektknoten beinhalten Daten und Objekte. Ein Objektknoten kann auf zwei Weisen dargestellt werden. Als eigenständiger Objektknoten mit einem Rechteck oder in Form von Pins an einer Aktion.
Initialknoten           | ![Initialknoten](images/uml/aktivitaetsdiagramm-initialknoten.png) | Mit einem Initialknoten wird der Beginn eines Aktivitätsablaufs gekennzeichnet. Es können in einer Aktivität keine oder mehrere Initialknoten existieren. Man kann im Initialknoten verbleiben, sofern es eine Überwachungsbedingung an der Kante gibt, die die Weitergabe blockiert. Von den Initialknoten werden an alle ausgehenden Kanten Tokens verteilt.
Aktivitätsendknoten     | ![Aktivitätsendknoten](images/uml/aktivitaetsdiagramm.aktivitaetsendknoten.png) | Sobald der erste Token ein Aktivitätsendknoten erreicht werden alle Abläufe einer Aktivität beendet und der Lebenszyklus eines Objekts endet. Es werden keine weiteren Aktionen ausgeführt und alle verbliebenen Tokens werden gelöscht. Datentokens an den Ausgabepins der Aktivität jedoch nicht!
Ablaufendknoten         | ![Ablaufendknoten](images/uml/aktivitaetsdiagramm-ablaufendknoten.png) | Beendet lediglich den Ablauf einer Aktivität und entfernt den Token.
Transition              | ![Transition](images/uml/aktivitaetsdiagramm-transition.png)   | Übergang einer Aktivität zu einer Anderen.
Token                   | ![Token](images/uml/aktivitaetsdiagramm-token.png)             | Ein Token dient zur Visualisierung eines Ablaufs innerhalb eines Aktivitätsdiagramms. Er wird nicht explizit eingezeichnet, sondern ist ein virtueller Marker. Es werden Kontrolltoken und Datentoken unterschieden.
Entscheidungsknoten     | ![Entscheidungsknoten](images/uml/aktivitaetsdiagramm-entscheidungsknoten.png) | Definiert alternative Verzweigungen in Ablaufen, also eine Art Weiche für den Fluss von Tokens. Die Bedingungen an einer Verzweigung müssen sich gegenseitig ausschließen!
Vereinigungsknoten      | ![Vereinigungsknoten](images/uml/aktivitaetsdiagramm-vereinigungsknoten.png) | Es muss nur eine Kante mit einem Token belegt sein, damit dieser weitergegeben wird.
Parallelisierungsknoten | ![Parallelisierungsknoten](images/uml/aktivitaetsdiagramm-parallelisierungsknoten.png) | Alle Tokens werden auf alle ausgehenden Kanten vervielfacht und an die dahinter liegenden Aktionen weitergegeben.
Synchronisationsknoten  | ![Synchronisationsknoten](images/uml/aktivitaetsdiagramm-synchronisierungsknoten.png) | Alle Tokens werden zu einem Token vereint. Es müssen alle eingehenden belegt sein, bevor es weitergeht. Das gilt für die Kontrollflusstoken. Datenflusstokens werden nicht verschmolzen!
Aktivitätsaufruf        | ![Aktivitätsaufruf](images/uml/aktivitaetsdiagramm-aktivitaetsaufruf.png) | Spezielle Aktion, die eine verschachtelte Aktivität beinhaltet und aufruft.
Partition               | ![Partition](images/uml/aktivitaetsdiagramm-partition.png)     | Mit Partitionen können Knoten und Kanten innerhalb einer Aktivität gruppiert werden.
Signal                  | ![Signal](images/uml/aktivitaetsdiagramm-signal.png)           | Wird für die Übermittlung eines Signals an einen Empfänger genutzt.
Async. Ereignis / Zeitereignis | ![Async. Ereignis / Zeitereignis](images/uml/aktivitaetsdiagramm-asychrones-ereignis-zeitereignis.png) | Wartet auf ein Ereignis bzw. einen Zeitpunkt.
Exception Handler       | ![Exception Handler](images/uml/aktivitaetsdiagramm-exception-handler.png) | Aktivität die bei Auftreten einer Ausnahme ausgeführt wird.
Unterbrechungsbereich   | ![Unterbrechungsbereich](images/uml/aktivitaetsdiagramm-unterbrechungsbereich.png) | Wird der Unterbrechungsbereich über die Unterbrechungskante verlasen, so werden alle in der Region vorhandenen Token gelöscht.


## Weitere Literatur und Quellen

* http://www.uml.ac.at/de/lernen
* https://www.bs7-augsburg.de/aicher/files_codeconcert/11Prog/ANPR_UML_Aktivitaetsdiagramm.pdf
