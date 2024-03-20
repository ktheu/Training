### Search mit bfs

Zur Übung sollen alle folgenden Probleme mit der Breitensuche gelöst werden.
Es gilt also, eine geeignete Modellierung zu finden und die Funktionen *nextstates* und *goaltest* zu implementieren.

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