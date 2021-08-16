# s.o.l.i.d.-Frontend

Diese Anleitung beschreibt, wie das s.o.l.i.d-Frontend lokal zum Entwickeln betrieben werden kann.

Hierfür müssen einige Programme und Tools installiert und eingerichtet werden:

1. Git: https://git-scm.com/downloads | https://gitforwindows.org/
2. Yarn (classic): https://classic.yarnpkg.com/en/docs/install
3. VSCode: https://code.visualstudio.com/Download (Vorschlag)

Außerdem ist ein [GitHub](https://github.com)-Account nötig, um Änderungen problemlos hochladen zu können. 

## Git - Versionierungstool

*Git* ist eines der bekanntesten und mit am weitesten verbreiteten Versionierungstools. Richtig eingesetzt sorgt es dafür, dass vergangene Versionen (von Dateien) immer wieder hergestellt werden können und Fortschritte in verschiedenen Entwicklungszweigen und von verschiedenen Personen getrennt bearbeitet werden können. Außerdem ist immer transparent, welche Änderung wann und von wem gemacht wurde.

Die Versionierung arbeitet wirklich auf _Verzeichnis-_ und _Dateiebene_ des Betriebssystems. D.h., wenn von einer Version zur nächsten oder in einen anderen Entwicklungszweig ("`branch`")  geschaltet wird, verändert sich wirklich die Dateistruktur. Wird in einem branch eine Datei gelöscht, taucht sie im Verzeichnis wieder auf, sobald man auf einen anderen Branch wechselt.

Änderungen an der Dateistruktur (z.B. Änderungen an Dateien) müssen aktiv in einem so genannten `commit` versioniert werden. Durch das *committen* wird eine Änderung an Git übergeben und mit einer Versionsnummer in der *git history* gespeichert. Die 

Git stellt auch die Verbindung mit der Entwicklungslpattform *GitHub* her, auf der unser Code liegt und in dem alle Versionen festgehalten werden.

Es gibt auch eine [Anleitung](solid-git-workflow.md), wie in unseren Projekten korrekt mit Git gearbeitet wird..

Git ist an sich ein Kommandozeilen-Tool, es gibt aber auch Benutzeroberflächen und in die meisten Entwicklungsumgebungen sind die üblichen Git-Funktionen gut integriert.

Git muss auf dem jeweiligen Betriebssystem installiert werden.

Für Windows-User wird *Git for Windows* empfohlen: https://gitforwindows.org/

## Yarn - Package Manager

Moderne Software basiert stark auf vielen einzelnen Software-Paketen, die verschiedene Unteraufgaben und Sonderfunktionen übernehmen, so dass nur der Programmiercode wirklich neu geschrieben werden muss, der für die jeweilige Software spezifisch ist.

Alle in s.o.l.i.d. verwendeten *packages* sind open source und werden von einem *Package Manager* verwaltet. Wir verwenden den Package Manager *yarn*.

Der Package-Manager installiert und aktualisiert alle Abhängigkeiten und Programmbibliotheken, die von unserem Framework benötigt werden.

Yarn muss heruntergeladen und für das jeweilige Betriebssystem installiert werden.
https://classic.yarnpkg.com/en/docs/install

**Achtung: Derzeit setzen wir *yarn classic* ein und nicht die aktuellste Version.**

## Visual Studio Code - Entwicklungsumgebung

Theoretisch müssen zum Programmieren nur Textdateien verändert werden - aber eine Entwicklungsumgebung (*IDE - Integrated development environment*) unterstützt das Programmieren mit zahlreichen Such- und Validierungsfunktionen und erleichtert die Arbeit immens, nicht zuletzt aufgrund der guten Integration mit Git.

In unserem Projekt wird fast ausschließlich die Entwicklungsumgebung *VSCode* verwendet, da sie kostenlos und ein mächtiges Tool ist. Andere Entwicklungsumgebungen können natürlich nach Präferenz benutzt werden.

Eine Entwicklungsumgebung (*IDE - Integrated development environment*) unterstützt das Programmieren mit zahlreichen Such- und Validierungsfunktionen. 

https://code.visualstudio.com/Download

## GitHub-Account

GitHub ist eine Online-Plattform zur Software-Entwicklung im Team und eng mit Git verzahnt. Die Software-Repräsentation eines Projekts wird als `repository` bezeichnet.

Ein repository (kurz auch 'repo' genannt) enthält alle Dateien, die zum Projekt gehören, sowie die komplette Entwicklungsgeschichte. 

Außerdem werden verschiedene Funktionen von der Online-Plattform bereitgestellt, wie z.B. eine Issue-Verwaltung für anstehende Aufgaben und verschiedene Projektplanungstools sowie Workflows zum Testen und Vorbereiten von Code-Änderungen.

http://github.com &rarr; Sign up

https://docs.github.com/en/get-started/quickstart/set-up-git

siehe hier insbesondere Schritte 2 und 3. Empfohlen wird die Authentifizierung per SSH - damit ist die Eingabe eines Passworts bei jeder Interaktion mit GitHub nicht erforderlich.

https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh

## Getting started

1. Zunächst müssen alle o.g. Tools installiert und ein GitHub-Account angelegt und eingerichtet werden
2. Auf der eigenen Festplatte muss ein Ordner angelegt werden, in welchen das repository geklont werden soll und mit dem es in Zukunft synchronisiert werden muss. Die Packages brauchen relativ viel Platz.

Die folgenden Schritte können im Prinzip von der Kommandozeile (*Git Bash* oder der Windows-Eingabeaufforderung / CMD) ausgeführt werden. Es ist meistens zweckmäßig, das Terminal aus VSCode heraus zu starten:

3. VSCode starten, den angelegten (leeren) Ordner öffnen und ein Terminal aufrufen (in der Standardkonfiguration mit `Strg+ö`). Das s.o.l.i.d.-Frontend-Repository wird mit dem Befehl `git clone https://github.com/zentrumnawi/solid-frontend ` in den aktuellen Ordner geklont.
4. Die benötigten Packages werden mit dem Befehl `yarn` installiert, dies dauert eine Weile.
5. Nach Abschluss der Installation kann das Frontend lokal gestartet werden: `yarn run serve <app-name>`. Nach Abschluss des Startprozesses wird eine URL (`http://localhost:4200`) angezeigt, mit der sich ein Browserfenster öffnet, in welchem die App ausgespielt wird und angesehen werden kann. Die Daten werden aus den Server-Schnittstellen des Staging-Systems geladen.
6. **Wichtig: Bevor der Code geändert wird, muss ein neuer branch im repository erzeugt werden!** Damit wird sichergestellt, dass alle Änderungen getrennt vom funktionierenden Status Quo sind. Für die Verwendung von Git im s.o.l.i.d.-Projekt gibt es eine eigene [Anleitung](solid-git-workflow).

Im Prinzip kann jetzt "entwickelt" werden. Nach jeder gespeicherten Änderung im Code wird die App neu geladen und kann im Browser direkt angesehen und getestet werden.

Alle Änderungen sollten gemäß unserer [Git-Coding-Rules](solid-coding-rules.md) regelmäßig *committed* werden.
