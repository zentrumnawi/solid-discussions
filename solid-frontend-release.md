1. Die Versionsnummer in `package.json` anpassen (nach SemVer-Prinzip `major.minor.patch`)
2. Ein Changelog schreiben
3. PR erstellen für `dev` -> `master` und mergen.
4. Einen neuen Release erstellen (Schaltfläche Release  --> `Draft a new Release`)
5. Im Web-Interface(!) einen _Tag_ auf den Merge-Commit erstellen im Format `<appname>-vX.Y.Z` (z.B. `dive-vX.Y.Z`)
![image](https://user-images.githubusercontent.com/13869236/141685508-f77ab652-79b8-4f59-96e7-5c593e3b91cf.png)

Nach dem publishing des Releases sollte ein build-Prozess nur für diese App angestoßen und anschließend deployed werden.

Falls es ein Problem gibt, müssen Release UND Tag gelöscht werden. Danach kann der Tag neu erstellt werden.
