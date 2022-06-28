## Frontend App Release HowTo

1. Die Versionsnummer in `package.json` anpassen (nach SemVer-Prinzip `major.minor.patch`)
2. Ein Changelog schreiben
3. PR erstellen für `dev` -> `master` und mergen.
4. Einen neuen Release erstellen (Schaltfläche Release  --> `Draft a new Release`)
5. Eine Release-Message schreiben und die s.o.l.i.d.-Version mit angeben.
6. Im Web-Interface(!) einen _Tag_ auf den Merge-Commit bzw. `master` erstellen im Format `<appname>-v.X.Y.Z` (z.B. `dive-v.X.Y.Z`)
![image](https://user-images.githubusercontent.com/13869236/141685508-f77ab652-79b8-4f59-96e7-5c593e3b91cf.png)

Hinweis: Die App-Version ist identisch mit der s.o.l.i.d. Version! (Neu seit 17.03.2022)

7. `Publish Release`

Nach dem publishing des Releases sollte ein build-Prozess nur für diese App inklusive Deployment angestoßen werden.

Falls es ein Problem oder einen Fehler gibt und der Release mit der gleichen Nummer wiederholt werden soll, müssen Release UND Tag gelöscht werden. Der build wird nur durch ein neues Tag ausgelöst. 
