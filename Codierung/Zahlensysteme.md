# Zahlensysteme


## BIN / DEZ / HEX

### Aufgaben: Zeit: 8 Minuten Umrechnung ohne Taschenrechner!
1. Was ist bei der Binärzahl 10111'0111 das MSB (=Most Significant Bit oder
Höchstwertigstes Bit) und was ist LSB (= Least Significant Bit oder
Kleinstwertigstes Bit)?

```
                | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
                |  1  |  0  |  0  | 1  |  1 |  1 | 0 | 1 | 1 | 1 |   
```

$$ 512 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 631$$

2. Umrechnung 11111111B in Dezimal 
$$247\text{D}$$
3. Umrechnung 01001101B in Dezimal
$$77\text{D}$$
4. Wieviele Bit werden benötigt, um 16 Bitkombinationen zu erstellen?
$$4$$
5. Umrechnung 11111111B in Hexadezimal
$$0\text{xFF}$$
6. Umrechnung 10110101B in Hexadezimal
$$0\text{xB}5$$
7. Umrechnung FFH in Binär
$$1111 1111\text{B}$$
8. Umrechnung E7H in Binär
$$1110 0111\text{B}$$
9. Umrechnung 37D in Binär
$$0011 0111\text{B}$$
10. Wieviele Bit werden mindestens benötigt, um 1000 Bitkombinationen darzustellen?
$$10$$


```
                | -512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
                |   1  |  0  |  0  | 1  |  1 |  1 | 0 | 1 | 1 | 1 |   
``` 

### Aufgaben: Zeit: 6 Minuten Ohne Taschenrechner!
1. Addiere die beiden 4Bit Integer 0101B + 0011B
$$1000\text{B}$$
2. Addiere die beiden 4Bit Integer 1101B + 0110B
$$0011\text{B}$$

 --> **Data Overflow**

3. Umrechnung -4D in Unsigned Integer mit Bitbreite 4

```
               | -8 | 4 | 2 | 1 |
               |  1 | 1 | 0 | 0 |
```
4. Umrechnung -18D in Unsigned Integer mit Bitbreite 8
```
| -128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|   1  |  1 |  1 | 0  | 1 | 1 | 1 | 0 |
```

## Float

32 Bit -> Single Precision

64 Bit -> **Double** Precision


```java
Dies wäre falsch: (Pseudocode)

float f = 300’000’000.0;
f = f + 1.0;
//liegt nicht mehr in der Genauigkeit
printf("%f",f); //Ergibt immer noch 300’000’000
```

```java
Dies ist ok: (Pseudocode)

float f = 3.0;
f = 1.0 / f;
```

### Aufgaben: Zeit: 6 Minuten

1. Welche Speicherkapazität in kiB (Hinweis: 1kiB=1024B) besitzt ein Arbeitsspeicher mit 12-Bit-Adressbus und 16-Bit-Datenbus?
$$ 2^{12} \cdot 2^{16} = 2^{28} = 2^{18} \cdot 2^{10} = 256 \cdot 1024 = 262144 \text{B} = 256 \text{kiB}$$
2. Zwei Geräte sind mit einer seriellen Leitung und einer Leitung für das Taktsignal von 1MHz verbunden.
- a. Wie viele Bytes können pro Sekunde übertragen werden?
$$ 1 \text{MHz} = 1 \cdot 10^6 \text{Hz} = 1 \cdot 10^6 \text{Bit/s} = \frac{1 \cdot 10^6}{8} = 125000 \text{B/s}$$
- b. Wie viele Bytes pro Sekunde können übertragen werden, wenn die Verbindung
der beiden Geräte nicht seriell, sondern 8 Bit-parallel wäre?
$$ 1 \text{MHz} = 1 \cdot 10^6 \text{Hz} = 1 \cdot 10^6 \text{Bit/s} = 1 \cdot 10^6 \text{B/s}$$
## Codierung von Text (Alphanumerische Zeichen)
### Beantworten sie nun die folgenden Kontrollfragen: 
#### Zeit: 10 Minuten
1. Wo wird UTF8 eingesetzt, wo UTF-16?
   - _UTF-8 wird häufig im Web und in Datenbanken verwendet, da es mit ASCII kompatibel ist und eine variable Länge für Zeichen bietet. UTF-16 wird oft in Anwendungen verwendet, die eine große Anzahl von Unicode-Zeichen benötigen, wie z.B. in Windows-Umgebungen._
2. Was bedeutet die Byteorder bei UTF-16?
   - _Die Byteorder bei UTF-16 bezieht sich darauf, in welcher Reihenfolge die Bytes für mehrbyte Zeichen gespeichert werden. Es gibt zwei Hauptarten: Big Endian (höchstwertiges Byte zuerst) und Little Endian (niedrigstwertiges Byte zuerst)._

3. Was bedeutet «abwärtskompatibel» im Zusammenhang mit UTF-8? Existiert diese
«Abwärtskompatibilität» auch bei UTF-16?
    - _Abwärtskompatibel bedeutet, dass UTF-8 alle ASCII-Zeichen in der gleichen Kodierung wie ASCII darstellt, was bedeutet, dass jede ASCII-Datei auch eine gültige UTF-8-Datei ist. Bei UTF-16 existiert diese Abwärtskompatibilität nicht, da es eine andere Kodierung für die Zeichen verwendet und nicht alle ASCII-Zeichen in der gleichen Form darstellt._
