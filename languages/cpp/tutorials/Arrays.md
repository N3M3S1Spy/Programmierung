# C++ Arrays
## C++ Arrays
Arrays werden verwendet, um mehrere Werte in einer einzigen Variablen zu speichern, anstatt für jeden Wert eine eigene Variable zu deklarieren.

Um ein Array zu deklarieren, definieren Sie den Variablentyp, geben den Namen des Arrays gefolgt von eckigen Klammern an und bestimmen die Anzahl der Elemente, die es speichern soll:
```cpp
string cars[4];
```

Wir haben jetzt eine Variable deklariert, die ein Array mit vier Zeichenketten enthält. Um darin Werte einzufügen, können wir ein Array-Literal verwenden, indem wir die Werte in einer durch Komma getrennten Liste innerhalb geschweifter Klammern platzieren:

```cpp
string cars[4] = {"Volvo", "BMW", "Ford", "Mazda"};
```

Um ein Array mit drei Ganzzahlen zu erstellen, könnten Sie schreiben:

```cpp
int myNum[3] = {10, 20, 30};
```

## Zugriff auf die Elemente eines Arrays
Sie greifen auf ein Array-Element zu, indem Sie sich auf die Indexnummer innerhalb der eckigen Klammern `[]` beziehen.

Diese Anweisung greift auf den Wert des **ersten Elements** in **cars** zu:
### Beispiel:
```cpp
string cars[4] = {"Volvo", "BMW", "Ford", "Mazda"};
cout << cars[0];
// Outputs Volvo
```
> **Note:** Array indexes start with 0: [0] is the first element. [1] is the second element, etc.

## Ändern eines Array-Elements
Um den Wert eines bestimmten Elements zu ändern, geben Sie die Indexnummer an:
```cpp
cars[0] = "Opel";
```
### Beispiel:
```cpp
string cars[4] = {"Volvo", "BMW", "Ford", "Mazda"};
cars[0] = "Opel";
cout << cars[0];
// Now outputs Opel instead of Volvo
```

-----

# C++ Arrays und Loops
## Loop druch ein Array
Mit der `for` Schleife können Sie die Array-Elemente in einer Schleife durchlaufen.

Das folgende Beispiel gibt alle Elemente im Array **cars** aus:
### Beispiel:
```cpp
// Create an array of strings
string cars[5] = {"Volvo", "BMW", "Ford", "Mazda", "Tesla"};

// Loop through strings
for (int i = 0; i < 5; i++) {
  cout << cars[i] << "\n";
}
```
In diesem Beispiel wird der Index eines jeden Elements zusammen mit seinem Wert ausgegeben:
### Beispiel:
```cpp
string cars[5] = {"Volvo", "BMW", "Ford", "Mazda", "Tesla"};
for (int i = 0; i < 5; i++) {
  cout << i << " = " << cars[i] << "\n";
}
```
Und dieses Beispiel zeigt, wie man eine Schleife durch ein Array von Ganzzahlen macht:
### Beispiel:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
for (int i = 0; i < 5; i++) {
  cout << myNumbers[i] << "\n";
}
```

## Die foreach Loop
Es gibt auch eine "**for-each** Schleife" (eingeführt in C++ Version 11 (2011)), die ausschließlich zum Durchlaufen von Elementen in einem Array (und anderen Datenstrukturen, wie Vektoren und Listen) verwendet wird:
### Syntax:
```cpp
for (type variableName : arrayName) {
  // code block to be executed
}
```
Die folgenden Beispiele geben alle Elemente in einem Array mit Hilfe einer "**for-each** Schleife" aus:
### Beispiel:
Schleife durch Ganzzahlen:
```cpp
// Create an array of integers
int myNumbers[5] = {10, 20, 30, 40, 50};

// Loop through integers
for (int i : myNumbers) {
  cout << i << "\n";
}
```
### Beispiel:
Schleife durch Strings:
```cpp
// Create an array of strings
string cars[5] = {"Volvo", "BMW", "Ford", "Mazda", "Tesla"};

// Loop through strings
for (string car : cars) {
  cout << car << "\n";
}
```

-----

# C++ Array-Größe weglassen
## Array-Größe weglassen
In C++ müssen Sie die Größe des Arrays nicht angeben. Der Compiler ist intelligent genug, um die Größe des Arrays auf der Grundlage der Anzahl der eingefügten Werte zu bestimmen:
```cpp
string cars[] = {"Volvo", "BMW", "Ford"}; // Three array elements
```
Das obige Beispiel ist gleichbedeutend mit:
```cpp
string cars[3] = {"Volvo", "BMW", "Ford"}; // Also three array elements
```
Der letzte Ansatz wird jedoch als "gute Praxis" angesehen, da er die Wahrscheinlichkeit von Fehlern in Ihrem Programm verringert.

## Elemente bei der Deklaration weglassen

Es ist auch möglich, ein Array zu deklarieren, ohne die Elemente bei der Deklaration anzugeben, und sie später hinzuzufügen:
### Beispiel:
```cpp
string cars[5];
cars[0] = "Volvo";
cars[1] = "BMW";
cars[2] = "Ford";
cars[3] = "Mazda";
cars[4] = "Tesla"; 
```
**Hinweis:** Das obige Beispiel funktioniert nur, wenn Sie die Größe des Arrays angegeben haben.

Wenn Sie die Array-Größe nicht angeben, tritt ein Fehler auf:
### Beispiel:
```cpp
string cars[];  // Array size is not specified
cars[0] = "Volvo";
cars[1] = "BMW";
cars[2] = "Ford";
cars[3] = "Mazda";
cars[4] = "Tesla";

