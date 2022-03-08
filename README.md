# Projekt 4.2: Eine existierende Todo-Liste auslesen

Diese Übung basiert auf den Übungen https://github.com/Oberschule-an-der-Egge/python-04 und https://github.com/Oberschule-an-der-Egge/python-04.01. Es wird empfohlen beide Übungen zu absolvieren, bevor die hier vorliegende Übung angegangen wird.


##Dateien aufrufen.

Um in Python mit einer Datei arbeiten zu können, ist es notwendig den vollständigen Dateipfand als String vorliegen zu haben. Wie man den Dateipfad Betriebssystemunabhängig auslesen aknn, wurde in https://github.com/Oberschule-an-der-Egge/python-04.01 erläutert.


##Daten einlesen:

Um den Inhalt einer Datei einzulesen verwenden wir die Methode  wir `open()` und den Kontextmanager `with .. as ..:`

```python
with open(file_path, "r") as file_in:  # Default for open() is option 'r'/read
    data = file_in.read()

```

Dieses mal verwenden wir als zweites Argument für open `"r"` also "read". Theoretisch, könnte man dieses Argument sogar weglassen und open nur das Argument file_path als String übergeben. Grunfd hierfür ist, dass open "r" als Standartargument eingestellt hat und, erhält die Methode kein zweites Argument, annimt, dass "r" gemeint ist.


##Probieren Sie es aus!

Erstellen Sie eine Textdatei mit beliebiegen Inhalt. Versuchen Sie den Inhalt einzulesen und sich via `print` ausgeben zu lassen.


##Eine Liste einlesen

Probieren Sie nun eine beliebige Liste einzulesen.

Listen haben in Python immer das Format
`['Element 1', 'Element 2', 'Element 3', ..., 'Element n']`

Legen Sie also eine beliebige Liste nach obigem Format in Ihrer Textdatei ab und lesen Sie sie ein.

Um einen String, der oben gezeigtes Format aufweist in eine Liste umzuwandeln können Sie die methode `eval()` verwenden. Als Argument verlangt eval einen String mit Listeneigenschaften.


Folgendes könnte helfen:


```python
liste = eval(data)
print(liste)

```


## Bonusaufgabe

Am Ende von https://github.com/Oberschule-an-der-Egge/python-04.01 sollten Sie den Quellcode so editieren, dass Ihre Liste in die Ausgabedatei im Format

```
Element 1
Element 2
Element 3
...
Element n
```

geschrieben wird.

Versuchen Sie eine Funktion zu erstellen, die dieses Listenformat einlesen kann und die einzelnen Elemente in einer Liste in Ihrem Programm ablegt.

Folgendes könnte Hilfreich sein:

```python
            for entry in file_in.readlines():
                data.append(entry.rstrip())  # .rstrip removes the \n at the end of each line
```     
