### Blockly - Python

---

<img src='./images/bild0.png' width='200'>

```
for i in range(6):
    oben()
```
---

<img src='./images/bild2.png' width='200'>

```
if hindernisRechts():
    oben()
```

---
<img src='./images/bild1.png' width='200'>

```
if hindernisOben():
    unten()
else:
    oben()
```

---
<img src='./images/bild7.png' width='250'>

```
if hindernisRechts():
    if hindernisOben():
        unten()
    else:
        oben()
else:
    rechts()
```

---
<img src='./images/bild6.png' width='300'>

```
if not plattformOben():
    bauePlattformOben()
```

---
<img src='./images/bild3.png' width='300'>

```
while aufPfeilNachRechts():
    rechts()
```

---
<img src='./images/bild4.png' width='300'>

```
for i in range(1,18):
    geheSchritte(i)
    links()
```

---
<img src='./images/bild5.png' width='300'>

```
for i in range(17,0,-1):
    geheSchritte(i)
    rechts()
```
---
