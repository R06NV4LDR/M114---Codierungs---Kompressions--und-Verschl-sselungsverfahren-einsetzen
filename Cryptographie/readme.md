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
