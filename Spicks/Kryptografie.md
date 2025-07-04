# Spick Prüfung 3 - Kryptografie

## Symmetrische Verschlüsselung

1. Was versteht man unter einer symmetrischen Verschlüsselung?
Symmetrische Verschlüsselung bedeutet, dass Sender und Empfänger denselben Schlüssel für das Ver- und Entschlüsseln verwenden.
Beispiele klassisch: ROT (Caesar), Vigenère, XOR
Modern: AES

2. ROT13-Aufgabe: „KRYPTO“ verschlüsseln
ROT13 bedeutet, jeden Buchstaben um 13 Stellen zu verschieben:
K → X, R → E, Y → L, P → C, T → G, O → B
Lösung: "XELCGB"

3. Vigenère: „BEEF“ mit „AFFE“
Vigenère:
B + A = B
E + F = J
E + F = J
F + E = J
Lösung: "BJJJ"

4. XOR von 4711 und 10001101
4711 dezimal = 0001 0010 0110 0111 binär
Schlüssel: 10001101
Wiederholen, um 16 Bit zu erreichen: 10001101 10001101
XOR:
0001001001100111
1000110110001101
= 1001111111101010 (binär)
= 40970 (dezimal)

5. Schlüsselanzahl bei 20 Teilnehmern
Formel: S = n × (n–1) / 2
S = 20 × 19 / 2 = 190 Schlüssel
Asymmetrische Verschlüsselung

6. Hauptvorteil asymmetrische Verschlüsselung:
Es muss kein geheimer Schlüssel über einen sicheren Kanal verteilt werden – der öffentliche Schlüssel kann offen verteilt werden

7. Diffie-Hellman:

    Kleine Primzahlen machen das Verfahren unsicher, da Angreifer den geheimen Schlüssel leicht berechnen können.

    Mathematische Funktion: Potenzieren und Modulo-Operationen (a^b mod p)

8. RSA und Primzahlen:

    Kleine Primzahlen machen RSA angreifbar (leicht faktorisierbar).

    Große Primzahlen sind notwendig, weil die Sicherheit auf der Faktorisierung großer Zahlen basiert.

## Hybride Verfahren & Praxis

9. Hybrides Verfahren:
    Kombiniert symmetrische (z.B. AES) und asymmetrische (z.B. RSA) Verschlüsselung.
    Der Session-Key ist ein zufälliger symmetrischer Schlüssel, der für die eigentliche Nachricht verwendet und dann asymmetrisch gesichert wird.
    Unterschied zu RSA/Diffie-Hellman: Höhere Effizienz, da symmetrisch schneller verschlüsselt wird, aber mit dem Komfort des sicheren Schlüsseltauschs.

10. Gpg4win/Kleopatra Datei signieren:

    Mit Kleopatra ein Schlüsselpaar erstellen

    Datei auswählen und auf „Signieren“ klicken

    Signierte Datei dem Empfänger senden

    Empfänger prüft die Signatur mit dem öffentlichen Schlüssel des Absenders

## Digitale Signatur und Hashes

11. Was ist eine digitale Signatur?
Eine digitale Signatur ist ein mit privatem Schlüssel erzeugter Wert, der die Authentizität, Integrität und Verbindlichkeit einer Nachricht gewährleistet.
Szenarien: Vertragsabschlüsse, Software-Updates

12. Hashfunktion – Avalanche-Effekt:
Bei einer guten Hashfunktion führt jede kleine Änderung im Input (Text) zu einem komplett anderen Hashwert. Das verhindert gezielte Manipulation und Kollisionen.

13. Hash-Angriff mit MD2/16Bit:
Bei schwachen/veralteten Hashfunktionen können zwei verschiedene Nachrichten denselben Hashwert haben (Kollision). So könnte ein Angreifer ein gültig signiertes, aber manipuliertes Dokument erzeugen.

## Public Key Infrastruktur (PKI) & Zertifikate

14. Unterschied PKI vs. Web-of-Trust:

    PKI: Hierarchisch mit zentraler Zertifizierungsstelle (z.B. X.509/CA)

    Web-of-Trust: Dezentral, Nutzer bestätigen sich gegenseitig (z.B. OpenPGP)

15. Zertifikatsvalidierung:

    Domain Validated (nur Domainkontrolle)

    Organization Validated (Domain + Firmenname bestätigt)

    Extended Validation (umfassende Identitätsprüfung)

16. TLS/HTTPS-Handshake (vereinfacht):

    Browser verbindet sich mit dem Server, fordert Zertifikat an

    Server schickt sein Zertifikat

    Browser prüft das Zertifikat (gültig? von vertrauenswürdiger CA?)

    Schlüsselaustausch erfolgt, Kommunikation ist danach verschlüsselt

## E-Mail-Verschlüsselung

17. Unterschied OpenPGP und S/MIME:

    OpenPGP: Dezentral, Web-of-Trust, OpenSource

    S/MIME: Hierarchisch, benötigt Zertifikate von CAs, meist in Firmenumgebungen
    Wann was?
    OpenPGP privat/offen, S/MIME für Unternehmen oder Behörden

18. Thunderbird: Verschlüsselt und signiert mailen:

    OpenPGP-Schlüsselpaar erzeugen

    Öffentliche Schlüssel austauschen

    Beim Schreiben der E-Mail „Signieren“ und „Verschlüsseln“ auswählen

    Senden

    Empfänger kann entschlüsseln und Signatur prüfen, wenn Schlüssel vorhanden