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

Die Kommandozeile

Editoren

Github

Die Kommandozeile
========================================================

**Warum?**

Jeder nutzt heute haupts�chlich grafische Benutzerinterfaces - aber: �ber die Kommandozeile geben wir Befehle direkt an den Computer.

Microsofts `cmd.exe` nutzt teilweise andere Befehle.


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


Echo
========================================================

`echo xyz` gibt *xyz* zur�ck. In der Konsole ist das vielleicht erstmal egal, aber wir k�nnen das auch in Dateien schreiben

Auf **UNIX**

`echo "Hello World"`

`echo Hello World`

`echo "Hello World`

 

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


Verzeichnis wechseln / Dateien anzeigen
========================================================

**UNIX**

`cd`

`ls`

**Windows**

`cd`

`dir`

Suchen:

`ls *.txt` oder

`dir *.txt`


Neue Datei erstellen
========================================================

**UNIX**

`touch`

**WINDOWS**

`echo. > test.txt` oder `type nul > test.txt`


�bung Kommandozeile
========================================================

Schreibe "Hallo Welt" in die Konsole

Wechsle ein Verzeichnis h�her und schreibe dort "Ich kann Kommandozeile" in eine Datei mit dem Namen kommandozeile.txt





Weitere n�tzliche Tools
========================================================

`ip a` (UNIX) oder `ipconfig` (Windows)

`curl`

`tar`
