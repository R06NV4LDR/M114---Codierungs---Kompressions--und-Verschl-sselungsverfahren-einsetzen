# Bilder codieren

Aufgaben

### dpi ppi

### Farbcodes
RGB:   #000000                        entspricht welcher Farbe? 2. RGB:   #FF0000                        entspricht welcher Farbe? 3. RGB:   #FFFF00                        entspricht welcher Farbe?        4. CMYK:  C:100%  M:0%     Y:0%   K:0%   entspricht welcher Farbe?        5. CMYK:  C:0%    M:100%   Y:100% K:0%   entspricht welcher Farbe?        6. CMYK:  C:0%    M:0%     Y:0%   K:100% entspricht welcher Farbe?        7. YCBCR: Y:0     CB:0     CR:0          entspricht welchem RGB-HEX -Wert? 8. YCBCR: Y:1     CB:0     CR:0          entspricht welchem RGB-HEX -Wert? 9. YCBCR: Y:0.3   CB:-0.17 CR:0.5        entspricht welchem RGB-HEX -Wert? 10.RGB:   #FF0000                        entspricht welchem Luminanzwert?Vom Farbbild zum Schwarz/Weiss-Bild


### Filmformate

1. Berechnen sie für beide Formate den Speicherbedarf  für ein einziges Bild, wenn jedes RGB-Pixel 3 Byte benötigt.
    $$
    1920 * 1080 * 3 = 6,220,800 \text{ Byte} \quad \text{(HD1080p50)}
    $$

    $$
    720 * 1280 * 3 = 2,764,800 \text{ Byte} \quad \text{(HD720p50)}
    $$

2. Berechnen sie für beide Formate den Speicherbedarf  für einen 90 minütigen Videofilm bei 50 Bilder/sec.

    $$
    1080 * 720 * 3 * 50 * 60 * 90 = 1,679,616,000,000 \text{ Byte} \quad \text{(HD1080p50)}
    $$

    $$
    720 * 1280 * 3 * 50 * 60 * 90 = 746,496,000,000 \text{ Byte} \quad \text{(HD720p50)}
    $$

3. Vergleichen und erklären sie die beiden Resultate aus Aufgabe 1 und 2.

    **Antwort:**
    _Die Ergebnisse aus Aufgabe 1 und 2 zeigen, dass der Speicherbedarf für ein einzelnes Bild bei HD1080p50 (6,220,800 Byte) höher ist als der für HD720p50 (2,764,800 Byte). Dies liegt daran, dass HD1080p50 eine höhere Auflösung hat und somit mehr Pixel pro Bild enthält._

4. Berechnen sie für beide Formate die Anzahl erforderlichen BluRay-Disks. Ein BluRay-Disk kann bei doppelseitiger Bespielung und Nutzung aller vier Layer maximal 100GB aufnehmen.

    $$
    \frac{1,679,616,000,000 \text{ Byte}}{107,374,182,400 \text{ Byte}} = 15.65 \text{ Disks} \quad \text{(HD1080p50)}
    $$

    $$
    \frac{746,496,000,000 \text{ Byte}}{107,374,182,400 \text{ GB}} = 6.95 \text{ Disks} \quad \text{(HD720p50)}
    $$
5. Berechnen sie für beide Formate die Datenrate in MBit/sec., die ihr Internetanschluss leisten müsste, um die Videos in Echtzeit von einem Videoserver zu streamen.
    **1 Byte = 8 Bit**

    $$
    \frac{1,679,616,000,000 \text{ Byte}}{90 \text{ min} * 60 \text{ sec/min} * 8 \text{ Bit/Byte}} = 2,400 \text{ MBit/sec} \quad \text{(HD1080p50)}
    $$

    $$
    \frac{746,496,000,000 \text{ Byte}}{90 \text{ min} * 60 \text{ sec/min} * 8 \text{ Bit/Byte}} = 2,400 \text{ MBit/sec} \quad \text{(HD720p50)}
    $$

6. Gehen wir davon aus, unser Internetanschluss bietet netto 1GBit/sec. Download-Geschwindigkeit. Wie lange würde es dauern, bis der "HD720p50"-Film bzw. der "HD1080p50"-Film komplett vom Videoserver geladen wäre?

    $$
    \frac{1,296,000,000 \text{ Byte}}{1,000 \text{ MBit/sec} * 125 \text{ MB/MBit}} = 10.368 \text{ sec} \quad \text{(HD1080p50)}
    $$

    $$
    \frac{1,296,000,000 \text{ Byte}}{1,000 \text{ MBit/sec} * 125 \text{ MB/MBit}} = 10.368 \text{ sec} \quad \text{(HD720p50)}
    $$

7. Vergleichen sie die soeben gemachten Berechnungen mit ihrer Erfahrung von zuhause. Hat es tatsächlich so lange gedauert, als sie neulich einen Spielfilm bei Netflix oder AppleStore heruntergeladen hatten? Bitte eine Erklärung.
