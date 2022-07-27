## Angular Update

Für Angular gibt es in der Regel zweimal im Jahr (Frühjahr und Herbst) ein Upgrade auf die nächste Major Version.

Da wir ein NX Monorepo für s.o.l.i.d. verwenden, muss das Upgrade mit den Upgrade-Tools durchgeführt werden - siehe [Dokumentation](https://nx.dev/using-nx/updating-nx).

_Hinweis: Die Migration mit den Angular-Tools funktioniert nicht unbedingt für Libraries sondern nur für die primäre App!_

Das allgemeine Vorgehen ist wie folgt:
* immer nur _eine_ Major Version pro Update
* alle Probleme beheben bis die App sauber funktioniert (z.B. Syntax-Änderungen, Deprecations...)
* anschließend kann erst auf die nächste Major Version upgegraded werden

Tipp: Den Angular-Update-Branch in einem eigenen, neu geklonten Repository durchführen, dann wirft es nicht die dependencies durcheinander.
