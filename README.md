# Git First Steps

Diese Übungen sollen Ihnen helfen, das Versionierungstool **Git** bedienen zu können.

## Getting started

Öffnen Sie ein Terminal (Git Bash oder WSL), um die folgenden Übungen zu absolvieren.

a) Konfigurieren Sie git, indem Sie **global** Ihren Namen und Ihre studentische Email-Addresse (vorname.nachname@htwk-leipzig.de) setzen.

<strong>Hinweis:</strong> Die spitzen Klammern (`>,<`) symbolisieren meistens sogenannte Tags und sind nicht Teil der Eingabe.

`git config --global user.name "<vorname>.<nachname>"`

`git config --gobal user.email "<Ihre Email>"`

Überprüfen Sie, dass Ihre Änderungen akzeptiert wurden.

`git config --global --list`

Die Ausgabe sollte (ungefähr) wie folgt aussehen:

```
user.email=vorname.nachname@stud.htwk-leipzig.de
user.name=vorname.nachname
```

**Hinweis:** Falls Sie sich den Eintrag aufgrund fehlender Zugriffsrechte nicht anzeigen lassen können, fahren Sie dennoch in der Übung fort.

b) Legen Sie für diese Übung ein eigenes Verzeichnis auf Ihrer Festplatte an und wechseln Sie im Terminal in das Verzeichnis.

c) Im Terminal, welches Sie standardmäßig verwenden, erzeugen Sie sich einen SSH-Key mit dem Befehl: 

`ssh-keygen -C <Ihre HTWK-Email>`

Das erzeugte Schlüsselpaar wird standardmäßig in Ihrem User-Verzeichnis/.ssh abgelegt. Im GitLab klicken Sie auf Ihr Profilbild > Preferences > SSH Keys > Add New Key. In die Textbox `Keys` kopieren Sie anschließend den Inhalt der Datei `id_git_exercise.pub`. Dieser Schlüssel wird von GitLab verwendet, um Sie (und Ihre Kommandos) zu identifizieren und zu authorisieren.

<strong>Hinweis:</strong> Das Programm `ssh-keygen` fragt Sie nach einem Dateinamen samt Pfad. Wenn Sie nur einen Dateinamen angeben, dann landen die Keys in Ihrem aktuellen Verzeichnis, sofern Sie die notwendigen Schreibrechte dazu besitzen.

<strong>Hinweis:</strong> Wer bereits einen SSH-Key besitzt, kann auch diesen im GitLab hinterlegen.

d) Im Verzeichnis des Git-Repositories im Terminal können Sie nun noch konfigurieren, welchen ssh-key Sie für git verwenden möchten:

`git config --global core.sshCommand "ssh -i ~/.ssh/id_git_exercise`

## Aufgabe 1

a) Clonen Sie dieses Repository mittels git und Terminal: `git clone git@gitlab.dit.htwk-leipzig.de:grundlagen-der-informatik/git-first-steps.git`. Ggf. müssen Sie danach Ihre ssh-Passphrase eingeben.

Anschließend wechseln Sie in das heruntergeladene Verzeichnis:
`cd git-first-steps`

b) Das remote Ihres geclonten Projekts zeigt nun noch auf das GitLab-Repository. Erzeugen Sie im Browser in GitLab ein eigenes Projekt, welches Sie für diese Übung als Remote Repository verwenden werden (New Project > Create blank project). Wählen Sie einen Namen, z.B. `git-exercise` und - ganz wichtig! - entfernen Sie das Häkchen bei `Initialize repository with a README `.

c) Nun müssen wir noch das alte remote durch Ihr neu erzeugtes remote Projekt in GitLab ersetzen. Dafür wechseln Sie in Ihr Terminal und in das Verzeichnis des geclonten Projekts aus Aufgabe a). Anschließend geben Sie folgenden Befehl ein:

`git remote set-url origin <URI>`

wobei `<URI>` die URI ist, die Sie aus Ihrem Projekt mittels Code > Clone with SSH erhalten und die mit `git@gitlab.dit.htwk-leipzig.de` beginnt:

`git remote set-url origin git@gitlab.dit.htwk-leipzig.de:<vorname>.<nachname>/<projekt_name>.git`
(Spitze Klammern markieren lediglich Platzhalter)

Nun wird es Zeit, unseren Code in das remote repository zu schreiben:

`git push`

Überprüfen Sie nun in der Weboberfläche von GitLab das Ergebnis ihres Kommandozeilenbefehls.

## Aufgabe 2

Wenn das geschafft ist, widmen Sie sich den Aufgaben in `Aufgabe2.md` dieses Repositories.