# Kryptografie 2


## Aufgabe "Diffie-Hellman"

Verwenden sie im **Cryptool1** unter _"Einzelverfahren→Protokolle"_ die _"Diffie-Hellman-Demo"_ um den Diffie-Hellman-  Schlüsseltausch zu studieren. Experimentieren sie mit verschiedenen Parametern wie

- Bitlänge
- Primzahlen(Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)
- Geheimnis

Folgendes soll dabei geklärt werden:

- Wie werden die Teilschlüssel berechnet? (Mathematische Funktion?)
- Was bewirkt die Wahl von kleinen Primzahlen wie z.B. 7,11 oder 13?
- Als Resultat erhalten sie einen "geheimen Schlüssel". Was haben sie damit erreicht?

## Erarbeitung

➤ **Mathematisches Verfahren zur Berechnung der Teilschlüssel:**

1. Öffentliche Parameter:

   - Eine Primzahl `p`

   - Eine Basis (Generator) `g`, wobei `g < p`

2. **Jede Partei wählt ein geheimes Geheimnis:**

    - Alice wählt ein geheimes `a`

   - Bob wählt ein geheimes `b`

3. **Berechnung der Teilschlüssel (öffentlichen Schlüssel):**

    - Alice berechnet `A = g^a mod p`

    - Bob berechnet `B = g^b mod p`

4. **Austausch dieser Teilschlüssel über unsicheren Kanal**

5. **Berechnung des gemeinsamen Schlüssels:**
    - Alice berechnet: `K = B^a mod p`

    - Bob berechnet: `K = A^b mod p`

    Beide erhalten **denselben geheimen Schlüssel** `K`, weil:
```lua
    B^a mod p = (g^b)^a mod p = g^(ab) mod p`
    A^b mod p = (g^a)^b mod p = g^(ab) mod p`
```
🧪 Was bewirkt die Wahl kleiner Primzahlen (z.B. 7, 11, 13)?

    Mit kleinen Primzahlen wird der Schlüsselraum stark eingeschränkt.

    Dadurch kann ein Angreifer leicht alle möglichen Werte ausprobieren (Brute-Force-Angriff).

    In der Demo sieht man, dass der geheime Schlüssel oft schnell gefunden werden kann.

    Diese Werte sind unsicher für echte Kommunikation, dienen aber gut zu Lernzwecken.

Beispiel:
Wenn p = 11, g = 2, a = 3, b = 4
Dann:

    Alice berechnet 2^3 mod 11 = 8

    Bob berechnet 2^4 mod 11 = 5

    Gemeinsamer Schlüssel = 5^3 mod 11 = 4 und 8^4 mod 11 = 4

→ Beide haben denselben Schlüssel 4, aber mit nur 11 möglichen Modulo-Werten ist das leicht ausrechenbar.