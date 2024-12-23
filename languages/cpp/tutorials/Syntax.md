# C++ Syntax
Zerlegen wir den folgenden Code, um ihn besser zu verstehen:  
```c++
#include <iostream>
using namespace std;

int main() {
  cout << "Hello World!";
  return 0;
} 
```

### Beispiel erklärt 

**Zeile 1:** `#include <iostream>` ist eine **Header-Datei-Bibliothek**, die es uns ermöglicht, mit Eingabe- und Ausgabeobjekten wie `cout` (in Zeile 5 verwendet) zu arbeiten. Header-Dateien erweitern die Funktionalität von C++-Programmen.

**Zeile 2:** `using namespace std` bedeutet, dass wir Namen für Objekte und Variablen aus der Standardbibliothek verwenden können.

> **Hinweis:** Machen Sie sich keine Sorgen, wenn Sie nicht verstehen, wie `#include <iostream>` und `using namespace std` funktionieren. Betrachten Sie es einfach als etwas, das (fast) immer in Ihrem Programm vorkommt.

**Zeile 3:** Eine Leerzeile. C++ ignoriert Leerzeichen. Wir verwenden sie aber, um den Code lesbarer zu machen.

**Zeile 4:** Ein weiteres Element, das immer in einem C++-Programm vorkommt, ist `int main()`. Dies wird eine **Funktion** genannt. Jeder Code innerhalb der geschweiften Klammern `{}` wird ausgeführt.

**Zeile 5:** `cout` (ausgesprochen "see-out") ist ein **Objekt**, das zusammen mit dem Einfügeoperator (`<<`) verwendet wird, um Text auszugeben/zu drucken. In unserem Beispiel wird es "Hello World!" ausgeben.

**Hinweis:** In C++ wird zwischen Groß- und Kleinschreibung unterschieden: "cout" und "Cout" haben unterschiedliche Bedeutung. 

**Hinweis:** Jede C++-Anweisung endet mit einem Semikolon `;`.

**Hinweis:** Der Hauptteil von `int main()` könnte auch wie folgt geschrieben werden: `int main () { cout << "Hallo Welt! "; return 0; }`

**Zur Erinnerung:** Der Compiler ignoriert Leerzeichen. Mehrere Zeilen machen den Code jedoch besser lesbar.

**Zeile 6:** `return 0`; beendet die Hauptfunktion.

**Zeile 7:** Vergessen Sie nicht, die schließende geschweifte Klammer `}` hinzuzufügen, um die Hauptfunktion tatsächlich zu beenden.

### Namensraum weglassen
Sie werden vielleicht einige C++-Programme sehen, die ohne die Standard-Namespace-Bibliothek laufen. Die Zeile `using namespace std` kann weggelassen und durch das Schlüsselwort std ersetzt werden, gefolgt von dem Operator `::` für einige Objekte:
```c++
#include <iostream>

int main() {
  std::cout << "Hello World!";
  return 0;
} 
```

> **Hinweis:** Es bleibt Ihnen überlassen, ob Sie die Standard-Namespace-Bibliothek einbinden wollen oder nicht.

# C++-Anweisungen
Ein **Computerprogramm** ist eine Liste von "Anweisungen", die von einem Computer "ausgeführt" werden sollen.

In einer Programmiersprache werden diese Programmieranweisungen als **Anweisungen** bezeichnet.

Die folgende Anweisung "weist" den Compiler an, den Text "Hello World" auf dem Bildschirm zu drucken:
```c++
cout << "Hello World!";
```

Es ist wichtig, dass Sie die Anweisung mit einem Semikolon abschließen `;`
Wenn Sie das Semikolon (`;`) vergessen, tritt ein Fehler auf und das Programm wird nicht ausgeführt:
```c++
cout << "Hello World!"
```
```cmd
error: expected ';' before 'return'
```