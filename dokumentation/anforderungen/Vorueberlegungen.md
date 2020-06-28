# Vorüberlegungen

Im Rahmen der Softwareentwicklung, kann diese nach folgenden Kriterien<sup id="a1">[1](#f1)</sup> eingeteilt werden:

* [Nähe und Anzahl der Kunden](#Nähe-und-Anzahl-der-Kunden)
* [Art der Benutzer, Art der Benutzung](#Art-der-Benutzer-Art-der-Benutzung)
* [Größe/Komplexität der Software und des Projekts](#Größe-Komplexität-der-Software-und-des-Projekts)
* [Wie kritisch ist nichttechnisches Domänenwissen?](#Wie-kritisch-ist-nichttechnisches-Domänenwissen?)
* [Müssen Nährungslösungen verwendet werden?](#Müssen-Nährungslösungen-verwendet-werden?)
* [Wie kritisch ist Effizienz?](#Wie-kritisch-ist-Effizienz?)
* [Wie kritisch ist Verlässlichkeit?](#Wie-kritisch-ist-Verlässlichkeit?)

In Folgenden werden sich zu jedem genannten Aspekt für das anstehende Projekt Gedanken gemacht.

## Nähe und Anzahl der Kunden

Bei diesem Projekt handelt es sich primär um eine **Individualsoftware**. Auch wenn es sich um ein Open-Source-Projekt
handelt und somit nicht ausgeschlossen ist, dass sich prinzipiell ein größerer anonymer Nutzerkreis für diese Anwendung
interessiert, ist die Anwendung nicht für diesen Fall ausgelegt.

Stattdessen stehen zwei Aspekte im Vordergrund.

1. **Übungsprojekt**<br />
Es handelt sich um ein Übungsprojekt für mein Studium.
2. **Persönliche Nutzung**<br />
Es wird ein gewisser Mehrwert für die Archivierung meiner privaten und beruflichen E-Mails erzeugt, der auf meinen persönlichen Anforderungen beruht.

## Art der Benutzer, Art der Benutzung

Bei diesem Kriterium wird bewusst zwischen zwei Aspekten unterschieden:

1. **Art der Benutzer und Art der Benutzung der Anwendung**<br />
Hier geht es in erster Linie um die Anforderungen an die Anwendung, die nach Fertigstellung genutzt werden soll.
2. **Art der Benutzer und Art der Benutzung der Dokumentation und Vorgehensweise**<br />
Bei diesem Aspekt geht es um die Nutzung der Dokumentation und des Vorgehens für Lehrzwecke.

### Art der Benutzer und Art der Benutzung der Anwendung

Die Anwendung soll für den privaten Einsatz ausgelegt sein. Mit ihr sollen E-Mails aus einem Postfach als PDF einfach
exportiert werden können. Es sind keine komplexen Funktionen angedacht. Die Benutzeroberfläche soll daher übersichtlich
und einfach gestaltet sein, sodass auch unerfahrene Benutzer gute damit arbeiten können. Es wird davon ausgegangen, dass
die Anwendung im Schnitt einmal im Monat genutzt wird.

### Art der Benutzer und Art der Benutzung der Dokumentation und Vorgehensweise

Es kann nicht ausgeschlossen werden, dass dieses Projekt als Beispiel für anderer Lehrveranstaltungen genutzt wird. 
Daher wird bei der Dokumentation großen Wert auf Nachvollziehbarkeit, Korrektheit und Verständlichkeit gelegt.
Dies sind Anforderungen an die Art der Dokumentation, jedoch nicht an das Software Produkt selbt.

## Größe/Komplexität der Software und des Projekts

Es handelt sich um eine Software mit einer sehr geringen Komplexität und das beteiligte Entwicklerteam besteht ebenfalls
nur aus einer Person. Daher wäre für diese Art von Projekt nicht zwingend alle Methoden des Software Engineers nötig.
Da aber auch die grundsätzliche Herangehensweise mit diesem Projekt geübt und auch vermittelt werden soll, wird hier
auf keinen Aspekt verzichtet.

## Wie kritisch ist nichttechnisches Domänenwissen?

Die Domäne ist nicht sehr umfangreich und die größten Herausforderungen werden voraussichtlich Technischer Natur sein.
Das nichttechnische Domänenwissen ist somit nicht kritisch.

## Müssen Nährungslösungen verwendet werden?

Bei dieser Software werden keine mathematischen Berechnungen durchgeführt. Daher werden auch keine Nährungslösungen 
benötigt.

## Wie kritisch ist Effizienz?

Da es sich im Grunde bei der geplanten Anwendung um ein Backup-System handelt, welches im Hintergrund laufen kann, ohne
den Anwender zu stören, ist Effizienz hier kein wichtiger Aspekt. Es ist auch nicht zu erwarten, dass bei der 
angedachten Aufgabenstellung größere Probleme bzgl Effizienz auftreten.<br />
Der größte Einfluss wird voraussichtlich der Speicherbedarf auf der Festplatte haben. Hier ist ausreichend Speicher 
einzuplanen.

## Wie kritisch ist Verlässlichkeit?

### Zuverlässigkeit

Die Anwendung muss zuverlässig funktionieren, da im schlimmsten Fall ansonsten Daten verloren gehen könnten. Das 
korrekte Verhalten der Software muss daher durch entsprechende Tests gewährleistet werden und darf auch im Fehlerfall
nicht zu unerwartetem Verhalten führen.

### Schutz vor unberechtigtem Zugriff

Die Anwendung ist Open Source und kann daher von jedem genutzt werden. Ebenso speichert die Anwendung keinerlei Daten.
Ein Schutz vor unberechtigtem Zugriff entfällt somit.

### Verfügbarkeit

Die Anwendung wird als reine Client Anwendung realisiert. Es kann daher davon ausgegangen werden, dass die Anwendung
praktisch jederzeit eingesetzt werden kann. Mit einem Ausfall, wie bei einer Client-Server Achitektur, ist daher nicht
zu rechnen.

### Sicherheit

Es muss sichergestellt werden, dass Zugangsdaten zu E-Mail Postfächern nicht an Dritte gelangen können. Um dies zu 
erreichen werden Zugangsdaten erst gar nicht gespeichert, sondern müssen bei jedem Zugriff erneut vom Benutzer 
eingegeben werden. Dies wirkt sich natürlich auf den Komfort für die Benutzer aus, was hier bei dieser Übung jedoch
in Kauf genommen wird.

<hr />
<b id="f1">1</b>: [Lutz Prechelt, Vorlesungsmaterial Softwaretechnik, Freie Universität Berlin, 2020, Version 2](http://www.inf.fu-berlin.de/inst/ag-se/teaching/V-SWT-2020/Miniskript.pdf)