// error: array size missing in 'cars' 
```

## Feste Größe (Arrays) vs. Dynamische Größe (Vektoren)

Du wirst oft die Begriffe "feste Größe" und "dynamische Größe" hören, wenn es um Arrays in C++ geht.

Das liegt daran, dass die Größe eines Arrays in C++ festgelegt ist, was bedeutet, dass du **keine Elemente** hinzufügen oder **entfernen** kannst, nachdem es erstellt wurde.
### Arrays - Beispiel mit fester Größe
```cpp
// An array with 3 elements
string cars[3] = {"Volvo", "BMW", "Ford"};

// Trying to add another element (a fourth element) to the cars array will result in an error
cars[3] = "Tesla"; 
```

## Vectors
Für Operationen, die das Hinzufügen und Entfernen von Array-Elementen erfordern, bietet C++ **Vektoren** an, die **vergrößerbare Arrays** sind.

Die Größe eines Vektors ist dynamisch, was bedeutet, dass er je nach Bedarf wachsen und schrumpfen kann.

Vektoren befinden sich in der `<vector>`-Bibliothek und bieten viele nützliche Funktionen zum Hinzufügen, Entfernen und Modifizieren von Elementen:
### Vektoren - Beispiel für dynamische Größe
```cpp
 // A vector with 3 elements
vector<string> cars = {"Volvo", "BMW", "Ford"};

// Adding another element to the vector
cars.push_back("Tesla"); 
```
> Dies war nur eine Einführung in Vektoren, um dir mitzuteilen, dass es "vergrößerbare Arrays" gibt.
>
> Mach dir keine Sorgen, wenn du die obenstehende Syntax noch nicht verstehst.
> 
> Du wirst viel mehr über Vektoren und andere Datenstrukturen in einem späteren Kapitel lernen.

-----

# C++ Array Size
## Abrufen der Größe eines Arrays
Um die Größe eines Arrays zu ermitteln, können Sie den Operator sizeof() verwenden:
### Beispiel:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
cout << sizeof(myNumbers);
```
Result:
```cmd
20 
```

Warum wurde das Ergebnis `20` statt `5` angezeigt, obwohl das Array 5 Elemente enthält?

Das liegt daran, dass der `sizeof()`-Operator die Größe eines Typs in **Bytes** zurückgibt.

Du hast im Kapitel über Datentypen gelernt, dass ein `int`-Typ normalerweise 4 Bytes groß ist. Aus dem obigen Beispiel ergibt sich also 4 x 5 (4 Bytes x 5 Elemente) = **20 Bytes**.

**Um herauszufinden, wie viele Elemente ein Array enthält**, musst du die Größe des Arrays durch die Größe des ersten Elements im Array teilen:
### Beispiel:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
int getArrayLength = sizeof(myNumbers) / sizeof(myNumbers[0]);
cout << getArrayLength;
```
Result:
```cmd
5
```

## Schleife durch ein Array mit sizeof()
Im Kapitel über Arrays und Schleifen haben wir die Größe des Arrays in der Schleifenbedingung geschrieben (i < 5). Das ist nicht ideal, da es nur für Arrays einer bestimmten Größe funktioniert.

Durch die Verwendung des `sizeof()`-Ansatzes aus dem obigen Beispiel können wir jedoch Schleifen erstellen, die für Arrays jeder Größe funktionieren, was nachhaltiger ist.

Anstatt zu schreiben:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
for (int i = 0; i < 5; i++) {
  cout << myNumbers[i] << "\n";
}
```
Es ist besser zu schreiben:
### Beispiel:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
for (int i = 0; i < sizeof(myNumbers) / sizeof(myNumbers[0]); i++) {
  cout << myNumbers[i] << "\n";
}
```
Beachten Sie, dass Sie in C++ Version 11 (2011) auch die "for-each"-Schleife verwenden können, die noch sauberer und einfacher ist:
### Beispiel:
```cpp
int myNumbers[5] = {10, 20, 30, 40, 50};
for (int i : myNumbers) {
  cout << i << "\n";
}
```
> Es ist gut, die verschiedenen Möglichkeiten zu kennen, ein Array in einer Schleife zu durchlaufen, da man sie in verschiedenen Programmen antreffen kann.

-----