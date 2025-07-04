# Kryptografie 2

- [Aufgabe "Diffie-Hellman"](##-aufgabe-diffie-hellman)
- [Aufgabe "RSA"](##-aufgabe-rsa)
- [Aufgabe "Hybride Verschlüsselungsverfahren"](##-aufgabe-hybride-verschlüsselungsverfahren)
- [Aufgabe "Hash-Algorithmus"](##-aufgabe-hash-algorithmus)
- [Aufgabe "Digital signieren"](##-aufgabe-digital-signieren)

## 🔐 Aufgabe "Diffie-Hellman"

Verwenden sie im **Cryptool1** unter _"Einzelverfahren→Protokolle"_ die _"Diffie-Hellman-Demo"_, um den Diffie-Hellman-Schlüsseltausch zu studieren. Experimentieren sie mit verschiedenen Parametern wie:

- Bitlänge  
- Primzahlen (Wählen sie auch bewusst kleine Primzahlen im ein- oder zweistelligen Bereich)  
- Geheimnis  

Folgendes soll dabei geklärt werden:

- Wie werden die Teilschlüssel berechnet? (Mathematische Funktion?)  
- Was bewirkt die Wahl von kleinen Primzahlen wie z.B. 7, 11 oder 13?  
- Als Resultat erhalten sie einen "geheimen Schlüssel". Was haben sie damit erreicht?

---

### Erarbeitung

#### ➤ Mathematisches Verfahren zur Berechnung der Teilschlüssel

1. **Öffentliche Parameter:**
   - Eine Primzahl `p`
   - Eine Basis (Generator) `g`, wobei `g < p`

2. **Jede Partei wählt ein geheimes Geheimnis:**
   - Alice wählt ein geheimes `a`
   - Bob wählt ein geheimes `b`

3. **Berechnung der Teilschlüssel (öffentlichen Schlüssel):**
   - Alice berechnet `A = g^a mod p`
   - Bob berechnet `B = g^b mod p`

4. **Austausch dieser Teilschlüssel über einen unsicheren Kanal**

5. **Berechnung des gemeinsamen Schlüssels:**
   - Alice berechnet: `K = B^a mod p`
   - Bob berechnet: `K = A^b mod p`

   Beide erhalten **denselben geheimen Schlüssel** `K`, weil:

   ```lua
   B^a mod p = (g^b)^a mod p = g^(ab) mod p
   A^b mod p = (g^a)^b mod p = g^(ab) mod p

---

## Aufgabe "RSA"

Verwenden sie im Cryptool1 bei _"Ver-/Entschlüsseln→Asymmetrisch"_ die _"RSA-Demo"_ um das RSA-Verfahren zu studieren. Experimentieren sie mit verschiedenen Parametern wie:

- Primzahl p  (Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)
- Primzahl q  (Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)
- Öffentlicher Schlüssel e
- Eingabe von Nachrichten verschiedener Längen

Folgendes soll dabei geklärt werden:

- Was bewirkt die Eingabe von kleinen Werten für p, q und e?
- Welche mathematische Funktion verwendet RSA?
- Was ist der wesentliche Unterschied zu Diffie-Hellman?

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

blabla

---

## Aufgabe "Hash-Algorithmus"

Verwenden sie im Cryptool1 unter _"Einzelverfahren→Hashverfahren"_ die _"Hash-Demo"_ um den Hash-Algorithmus zu studieren. Experimentieren sie mit verschiedenen Parametern wie

- Hashfunktion
- Inhalt des aktuellen Dokuments: Tauschen sie beim Originaltext z.B. einen Buchstaben aus oder fügen sie ein Leerzeichen ein.

Folgendes soll dabei geklärt werden:

- Beobachten sie, wie sich der Hashwert auch bei subtilen Textmodifikationen ändert.
- In was unterscheiden sich die verschiedenen Hashfunktionen?
- Welche Hashfunktion erfüllt die aktuellen Sicherheitsanforderungen?

---

## Aufgabe "Digital signieren"

Erstellen sie auf ihrem Desktop eine kurze Textdatei.

Verwenden sie im Cryptool1 unter _"Digitale Signaturen/PKI"_ das Tool _"Dokument signieren"_ um ihre Textdatei zu signieren.

Verwenden sie im Cryptool1 unter _"Digitale Signaturen/PKI"_ das Tool _"Signatur überprüfen"_ um die Signatur ihrer Textdatei zu überprüfen.

Ändern sie in ihrer Textdatei z.B. den ersten Buchstaben.

Überprüfen sie im Cryptool1 unter _"Digitale Signaturen/PKI"_ mit _"Signatur überprüfen"_ erneut die Signatur ihrer Textdatei.

Was stellen sie fest?

### Erarbeitung

---

## Aufgabe "Hash-Funktion auf dem Prüfstand"

Wie sicher ist eigentlich die Hash-Funktion? Passt ein Hashwert wirklich nur zu einem einzigen Original?

 Verwenden sie im Cryptool1 unter _"Analyse → Hashverfahren"_ das Tool _"Angriff auf den Hashwert der digitalen Signatur"_
 
  Text und Hashwert müssen eigentlich ein-eindeutig übereinstimmen. Unsichere, veraltete Hashverfahren können das aber nicht zu 100% garantieren und sind dann ein Problem, wenn es gelingt bei verschiedenen Nachrichten einen übereinstimmenden Hashwert zu finden. 
  
  Probieren sie das doch gleich mal aus!