4. Wie beurteilen sie den Speicherbedarf von deutsch- oder englischsprachigem Text
bei ISO-8859-Codierung, UTF-8-Codierung und UTF-16-Codierung?
    - _Der Speicherbedarf für deutsch- oder englischsprachigen Text ist bei ISO-8859-Codierung in der Regel am geringsten, da es eine feste Länge von 1 Byte pro Zeichen verwendet. UTF-8 benötigt je nach Zeichen 1 bis 4 Bytes, was für die meisten englischen und deutschen Texte effizient ist. UTF-16 benötigt immer mindestens 2 Bytes pro Zeichen, was zu einem höheren Speicherbedarf führen kann, insbesondere bei Texten, die hauptsächlich aus ASCII-Zeichen bestehen._
5. Wann wird ein UTF-16-Code vier Byte lang?
    - _Ein UTF-16-Code wird vier Byte lang, wenn er ein Zeichen codiert, das außerhalb des Basic Multilingual Plane (BMP) liegt. Diese Zeichen werden als Surrogatpaare dargestellt, die jeweils 2 Byte lang sind, was insgesamt 4 Byte ergibt._
6. Wie müssen sie vorgehen, wenn sie z.B. in Word ein Zeichen eingeben wollen, das sie auf der
Tastatur zwar nicht finden, dessen Unicode sie aber kennen? (z.B. das Eurozeichen)
    - _In Word können sie das Eurozeichen eingeben, indem sie die Unicode-Nummer des Zeichens kennen und die Tastenkombination "Alt" + "X" verwenden. Zuerst geben sie die Unicode-Nummer (z.B. 20AC für das Eurozeichen) ein und drücken dann "Alt" + "X", um das Zeichen einzufügen._
7. Was wird das Problem sein, wenn sie auf dieselbe Weise wie in der vorangegangenen Aufgabe
das Unicode-Zeichen des Violinschlüssels (Musiknoten) in eine Wordtext einfügen wollen?
    - _Das Problem wird sein, dass der Violinschlüssel ein Zeichen ist, das außerhalb des Basic Multilingual Plane (BMP) liegt und daher als Surrogatpaar codiert werden muss. Die Eingabe der Unicode-Nummer allein wird nicht ausreichen, um das Zeichen korrekt darzustellen._


### Aufgaben: 
#### Zeit: 9 Minuten 
#### Hilfsmittel: Notepad++ und hexed.it
Untersuchen sie den Textstring €URO. Beachten sie, dass es sich beim ersten Zeichen
nicht um ein E sondern um das Eurozeichen € handelt.

**1. Wie lautet der ANSI-ASCII-Code für das Eurozeichen €?**
- _Das Eurozeichen € ist im ursprünglichen ASCII-Standard (ANSI-ASCII) nicht enthalten, da dieser nur 128 Zeichen umfasst. In der erweiterten Windows-1252 (ANSI) Codierung hat das Eurozeichen den Hex-Code **0x80** (hexadezimal) bzw. **128** (dezimal)._  
2. Wie lautet der Unicode für das Eurozeichen €?
    - _Der Unicode für das Eurozeichen € ist U+20AC._

**3. Schreiben sie den ANSI-ASCII Text €URO in HEX und in Binär.**
- HEX: 
$$
0\text{xE}282\text{AC} 55 52 4\text{F}
$$
- BIN:
    $$
    11100010 10000010 10101100 01010101 01010010 01001111
    $$

**4. Schreiben sie den UTF-8 Text €URO in HEX und in Binär.**
- HEX: $$0\text{xE}282\text{AC} 55 52 4\text{F}$$


- BIN:
    $$
    11100010 10000010 10101100 01010101 01010010 01001111
    $$
**5. Schreiben sie den UTF-16-BE Text €URO in HEX und in Binär.**
- HEX: 
    $$\text{FEFF}20\text{AC}00550052004\text{F}00000000$$
- BIN: 
    $$
    11111111 11111111 00100000 10101100 00000000 01010101 00000000 01010010 00000000 01001111 00000000
    $$
**6. Schreiben sie den UTF-16-LE Text €URO in HEX und in Binär.**
- HEX:
    $$20\text{AC}00550052004\text{F}00000000\text{FEFF}$$
- BIN:
    $$
    00100000 10101100 00000000 01010101 00000000 01010010 00000000 01001111 00000000 11111111 11111111
    $$
**7. Vergleichen sie die Resultate.**
 - _Der ANSI-ASCII-Code für das Eurozeichen ist nicht definiert, während der Unicode U+20AC ist. Der UTF-8 Text hat die gleiche HEX- und Binärdarstellung wie der ANSI-ASCII Text, da das Eurozeichen in UTF-8 als 3 Byte dargestellt wird. Der UTF-16-BE Text beginnt mit dem Byteorder Mark (BOM) FEFF, gefolgt von den UTF-16-Codes für die Zeichen. Der UTF-16-LE Text hat die Bytes in umgekehrter Reihenfolge._