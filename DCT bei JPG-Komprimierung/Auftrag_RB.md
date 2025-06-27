
1. **Farbraumumwandlung**
Das Bild wird vom RGB-Farbraum in den YCbCr-Farbraum umgewandelt (Helligkeit + Farbanteile getrennt).
**2. Unterteilung in 8x8-Blöcke**
Jeder Kanal (Y, Cb, Cr) wird in 8x8-Pixel-Blöcke unterteilt.
**3. DCT-Anwendung**
Auf jeden 8x8-Block wird die DCT angewendet, um die Frequenzkomponenten zu extrahieren. Ergebnis: 64 Frequenzkoeffizienten.
**4. Quantisierung**
Kleine (unwichtige) Frequenzanteile werden **stark reduziert oder ganz gestrichen** - das spart Speicherplatz.

**5. Codierung**
Die verbleibenden Werte werden mithilfe von RLC (Run Length Coding) und Huffman-Codierung weiter komprimiert.

## Wie viel Datenreduktion ist möglich?
- **Typisch:** Reduktion um 90% oder mehr möglich
- **Beispiel:** Ein 3 MB-Bild kann auf 300 KB oder weniger reduziert werden
- **Effizienz:** Besonders bei Fotos mit grossen, gleichmässigen Flächen


# 📸 JPG-Komprimierung mit DCT


## 🧠 Wie funktioniert DCT in JPG?

**1. Farbraumumwandlung**
    Das Bild wird vom RGB-Farbraum in den YCbCr-Farbraum umgewandelt:

    - Y: Helligkeit (Luminanz)

    - Cb, Cr: Farbinformationen (Chrominanz)

**2. Unterteilung in 8x8-Blöcke**
    Jeder Kanal (Y, Cb, Cr) wird in 8×8 Pixel große Blöcke unterteilt. Jeder Block wird einzeln verarbeitet.

**3. DCT-Anwendung**
    Auf jeden Block wird die Diskrete Kosinustransformation (DCT) angewendet.
    Dadurch wird das Bild vom Ortsraum in den Frequenzraum übertragen:

        Oben links im Block: niedrige Frequenzen (wichtige Bildinformationen)

        Unten rechts: hohe Frequenzen (feine Details, weniger wichtig)
        → Ergebnis: 64 DCT-Koeffizienten pro Block

**4. Quantisierung**
    Die DCT-Werte werden gerundet (je nach visuellem Einfluss).

        Hohe Frequenzen (kleine Details) werden stärker reduziert oder gestrichen

        Führt zur Datenreduktion, aber auch zu Informationsverlust

    Codierung
    Die quantisierten Werte werden mit Run Length Encoding (RLE) und Huffman-Codierung komprimiert.

📉 Wie viel Datenreduktion ist möglich?

    Typisch: Reduktion um 90 % oder mehr

    Beispiel: Ein 3 MB-Foto kann auf ca. 300 KB schrumpfen

    Effizient bei: Fotos mit großen, gleichmäßigen Farbflächen

    Durch Kombination aus DCT, Quantisierung und Entropiekodierung

⚠️ Nachteile bei starker Kompression

    Blocking-Artefakte
    Sichtbare Grenzen zwischen den 8×8-Blöcken, vor allem in glatten Flächen oder bei starkem Zoom
    → entsteht durch zu starke Quantisierung oder fehlende Übergangsbereiche

    Detailverlust
    Feine Strukturen (z. B. Haare, Texturen) gehen verloren

    Farbliche Unschärfen
    Besonders bei Chroma Subsampling (z. B. 4:2:0), da Farbinformationen stärker komprimiert werden

Beispiel für Blocking-Artefakte

(Quelle: Wikipedia – JPEG-Komprimierungsartefakte)
Beispiel: JPEG-Artefakte
🎥 Bonus: Chroma Subsampling

Das menschliche Auge ist empfindlicher für Helligkeit als für Farbe.
Daher werden Farbkanäle reduziert (z. B. 4:2:0 statt 4:4:4) – das spart Speicherplatz bei kaum sichtbarem Qualitätsverlust.

YouTube-Empfehlung:
🔗 Chroma Subsampling erklärt (YT)
**✅ Fazit**

Die DCT ist das Herzstück der verlustbehafteten JPG-Komprimierung.
Sie erlaubt durch mathematische Umwandlung und gezielte Datenreduktion eine massive Verkleinerung von Bilddateien.
Doch zu hohe Kompression kann sichtbare Qualitätsverluste verursachen – ein guter Kompromiss zwischen Größe und Qualität ist entscheidend.
