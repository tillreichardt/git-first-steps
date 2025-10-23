## Aufgabe 1

Um nun einen Edit zu simulieren, öffnen Sie in Ihrem Browser Ihren neu angelegten Branch und editieren Sie die Datei `edit.me`, indem Sie ein paar Zeilen hinzufügen. Klicken Sie anschließend auf `Commit changes` (ggf. im Browser nach unten scrollen). In der linken SideBar klicken Sie auf `Commits`, wählen Ihren Branch aus und überprüfen, dass Ihr Commit im remote repository existiert.

## Aufgabe 2

Wechseln Sie wieder auf Ihr Terminal und überprüfen Sie mit `git log`, dass der remote Commit sich nicht in Ihrem lokalen Repository befindet. Laden Sie diesen mithilfe von `git fetch` vom remote in Ihr lokales Repository. Überprüfen Sie, dass der neue Commit nun im `git log origin/<your_branch> ^<your_branch>` steht, aber sich die Dateien noch nicht in Ihrem lokalen Arbeitsverzeichnis befinden. Nun müssen Sie erst die neuen Änderungen mit Ihrem lokalen Arbeitsstand zusammenführen, indem Sie `git merge` aufrufen.

<strong>Hinweis:</strong> Die Parameter des zweiten `git log`-Befehls bedeuten sinngemäß: "Zeige alle Commits die in origin/<branch> erreichbar sind ohne die Commits, die in <branch> erreichbar sind." Das Zirkumflex ist Teil der Syntax.

<strong>Hinweis:</strong> Der Befehl `git pull` führt automatisch einen `git fetch` und anschließend `git merge` aus.

## Aufgabe 3

Wenn Sie den Inhalt von `sortierVerfahren.py` überprüfen, werden Sie feststellen, dass der Code für die Methode `bubbleSort` fehlerhaft ist. Ein BugFix läuft im Allgemeinen wie folgt ab:

1. Sie legen einen neuen Branch an (meist mit `-feature` oder `-bugfix` Suffix, hier: `<nutzername>-bugfix`) und checken diesen aus.
2. Sie führen die Änderungen durch
3. Sie laden Ihren Branch ins Repo hoch
(4. Es wird ein Merge-Request mit dem protected main-Branch erstellt)
(5. Der Verantwortliche pflegt Ihre Änderungen nach einem Code-Review in den main-Branch des Projekts ein)

Führen Sie für die Aufgabe die Schritte 1 bis 3 durch und berichtigen Sie dabei den Fehler in der Methode bubbleSort(). Sie können anschließend Ihren Algorithmus mittels `python3 main.py` überprüfen.

## Aufgabe 4

Wenn Sie nun die Logs Ihrer Branches `<nutzername>` und `<nutzername>-bugfix` vergleichen, sollten Sie feststellen, dass der `-bugfix`-Branch (mindestens) einen Commit voraus ist.

a) Erweitern Sie `sortierVerfahren.py` um den InsertionSort-Algorithmus.

b) Versuchen Sie nun, den Branch `<nutzername>-bugfix` in Ihren lokalen Branch zu mergen. Dies sollte mit einer aufschlussreichen Fehlermeldung scheitern, da Ihr aktueller Branch Änderungen beinhaltet, die nicht im lokalen Repository commited wurden. Mithilfe von `git stash` können Sie Ihre Änderungen zwischenspeichern. Mit `git stash list` können Sie einsehen, welche Änderungen Sie zwischengespeichert haben.

c) Mergen Sie nun den `-bugfix`-Branch, nachdem Sie Ihre Änderungen zwischengespeichert haben. Kontrollieren Sie den Inhalt von `sortierVerfahren.py`, dass sich zwar die gefixte Version von bubbleSort, aber nicht der InsertionSort-Algorithmus darin befindet. Laden Sie Ihren Zwischenspeicher mittels `git stash pop`, und kontrollieren Sie den Inhalt von `sortierVerfahren.py`. Kontrollieren Sie erneut den Inhalt, nach einem weiteren `git stash` Befehl.

d) Lassen Sie sich den Zustand Ihres Repositories mithilfe von `git log --graph --oneline --all` anzeigen.

## Aufgabe 5

Weitere Aufgaben mit Visualisierung des Git-Baumes finden Sie hier: https://learngitbranching.js.org