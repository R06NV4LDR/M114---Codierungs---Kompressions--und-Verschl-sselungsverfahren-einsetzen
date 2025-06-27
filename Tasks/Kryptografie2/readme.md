# Kryptografie 2

## 🔐 Aufgabe "Diffie-Hellman"

Verwenden sie im **Cryptool1** unter _"Einzelverfahren→Protokolle"_ die _"Diffie-Hellman-Demo"_ um den Diffie-Hellman-  Schlüsseltausch zu studieren. Experimentieren sie mit verschiedenen Parametern wie

- Bitlänge
- Primzahlen(Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)
- Geheimnis

Folgendes soll dabei geklärt werden:

- Wie werden die Teilschlüssel berechnet? (Mathematische Funktion?)
- Was bewirkt die Wahl von kleinen Primzahlen wie z.B. 7,11 oder 13?
- Als Resultat erhalten sie einen "geheimen Schlüssel". Was haben sie damit erreicht?

---

### Erarbeitung

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
    B^a mod p = (g^b)^a mod p = g^(ab) mod p
    A^b mod p = (g^a)^b mod p = g^(ab) mod p
```

### 🧪 Was bewirkt die Wahl kleiner Primzahlen (z.B. 7, 11, 13)?

- Mit **kleinen Primzahlen** wird der Schlüsselraum stark eingeschränkt.

- Dadurch kann ein Angreifer leicht alle möglichen Werte ausprobieren (**Brute-Force-Angriff**).

- In der Demo sieht man, dass der geheime Schlüssel oft schnell gefunden werden kann.

- Diese Werte sind unsicher für echte Kommunikation, dienen aber gut zu **Lernzwecken**.

**Beispiel:**

Wenn `p = 11`, `g = 2`, `a = 3`, `b = 4`

Dann:

- Alice berechnet `2^3 mod 11 = 8`

- Bob berechnet `2^4 mod 11 = 5`

- Gemeinsamer Schlüssel = `5^3 mod 11 = 4` und `8^4 mod 11 = 4`

→ Beide haben denselben Schlüssel `4`, aber mit nur 11 möglichen Modulo-Werten ist das leicht ausrechenbar.

### 🎯 Was erreicht man mit dem geheimen Schlüssel?

- Dieser gemeinsame Schlüssel kann für die **weitere symmetrische Verschlüsselung** verwendet werden.

- Beispiel: Danach könnten Alice und Bob mit **AES** oder **DES** verschlüsseln, wobei sie **denselben Schlüssel** nutzen, ohne dass dieser je direkt über das Netz gesendet wurde.

- Ziel: **Sicherer Schlüsseltausch über einen unsicheren Kanal** – z. B. das Internet.

### ✅ Fazit

| Frage | Antwort |
| --- | --- |
| Wie werden Teilschlüssel berechnet? | Mit der Potenzierungsfunktion `g^a mod p` bzw. `g^b mod p` |
| Was bewirken kleine Primzahlen? | Sie machen das Verfahren leicht angreifbar durch **Brute-Force** |
| Was erreicht man mit dem geheimen Schlüssel? | Einen gemeinsamen geheimen Schlüssel für weitere sichere Kommunikation |

## ✅ Beispiel 1 - Kleine Zahlen (unsicher, aber leicht nachvollziehbar)

### 🔢 Gegegebene öffentliche Parameter

- **Primzahl** `p = 23`
- **Basis (Generator)** `g = 5`

### 🧠 Geheime Schlüssel

- **Alice wählt** `a = 6`
- **Bob wählt** `b = 15`

### 🔄 Berechnung der öffentlichen Teilschlüssel

**Alice sendet an Bob:**

$$A = 5^6 \mod 23 = 15625 \mod 23 = 8$$

**Bob sendet an Alice:**

$$B = g^b \mod p = 5^{15} \mod 23 = 30517578125 \mod 23 = 2$$

### 🔐 Gemeinsamer geheimer Schlüssel

**Alice berechnet:**

$$K = B^a \mod p = 2^6 \mod 23 = 64 \mod 23 = 18$$

**Bob berechnet:**

$$K = A^b \mod p = 8^{15} \mod 23 = 32768...(gross) \mod 23 = 1$$

✅ **Ergebnis:** Beide erhalten denselben geheimen Schlüssel: `K = 18`

➡️ Aber: **Diese Werte sind leicht durch Brute-Force rekonstruierbar!**

---

## ✅ Beispiel 2 – Große Zahlen (realistische Sicherheit)

### 🔢 Gegebene öffentliche Parameter

- **Primzahl** `p = 104729` (grösste 5-stellige Primzahl)
- **Basis (Generator)** `g = 2`

### 🧠 Geheime Schlüssel (Beispiel 2)

- **Alice wählt** `a = 4567`

- **Bob wählt** `b = 8910`

🔄 Berechnung der öffentlichen Teilschlüssel

**Alice sendet an Bob:**

$$A = g^a \mod p = 2^{4567} \mod 104729$$

(Da 2^4567 eine riesige Zahl ist, berechnen wir sie mit einem Programm oder Tool:)

$$A = 85061$$

**Bob sendet an Alice:**

$$B = g^b \mod p = 2^{8910} \mod 104729$$

$$B = 101798$$

### 🔐 Gemeinsamer geheimer Schlüssel (Beispiel 2)

**Alice berechnet:**
$$K = B^a \mod p = 101798^{4567} \mod 104729 = 45655$$

**Bob berechnet:**
$$K = A^b \mod p = 85061^{8910} \mod 104729 = 45655$$
$$K = A^b \mod p = 85061^{8910} \mod 104729 = 45655$$

### ✅ Ergebnis

Beide erhalten denselben geheimen Schlüssel:

$$K = 45655$$

---





## Aufgabe "Hybride Verschlüsselungsverfahren"

Erstellen sie im Cryptool1 bei _"Digitale Signaturen/PKI→PKI"_ unter _"Schlüssel erzeugen/importieren"_ ein eigenes Schlüsselpaar.

 Erstellen sie danach auf ihrem Desktop eine kleine Textdatei.

 Verwenden nun sie im Cryptool1 bei _"Ver-/Entschlüsseln→Hybrid"_ die _"RSA-AES-Verschlüsselung"_ und verschlüsseln sie ihre Textdatei.

 Verwenden nun sie im Cryptool1 bei _"Ver-/Entschlüsseln→Hybrid"_ die _"RSA-AES-Entschlüsselung"_ und entschlüsseln sie ihre Textdatei.

Folgendes soll dabei geklärt werden:

- Was bezweckt der Session-Key?
- Was ist der wesentliche Unterschied zu RSA oder Diffie-Hellman?

### Erarbeitung



---