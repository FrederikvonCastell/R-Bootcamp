2 - Einstieg in R
========================================================
author: Benedict Witzenberger
date: 16.04.2019
autosize: true

Was ist R?
========================================================

> "R is a system for statistical computation and graphics. It consists of a language plus a run-time environment with graphics, a debugger, access to certain system functions, and the ability to run programs stored in script files."

> (Quelle: [R FAQ](https://cran.r-project.org/doc/FAQ/R-FAQ.html))

Was ist R?
========================================================

* Entstanden 1996 an der University of Auckland
* Entwickelt von Robert Gentleman und Ross Ihaka
* Basiert auf den Sprachen `S` und `Scheme`
* inzwischen gibt es eine breite Entwicklercommunity, die die Sprache voranbringt

R vs Python
========================================================
**R**

* Entwickelt von Statistikern
* viele statistische Tools
* einfache M�glichkeiten zur Datenvisualisierung
* gutes User-Interface durch RStudio
* vielf�ltigere L�sungen f�r dasselbe Problem
* verbreitet im Journalismus und der Wirtschaft
* relative steile Lernkurve, aber nach den Basics geht es schnell
* Bibliotheken: CRAN (Comprehensive R Archive Network)

***

**Python**

* Entwickelt in der Informatik
* multi-funktionelle Sprache
* schneller
* einfachere Syntax
* weniger L�sungen f�r dasselbe Problem
* relativ flache Lernkurve
* Bibliotheken: PyPi

R vs Python
========================================================

Es gibt Bibliotheken, die Programmcode der einen Sprache in der anderen Sprache ausf�hren k�nnen.

* R in Python: RPy2
* Python in R: rPython

R vs Python
========================================================

Fazit: 

Beide Sprachen haben vor und Nachteile.

Wir lernen hier R, weil es im Journalismus weiter verbreitet ist. Seine Konzepte stammen eher aus der Statistik stammen - und f�hren daher f�r unsere Zwecke schneller zu Ergebnissen.


Heute Vormittag
========================================================

* Die Kommandozeile

* Editoren

* Github

Die Kommandozeile
========================================================

**Warum?**

Jeder nutzt heute haupts�chlich grafische Benutzerinterfaces - aber: �ber die Kommandozeile geben wir Befehle direkt an den Computer.

Programme k�nnen schnell und direkt aufgerufen werden.

Alternative Namen: Konsole, Terminal, Bash, Shell (z.B. bei OS X, Linux)

Microsofts `cmd.exe` nutzt teilweise andere Befehle. Deswegen haben wir versucht, auf Windows 10-Rechnern Linux zu installieren.

Kommandozeile: Wo?
========================================================

**Windows**: Windows-Taste, �cmd�. Oder Startmen� <U+2192> Alle Programme <U+2192> Zubeh�r <U+2192> Eingabeaufforderung

**Linux Subsystem f�r Windows**: Eingabeaufforderung <U+2192> �bash�

**Mac OS X**: Programme <U+2192> Zubeh�r <U+2192> Terminal

**Linux**: Programme <U+2192> Zubeh�r <U+2192> Terminal (versionsabh�ngig)


Bash vs DOS
========================================================

Change Directory: `cd` in Bash, `cd` oder `chdir` in DOS

List Contents of Directory:  `ls` in Bash, `dir` in DOS

Move or Rename a File: `mv` in Bash, `move` und `rename` in DOS

Copy a File: `cp` in Bash, `copy` in DOS

Delete a File: `rm` in Bash, `del` oder `erase` in DOS

Create a Directory:  `mkdir` in Bash, `mkdir` in DOS

Use a Text Editor: `vi` or `nano` in Bash,  `edit` in DOS


Eine Kommandozeileneingabe
========================================================

![](anatomy.png)

Quelle: https://www.learnenough.com/command-line-tutorial/basics

Let's start!
========================================================

`whoami`

```
benedict@LAPTOP-SG0F5D8L:~$ whoami
benedict
```

Echo
========================================================

`echo xyz` gibt *xyz* zur�ck. In der Konsole ist das vielleicht erstmal egal, aber wir k�nnen das auch in Dateien schreiben

`echo "Hello World"`

`echo Hello World`

`echo "Hello World`
 
![](hello_world.png)

**L�sung, wenn die Konsole h�ngt: Strg + C / Ctrl + C**

Echo in eine Datei
========================================================

`echo "Ich bin ein Test-Text" > test.txt`

`>` leitet den Inhalt von echo in eine Datei

Wie k�nnen wir das �berpr�fen?

**UNIX**

`cat`

**Windows**

`type`

Noch eine Zeile hinzuf�gen:

`echo "Ich bin ein weiterer Test-Text" >> test.txt`

`>>` ist der Append-Operator

Editor �ffnen
========================================================

`notepad test.txt (Win) | open test.txt (Unix)`


Verzeichnis wechseln / Dateien anzeigen
========================================================

**UNIX**

`cd [Ordnername]` oder `cd ..` f�r eine Ebene hoch

`ls`

**Windows**

`cd [Ordnername]` oder `cd ..` f�r eine Ebene hoch

`dir`

Suchen:

`ls *.txt` oder

`dir *.txt`

Noch detaillierter suchen
========================================================

**UNIX**

`find ./ -iname �datei.endung�`

`grep -i -R �suchtext� ./*`

**WINDOWS**

`dir /b /s �datei.endung�`

`findstr /s /m �suchtext� *.*`

Hilfe bekommen
========================================================

**UNIX**

`help [Kommando]` (auch gut: `man [Kommando]` f�hrt zur Hilfeseite)

**WINDOWS**

`help [Kommando]`

Meistens funktionieren auch:

```
[Kommando] -h
[Kommando] -help
[Kommando] --help

```

Einen �berblick gewinnen
========================================================

**UNIX**

`find .`


`ps -ax`

`kill [PID]`

**WINDOWS**

`tree`

`tasklist`

`tasklist -PID [PID]`

Neue (leere) Datei erstellen
========================================================

**UNIX**

`touch test.txt`

**WINDOWS**

`echo. > test.txt` oder `type nul > test.txt`

Datei umbenennen
========================================================

**UNIX**

`mv test_alt.txt test_neu.txt`

**WINDOWS**

`rename test_alt.txt test_neu.txt`

Geht auch f�r alle Dateien mit einer Auswahl:

`mv *.htm *.html`

`rename *.htm *.html`

**TIPP**

Verwende bei Dateinamen die TAB-Taste f�r Autovervollst�ndigung.


Datei kopieren
========================================================

**UNIX**

`cp test.txt test_kopie.txt`

**WINDOWS**

`copy test.txt test_kopie.txt`


Datei l�schen
========================================================

**UNIX**

`rm test_kopie.txt` (`-f` ohne Nachfragen und `-r` f�r Unterverzeichnisse)

**WINDOWS**

`del test_kopie.txt` (`/F` ohne Nachfragen und `/S` f�r Unterverzeichnisse)

Sehr m�chtiges Werkzeug, sollte mit Bedacht eingesetzt werden.

NICHT BENUTZEN: `rm -rf /` im Root-Verzeichnis

***

![](rm_rf.png)

Zusammen:
========================================================

1. cd (Win) | pwd (Unix)

2. dir (Win) | ls (Unix)

3. cd Desktop

4. mkdir rBootcamp

5. dir | ls

6. rmdir /S rBootcamp (Win) | rm -r rBootcamp (Unix)

7. exit


�bung Kommandozeile
========================================================

1. Schreibe "Hallo Welt" in die Konsole.

2. Erstelle ein Verzeichnis h�her eine leere Datei mit dem Namen `kommandozeile.txt`.

3. Schreibe "Ich kann Kommandozeile" in die Datei mit dem Namen `kommandozeile.txt`

4. Erstelle eine Kopie von dieser Datei.

5. �berpr�fe, ob die Kopie erstellt wurde.

6. L�sche die Kopie �ber die Kommandozeile.


Weitere n�tzliche Tools
========================================================

`ip a` (UNIX) oder `ipconfig` (Windows): Gibt Infos �ber die aktuellen Netzwerkverbindungen

`curl` kann Dateien herunterladen

`tar` kann Dateien ver- und entpacken

CURL (Client URL)
========================================================

`curl www.example.com`

`curl -v www.example.com` (Verbose-Mode mit mehr Infos)

`curl -o webseite.html www.example.com`

`curl wttr.in/Munich`

Alternative: wget

Programme installieren
========================================================

**Windows:** schwierig

**Linux** (als Admin): �ber apt install

Mac** OS**: Paketmanager Homebrew: https://brew.sh/

------

Zum Beispiel: 

Git: https://wiki.ubuntuusers.de/Git/

`sudo apt-get install git`

oder

`brew install git`

Beispiel: Bild-Metadaten verifizieren
========================================================

Exif-Tools als Anhaltspunkte

https://wiki.ubuntuusers.de/ExifTool/

`exiftool [Bildname]`

Beispiel: PDFs bearbeiten
========================================================

pdftk kann PDFs zusammenf�gen, teilen, bearbeiten, ausf�llen ...

`pdftk EINGABEDATEI OPERATION OPTION output AUSGABEDATEI PASSWORT RECHTEOPTION`

Zusammenf�gen:

`pdftk datei1.pdf datei2.pdf datei3.pdf cat output datei123.pdf`


Editoren
========================================================

In der Kommandozeile k�nnen wir verschiedene Editoren aufrufen.

**UNIX**

`open datei.txt`

`vim datei.txt`

`nano datei.txt`

**Windows**

`notepad datei.txt`

Visuelle Editoren
========================================================

F�r die Softwareentwicklung gibt es g�ngige Editoren:

[Visual Code Studio](https://code.visualstudio.com/) von Microsoft, Open Source

[Sublime](https://www.sublimetext.com/) sehr schnell, nervt mit Lizenzfrage

[Atom](https://atom.io/) Projekt von Github

**Unser Gl�ck:** 

F�r R ist die g�ngige Umgebung RStudio. Theoretisch k�nnen wir aber auch einen anderen Editor benutzen.

Git
========================================================

Versionskontrolle (Version Control System, VCS): Erm�glicht gemeinsames Arbeiten an (Programmier-)Projekten, Nachvollziehen von Arbeitsschritten, Zur�cksetzen auf fr�here Versionen, Zusammenf�hren neuer Elemente

Git ist freie Software, sehr popul�r (Android, Ruby on rails, Eclipse, VLC media player, �). 

Funktioniert lokal oder auf Servern. 

Anbieter z.B: GitHub, GitLab, Bitbucket

Git installieren
========================================================

�berpr�fen wir, welche Version wir installiert haben

```
git --version
```

![](git.png)

Installiert haben wir ja gestern schon.

Git konfigurieren
========================================================

Usernamen eingeben:

`git config --global user.name "YOUR_USERNAME"`

Usernamen nochmal checken:

`git config --global user.name`

Emailadresse eingeben: 

`git config --global user.email "your_email_address@example.com"`

Emailadresse nochmal checken:

`git config --global user.email`

Alles checken:

`git config --global --list`

Repositories
========================================================

![](repository.png)

Branches
========================================================

Bekannte Dateinamen sind:

Text.doc

Text-final.doc

Text-final2.doc

Git �bernimmt dieses Dilemma f�r uns mit Branches: neben unserer `master`-Branch k�nnen wir beliebig nebenbei arbeiten

![](branching.png)

Commits
========================================================

Verschiedene Versionen eins Projekts werden in Commits gespeichert.

Jeder Commit hat eine Commit-Message: zum Beispiel "Intial commit", "removed xyz", "added xyz"

Push und Pull
========================================================

Commitete Dateien, die wir auf unserem Rechner ver�ndert haben, **pushen** wir auf der Git-Server, damit sie f�r alle Mitarbeitenden verf�gbar sind.

Dateien, die auf dem Server ver�ndert sind, **pullen** wir auf unseren Rechner.

Der **Pull-Request** in einem Projekt bedeutet, dass der Code in einem Branch gepr�ft und in ein Hauptprogejt �bernommen werden soll. In Github werden die Unterschiede im Code in rot und gr�n dargestellt.

Erfolgreiche Pull-Requests werden **gemergt**. Der Code wird zusammengef�hrt.

Clones
========================================================

Repositories, in denen wir gerne lokal weiterarbeiten wollen, k�nnen wir **klonen**.

Dadurch entsteht eine Verbindung von unserem Computer zum Repository, und wir k�nnen immer den aktuellsten Stand des Projekts abrufen.

Die Befehle in Github Bash I
========================================================

`git init`- Repo im aktuellen Ordner erstellen

`git remote add origin https://github.com/munichrocker/mynewrepository.git` - Repository vom Server verbinden

`git status` - zeigt Ver�nderungen

`git add .` - f�gt alle (durch den Punkt) Dateien im Ordner zu Git hinzu

`git commit -m "Initial Commit"` - f�gt die �nderungen zu einem Commit zusammen

Die Befehle in Github Bash II
========================================================

Branches:

`git branch`

`git checkout -b [neue Branch]` - erstellt neue Branch und wechselt dorthin. Nur Wechseln geht ohne das `-b` 

`git push -u origin master` - pusht in die Master-Branch in unserem Server-Repository. Statt Master k�nnen wir auch eine andere Branch ausw�hlen.

`git pull origin master` - holt die Dateien vom Server zur�ck auf den Computer

F�r Github gibt es auch grafische Benutzeroberfl�chen - was euch lieber ist.

�bung Git
========================================================

1. Erstellt ein neues Repository (privat oder �ffentlich) auf Github

2. Klont das Repository auf euren Computer

3. Erstellt eine Textdatei in das lokale Repository

4. Committet und pusht die Datei zu Github

5. Erstellt eine neue Branch und eine neue Datei

6. Pusht die Datei in die neue Branch

Bonus:

7. Versucht auf Github einen Pull-Request zu erstellen und ihn zu mergen.
