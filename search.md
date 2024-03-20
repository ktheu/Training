### Search mit bfs

Zur Übung sollen alle folgenden Probleme mit der Breitensuche gelöst werden.
Es gilt also, eine geeignete Modellierung zu finden und die Funktionen *nextstates* und *goaltest* zu implementieren.

```
from collections import deque
def bfs(startstate):
    frontier =  deque([startstate])
    prev = {startstate:None}
    while frontier:
        state = frontier.popleft()
        if goaltest(state):
            return prev, state
        for v in nextstates(state):
            if v not in prev:
                frontier.append(v)
                prev[v] = state
    return None, None

def reconstructPath(prev,goalstate):
    state = goalstate
    path = []
    while state is not None:
        path.append(state)
        state = prev[state]
    path.reverse()
    return path

def nextstates(state):
    '''
    returns: Liste mit den möglichen Folgezuständen
    '''
    pass


def goaltest(state):
    '''
    True, falls state ein goalstate ist
    '''
    pass



# Aufruf:
prev, state = bfs(startstate)
path = reconstructPath(prev, state)

```

#### Aufgabe: MOO-Operations

Gegeben ist ein String s der nur aus den Zeichen M und O besteht. Folgende Operationen sind möglich:
- (1) ersetze den ersten oder letzten Buchstaben durch den jeweils anderen ('M' wird zu 'O' bzw. 'O' wird zu 'M')
- (2) lösche den ersten oder letzten Buchstaben

Ziel ist es, durch eine minimale Anzahl von Operationen aus dem Anfangsstring s den String 'MOO' zu erzeugen.
Ermittle die Anzahl der Operationen und beschreibe einen Weg dorthin.

```
# Beispiel 1
s = 'MOMMOM'

Anzahl Operationen: 4
Lösche erstes Zeichen von MOMMOM
Lösche erstes Zeichen von OMMOM
Lösche letztes Zeichen von MMOM
Ändere letztes Zeichen von MOM auf O
MOO


# Beispiel 2
s = 'MMOMOMOMM'

Anzahl Operationen: 7
Lösche letztes Zeichen von MMOMOMOMM
Lösche erstes Zeichen von MOMOMOMM
Lösche erstes Zeichen von OMOMOMM
Lösche erstes Zeichen von MOMOMM
Lösche erstes Zeichen von OMOMM
Lösche letztes Zeichen von MOMM
Ändere letztes Zeichen von MOM auf O
MOO
```


#### Aufgabe: Girlande

Eine Girlande besteht aus Lampen, die vier verschiedene Farben haben können. Ein String s der Länge 4 und nur die Zeichen 1 bis 4 enthält, stellt eine Girlande dar.

```
# Beispiel:
s = '1211'     # Girlande besteht aus 1 Lampe mit Farbe 1, 1 Lampe mit Farbe 2, dann wieder 2 Lampen mit Farbe 1
```

Zu Beginn sind alle Lampen ausgeschaltet. Wir können beliebig oft folgende Operation durchführen:
Wähle eine Lampe und ändere ihren Status (aus 'An' mache 'Aus' und umgekehrt). Die nächste Operation darf aber nur an einer Lampe ausgeführt werden, die eine andere Farbe hat. 

Berechne die minimale Anzahl der Operationen, die wir benötigen, um alle Lampen der Girlande anzuschalten und beschreibe eine mögliche Lösung.
Gib -1 aus, wenn es nicht geht.

```
# In den Ausgabe ist die Lampe 1 die erste Lampe usw.
# Beispiel1:
s='1211'
Anzahl Operationen: 6
Lampe 1 ein
Lampe 2 ein
Lampe 3 ein
Lampe 2 aus
Lampe 4 ein
Lampe 2 ein

# Beispiel2:
s='1111'
-1

# Beispiel3:
s='1231'
Anzahl Operationen: 4
Lampe 1 ein
Lampe 2 ein
Lampe 3 ein
Lampe 4 ein
```

#### Aufgabe: Tubes

Gegeben sind zwei nicht leere Strings s1, s2 und ein leerer String s3. s1 und s2 bestehen nur aus '1' und '2', jede dieser Zeichen kommt insgesamt mindestens einmal vor. Ein Spielzug besteht darin, das letzte Zeichen von einem String zu entfernen und es einem anderen String hinzuzufügen, wobei für das Hinzufügen gilt: folgen zwei gleiche Zeichen hintereinander, so verschmelzen sie zu einem.

```
# Beispiel:
s1 = '121'
s2 = '1'
s3 = ''

# Zug 1-2 = letztes Zeichen von s1 zu s2 hinzufügen
s1 = '12'
s2 = '1'    # die hinzugfügte '1' ist mit der bestehenden '1' verschmolzen
s3 = ''
```

Wieviele Züge benötigen wir, damit in s1 und s2 nur noch eine '1' oder '2' steht und s3 leer ist. Gib die Anzahl der Züge und eine mögliche Zugfolge an.

```
Beispiel:
s1 = '121'
s2 = '12'

Zugfolge: 1-3 1-2 1-3 2-1 3-2  führt in 5 Zügen zu
s1 = '2'
s2 = '1'
```

#### Aufgabe: Flussüberquerung
Auf der Westseite des Flusses sind jeweils 3 A und 3 B. Auf einer Überfahrt zur Ostseite muss mindestens ein A oder B auf dem Schiff sein. In das Schiff passen höchstens 2 rein. Falls auf einer Seite mindestens ein A ist, dürfen es dort nicht mehr B als A sein.

Wie viele Überfahrten benötigt man, damit alle auf der Ostseite sind? Gib dazu eine mögliche Reihenfolge der Überfahrten aus.


#### Aufgabe: Kohl, Wolf, Ziege
Auf der einen Seite des Flusses sind Kohl, Wolf und Ziege und Mensch. Nur der Mensch kann die Fähre steuern und höchstens einen Gegenstand bzw Tier mitnehmen. Wolf und Ziege dürfen nie alleine auf einer Seite bleiben. Ziege und Kohl auch nicht. Wieviel Fahrten sind nötig? Gib eine mögliche Reihenfolge an.