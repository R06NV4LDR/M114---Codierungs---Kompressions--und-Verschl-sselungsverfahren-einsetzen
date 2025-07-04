# Cryptography

# Schlüsselanzahl

Berechnung

Allgemein:
$$ S=T * (T-1) / 2 $$

Mit 12 T:
$$ S=12 * (12-1) / 2 $$
$$ S=12 * 11 / 2 $$
$$ S=132 / 2 $$
$$ S=66 $$

## Aufgabe "Diffie-Hellman"

### Grundlagen

Diffie-Hellman ist ein **asymmetrisches Schlüsseltauschverfahren**, bei dem zwei Parteien über eine unsichere Verbindung einen gemeinsamen geheimen Schlüssel erzeugen – ohne ihn jemals direkt auszutauschen.

### Ablauf

1. Öffentliche Parameter:

        Eine Primzahl p

        Eine Basis g (primitive Wurzel mod p)

2. Jeder Teilnehmer wählt ein geheimes Exponent a bzw. b.

3. Es werden Teil-Schlüssel berechnet:

$A = g^a mod p$

$B = g^b mod p$

4. Der gemeinsame geheime Schlüssel lautet:

    $K = B^a mod p = A^b mod p = g^(ab) mod p$

Mathematische Grundlage:
Exponentiation im Restklassenring:
  $g^a \mod p$ und $g^b \mod p$

## Aufgabe "RSA"

Verwenden sie im Cryptool1 bei "Ver-/Entschlüsseln→Asymmetrisch"die "RSA-Demo" um das RSA-Verfahren zu studieren.Experimentieren sie mit verschiedenen Parametern wie•Primzahl p  (Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)•Primzahl q  (Wählen sie auch bewusst kleine Primzahlen im ein oder zweistelligen Bereich)•Öffentlicher Schlüssel e•Eingabe von Nachrichten verschiedener LängenFolgendes soll dabei geklärt werden:•Was bewirkt die Eingabe von kleinen Werten für p, q und e?•Welche mathematische Funktion verwendet RSA? •Was ist der wesentliche Unterschied zu Diffie-Hellman?

## Aufgabe "Hybride Verschlüsselungsverfahren"

Erstellen sie im Cryptool1  bei "Digitale Signaturen/PKI→PKI" unter "Schlüssel erzeugen/importieren" ein eigenes Schlüsselpaar. Erstellen sie danach auf ihrem Desktop eine kleine Textdatei.Verwenden nun sie im Cryptool1 bei "Ver-/Entschlüsseln→Hybrid" die "RSA-AES-Verschlüsselung" und verschlüsseln sie ihre Textdatei.Verwenden nun sie im Cryptool1 bei "Ver-/Entschlüsseln→Hybrid" die " "RSA-AES-Entschlüsselung" und entschlüsseln sie ihre Textdatei.Folgendes soll dabei geklärt werden:•Was bezweckt der Session-Key?•Was ist der wesentliche Unterschied zu RSA oder Diffie-Hellman?

## Aufgabe "Hash-Algorithmus"

Verwenden sie im Cryptool1 unter "Einzelverfahren→Hashverfahren" die "Hash-Demo" um denHash-Algorithmus zu studieren. Experimentieren sie mit verschiedenen Parametern wie•Hashfunktion•Inhalt des aktuellen Dokuments: Tauschen sie beim Originaltextz.B. einen Buchstaben aus oder fügen sie ein Leerzeichen ein.Folgendes soll dabei geklärt werden:•Beobachten sie, wie sich der Hashwert auch bei subtilen Textmodifikationen ändert.•In was unterscheiden sich die verschiedenen Hashfunktionen?•Welche Hashfunktion erfüllt die aktuellen Sicherheitsanforderungen?

## Aufgabe "Digital signieren"
Erstellen sie auf ihrem Desktop eine kurze Textdatei.Verwenden sie im Cryptool1 unter "Digitale Signaturen/PKI" das Tool "Dokument signieren" um ihre Textdatei zu signieren.Verwenden sie im Cryptool1 unter "Digitale Signaturen/PKI" das Tool "Signatur überprüfen" um die Signatur ihrer Textdatei zu überprüfen.Ändern sie in ihrer Textdatei z.B. den ersten Buchstaben.Überprüfen sie im Cryptool1 unter "Digitale Signaturen/PKI" mit "Signatur überprüfen" erneut die Signatur ihrer Textdatei.Was stellen sie fest?

## Aufgabe "Hash-Funktion auf dem Prüfstand"
Wie sicher ist eigentlich die Hash-Funktion? Passt ein Hashwert wirklich nur zu einem einzigen Original?Verwenden sie im Cryptool1 unter "Analyse → Hashverfahren"das Tool "Angriff auf den Hashwert der digitalen Signatur".Text und Hashwert müssen eigentlich ein-eindeutig übereinstimmen.Unsichere, veraltete Hashverfahren können das aber nicht zu 100% garantieren und sind dann ein Problem, wenn es gelingt bei verschiedenen Nachrichten einen übereinstimmenden Hashwert zu finden.Probieren sie das doch gleich mal aus!
