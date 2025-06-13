# JPG-Komprimierung mit DCT

## WWie funktioniert DCT in JPG?
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