# Guida all'uso del Gravimetro phyphox

## Cos'è questo esperimento

Il Gravimetro misura l'accelerazione di gravità **g** nel punto in cui ti trovi, usando due sensori dello smartphone:

- l'**accelerometro** per misurare la componente verticale dell'accelerazione
- il **GPS** per ricavare latitudine e altezza, da cui calcolare il valore teorico atteso di g

Il risultato finale è una misura statistica di g calibrata e centrata sul valore teorico previsto dalla fisica per la tua posizione geografica.

---

## Cosa ti serve

- Uno smartphone con **phyphox** installato (Android o iOS)
- GPS attivo e permesso di localizzazione concesso all'app
- Il telefono posato su una superficie **orizzontale e ferma** durante la misura

---

## Come caricare l'esperimento

Scansiona questo QR code con phyphox (menu → Aggiungi esperimento → Scansiona QR code):

> URL diretto:
> `https://raw.githubusercontent.com/AndreaColonna/Gravimeter/master/Documents/Phyphox/Gravimetro/gravimetro.phyphox`

---

## Procedura passo per passo

### 1. Posiziona il telefono
Appoggia lo smartphone su una superficie piana e orizzontale, con lo schermo rivolto verso l'alto. Non toccarlo durante la misura.

### 2. Avvia l'esperimento
Premi il tasto **Play** (▶) in phyphox. L'accelerometro e il GPS iniziano a raccogliere dati simultaneamente.

### 3. Attendi il GPS
Il GPS impiega qualche secondo (a volte qualche minuto) per agganciarsi ai satelliti. Finché la scheda **GPS e calibrazione** non mostra valori di latitudine e altezza, il fattore di calibrazione (bias) non è ancora calcolato.

### 4. Accumula almeno 100 misure
La calibrazione usa la media delle **ultime 100 misure** dell'accelerometro. Aspetta che il contatore nella scheda **Misura statistica g_z** raggiunga almeno 100 prima di leggere i risultati.

### 5. Leggi i risultati
Vai alla scheda **g calibrato** per il risultato finale.

---

## Le quattro schede dell'app

### Scheda 1 — Misura statistica g_z
Mostra i dati grezzi dell'accelerometro, non ancora calibrati.

| Campo | Significato |
|---|---|
| g_z istantaneo | Valore corrente dell'accelerometro (m/s²) |
| Media (tutte le misure) | Media su tutto il campione raccolto |
| Dev. standard | Dispersione statistica delle misure |
| Conteggio totale | Numero totale di misure acquisite |
| Media (ultime 100 misure) | Media usata per calcolare il bias di calibrazione |
| Dev. standard (100) | Dispersione delle ultime 100 misure |
| Conteggio (100) | Quante misure sono entrate nella finestra (max 100) |

L'istogramma mostra la distribuzione delle misure con la curva gaussiana sovrapposta. Regola **Ampiezza bin** per rendere l'istogramma più o meno dettagliato (default 0.01 m/s²).

---

### Scheda 2 — GPS e calibrazione
Mostra i dati GPS e il calcolo del valore teorico di g.

| Campo | Significato |
|---|---|
| Latitudine | Latitudine geografica in gradi |
| Altezza WGS84 | Altezza sul geoide WGS84 in metri |
| Incertezza altezza | Precisione verticale del GPS (m) |
| g teorico (Somigliana) | Valore atteso di g calcolato dalla formula |
| Incertezza g teorico | Errore su g dovuto all'incertezza dell'altezza GPS |
| Fattore di normalizzazione (bias) | Rapporto g_teorico / media_100 |

Il **bias** è il cuore della calibrazione: se l'accelerometro fosse perfetto varrebbe esattamente 1. Valori tipici sono compresi tra 0.99 e 1.01.

#### Formula usata per g teorico
La formula di Somigliana con correzione altimetrica (WGS84):

```
g_t = 9.7803184 × (1 + 0.0053024 × sin²L − 0.0000059 × sin²2L) − 3.086×10⁻⁶ × h
```

dove **L** è la latitudine in gradi e **h** è l'altezza in metri.

---

### Scheda 3 — g calibrato
È il risultato finale dell'esperimento.

| Campo | Significato |
|---|---|
| g_z calibrato istantaneo | Valore corrente dopo applicazione del bias |
| Media g calibrato | Stima statistica di g nella tua posizione |
| Dev. standard calibrato | Incertezza statistica della misura |
| Conteggio calibrato | Numero di misure calibrate |

La **media g calibrato** è la tua misura di g. Confrontala con il valore tabulato nella scheda 4.

L'istogramma calibrato dovrebbe mostrare una gaussiana centrata sul valore teorico. Regola **Ampiezza bin calibrato** se necessario.

---

### Scheda 4 — Valore tabulato
Permette di inserire un valore di riferimento (es. da INGV o da misure gravimetriche assolute con strumento FG5) per confronto.

| Campo | Significato |
|---|---|
| Latitudine riferimento | Latitudine del punto di misura di riferimento |
| Altezza media | Altezza del punto di riferimento |
| g INGV/FG5 | Valore tabulato di g (m/s²) |
| Incertezza g INGV | Incertezza del valore tabulato (m/s²) |

I valori di default sono preimpostati per un sito di riferimento italiano (latitudine ~45.89°, altezza ~220 m, g ≈ 9.8066 m/s²). Modificali con i dati del tuo sito se disponibili.

---

## Come interpretare i risultati

- La **media g calibrato** dovrebbe coincidere con **g teorico** entro la deviazione standard
- Una deviazione standard piccola (< 0.01 m/s²) indica misure stabili e un telefono ben fermo
- Se il bias è molto lontano da 1 (es. > 1.05 o < 0.95), l'accelerometro del tuo dispositivo ha un errore sistematico significativo
- Più misure accumuli, più la media converge al valore vero (legge dei grandi numeri)

---

## Esportare i dati

Dal menu di phyphox (tre puntini in alto a destra) → **Esporta dati**. Sono disponibili quattro set:

- **Dati grezzi** — serie temporale di g_z grezzo e calibrato
- **Statistiche grezze** — medie, deviazioni standard, istogramma grezzo
- **Dati GPS e calibrazione** — latitudine, altezza, g teorico, bias
- **Statistiche calibrate** — medie e istogramma del segnale calibrato

---

## Consigli pratici

- Esegui la misura al chiuso o in un luogo con buona ricezione GPS
- Aspetta che l'incertezza altezza GPS scenda sotto i 10 m prima di fidarti del bias
- Evita vibrazioni: passi, traffico, ventilatori nelle vicinanze peggiorano la deviazione standard
- Una sessione di 5-10 minuti (circa 500-1000 misure) dà risultati molto stabili
- Se riavvii la misura, il bias viene ricalcolato automaticamente sulle nuove 100 misure
