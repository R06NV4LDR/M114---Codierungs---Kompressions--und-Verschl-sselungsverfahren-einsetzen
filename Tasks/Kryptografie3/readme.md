# Kryptografie 3

## Auftrag A "GPG4WIN/Kleopatra ein Schlüsselpaar erstellen"   Dauer: 8 Min

1. GPG4WIN auf dem Notebook installieren [GPG4Win](https://www.gpg4win.de/)

2. Starten des gpg4win-Zertifikatsmanagers Kleopatra und Erzeugen eines persönlichen Schlüsselpaars unter Datei/Neues OpenPGP-Schlüsselpaar...(Hinweis: Alternativ wäre auch ein X.509-Schlüsselpaar denkbar. Dazu müsste man aber eine Beglaubigungsstelle einbeziehen, was den Rahmen dieser Übung sprengen würde.) Beim Erzeugen eines Schlüsselpaars wird eine sogenannte Passphrase verlangt. Dies ist ein Passwort, dass man später beim Erstellen und Öffnen einer verschlüsselten Nachricht eingeben muss. Diese Passphrase darf man
darum keinesfalls vergessen und niemals weitergeben.
3. Exportieren des eigenen öffentlichen Schlüssels. Achtung: Hier den PublicKey und nicht den PrivateKey exportieren! Im Zweifelsfall mit einem Texteditor der Wahl das ASC-File überprüfen! (In der ersten Zeile sollte BEGIN PGP PUBLIC KEY BLOCK stehen.) Der PublicKey sollte etwa so benennt sein: _Vorname_Nachname_PublicKey.asc_
4. Importieren sie in Kleopatra die öffentlichen Schlüssel ihrer Kommunikationspartner.

(Hinweis zu den Schlüsseln: Sowohl öffentliche wie auch geheime Schlüssel können in Kleopatra importiert oder exportiert werden. Beide Schlüssel bahen die Dateiendung .asc. Dies ist ein Hinweis, dass es sich um ASCII-Dateien handelt, die mit einem Texteditor wie z.B. Notepad++ geöffnet werden können. Damit lässt sich zumindest feststellen, ob die betreffende Datei PrivateKey oder PublicKey ist. Welcher Person diese zuzuordnen ist, bleibt innerhalb der Datei allerdings verborgen. Darum empfiehlt es sich, dem Dateinamen Sorge zu tragen, weil er der einzige Hinweis auf den Besitzer ist.)

---

## Auftrag B "GPG4WIN/Kleopatra anwenden"   Dauer: 20 Min

1. **Nachricht verschlüsseln:** Es soll eine Datei (Nachricht als Text, Bild etc.) für ihren Kommunikationspartner verschlüsselt werden. Dies kann direkt in Kleopatra erfolgen. Stellen sie das verschlüsselte File ihrem Kommunikationspartner zur Verfügung. Wenn dieser es entschlüsseln kann, wurde der Auftrag erfolgreich erledigt.

2. **Nachricht signieren:** Nun soll eine Datei für ihren Kommunikationspartner signiert werden. Dies kann ebenfalls wieder direkt in Kleopatra erfolgen. Stellen sie das File inklusive Signatur ihrem Kommunikationspartner zur Verfügung. Wenn dieser mit der Signatur die Echtheit ihres Files verifizieren kann, wurde der Auftrag erfolgreich erledigt.

3. **Nachricht verschlüsseln und signieren:** Diesmal soll eine Datei für ihren Kommunikationspartner verschlüsselt und signiert werden. Wiederum in Kleopatra. Stellen sie das File inklusive Signatur ihrem Kommunikationspartner zur Verfügung. Wenn dieser das File entschlüsseln und dank der Signatur den Absender verifizieren kann, wurde der Auftrag erfolgreich erledigt.
Zusatzfrage: Welchen Mehrwert hat das Verschlüsseln mit zusätzlichem Signieren?

## Auftrag "Den Mailclient Thunderbird installieren und einrichten"  Dauer: 40 Min

1. Installieren sie den eMail-Client "Mozilla Thunderbird". Siehe https://www.thunderbird.net/de/
2. Richten sie ihr eMail-Konto darin ein. Es wird empfohlen, nicht ihr produktiver eMail-Account zu verwenden, sondern ein explizit für Tests eingerichteten.
3. Überprüfen sie ihre Thunderbird-Installation bzw. Konfiguration, indem sie gegenseitig unverschlüsselte eMails austauschen.
4. Nun widmen wir uns der Ende-zu-Ende Verschlüsselung: Erzeugen sie sich ein OpenPGP-Schlüsselpaar. (Hinweis: Ihr OpenPGP-Schlüsselpaar, das sie in Kleopatra kreiert haben, könnte hier auch verwendet werden.)
5. Tauschen sie die PublicKeys gegenseitig aus.
6. Nun geht es an den eMail-Austausch: Schicken sie ihrem Kommunikationspartner/in verschlüsselte und/oder signierte eMails.
7. Zur Kontrolle schicken sie eine verschlüsselte eMail an edu@juergarnold.ch (Hinweis: Den hierfür benötigte PublicKey finden sie hier: https://edu.juergarnold.ch/Thunderbird_PK_ARJ.zip)
8. Erstellen sie eine Kurzanleitung, die ihre Installationsschritte beschreibt und geben sie diese auf Teams/Aufgaben der Lehrperson ab. In ihre Kurzanleitung muss die Thunderbird-Versionsnummer erwähnt sein, auf die sich ihre Arbeitsschritte beziehen.

