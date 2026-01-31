# WGS-84: World Geodetic System 1984

WGS-84 è il **sistema geodetico di riferimento mondiale** adottato dal Dipartimento della Difesa degli Stati Uniti nel 1984 e tuttora usato da GPS e dalla maggior parte delle carte nautiche/aree globali.

## 1. Cos'è un sistema geodetico?
È un insieme di:
- un **ellissoide di riferimento** (forma e dimensioni della Terra),
- un **datum** (posizione dell'ellissoide rispetto al centro di massa della Terra),
- un sistema di coordinate (latitudine, longitudine, altezza),
- un modello di campo gravitazionale associato.

## 2. Parametri principali di WGS-84
| Grandezza | Simbolo | Valore |
|-----------|---------|--------|
| Semiasse maggiore | *a* | 6 378 137,0 m |
| Semiasse minore | *b* | 6 356 752,314 245 m |
| Schiacciamento | *f* = (a-b)/a | 1 / 298,257 223 563 |
| Costante geocentrica gravitazionale | *GM* | 3,986 004 418 × 10¹⁴ m³ s⁻² |
| Velocità angolare terrestre | *ω* | 7,292 115 × 10⁻⁵ rad s⁻¹ |

## 3. Cosa fornisce WGS-84?
- **Coordinate GPS**: latitudine e longitudine espressi proprio sul suo ellissoide.  
- **Altezza ellisoidica** (*h*): distanza lungo la normale all'ellissoide, non l'altezza sul livello del mare (quella si chiama *altezza ortometrica*).  
- **Modello di gravità normale**: la formula di Somigliana (quella che usi per *g* teor) è parte dello standard WGS-84.  
- **Frame di riferimento terrestre**: il centro dell'ellissoide coincide con il centro di massa della Terra (±2 cm).

## 4. Perché è importante nel tuo esperimento?
- Il GPS del telefono restituisce **latitudine φ** e **altezza ellisoidica *h*** proprio in WGS-84.  
- La formula che usi per calcolare *g* teorico è la **"gravity formula 1984"** del WGS-84: senza quei parametri il confronto con la misura non sarebbe coerente.

## 5. WGS-84 vs altri sistemi
| Sistema | Uso tipico | Differenza rispetto a WGS-84 |
|---------|------------|-----------------------------|
| ETRS89 | Europa | ~0,5–1 m (fissa all'Europa, diverge 2,5 cm/anno) |
| ED50 | Carte nautiche europee storiche | decine di metri |
| ITRFxx | Ricerca geodetica | centimetri, aggiornato ogni anno |

Per un esperimento di fisica liceale queste differenze sono trascurabili; usare WGS-84 è sufficiente e coerente con i dati GPS del telefono.