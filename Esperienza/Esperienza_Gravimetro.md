# Misura dell'accelerazione di gravità con smartphone e calibrazione GPS
**Classe 3° Liceo Scientifico – Anno scolastico 2024/25**  
**GRUPPO:** ____________________  
**Alunno/i:** ____________________  
**Data:** ____________________

## 1. Obiettivi
- Determinare sperimentalmente il valore locale dell’accelerazione di gravità **g** utilizzando l’accelerometro di uno smartphone.  
- Correggere l’errore sistematico del sensore applicando la [formula](Somigliana.md) di [Somigliana](Somigliana1.md) con i valori di [WGS-84](WGS.md) **g(φ, h)**.  
- Costruire l’istogramma dei dati calibrati, stimare **g** e la deviazione standard.  
- Trovare l'errore e confrontare il risultato con il valore teorico attraverso il valore di bias.
- Calcolare [l’incertezza](incertezzatipoA.md) del risultato. 
- Controllare se compatibile con il valore sperimentale dato da misure FG5-238 dato da [BGI del luogo](BGI_Rovereto.md) 

## 2. Materiale e strumenti
- Smartphone con accelerometro e GPS attivo  
- App **phyphox** (versione 1.19 o successiva)  
- File esperimento **Gravimetro.phyphox**  
- Superficie orizzontale stabile (preferibilmente antivibrazioni)

## 3. Richiamo teorico
Il valore teorico dell’accelerazione di gravità, utilizzando il modello di Somigliana, dipende dalla latitudine φ e dall’altezza h (in metri sul geoide WGS84):

$$
g_{\text{teor}} = 9{,}780\,318\,4 \left(1 + 0{,}005\,302\,4 \sin^2 \varphi - 0{,}000\,005\,9 \sin^2 2\varphi \right) - 0{,}000\,003\,086 \cdot h
$$

L’accelerometro fornisce un valore grezzo $g_{z,\text{grezzo}}$ affetto da errore sistematico (bias e fattore di scala).  
Il **bias moltiplicativo** è definito come:

$$
\text{bias} = \frac{g_{\text{teor}}}{\overline{g}_{z,\text{grezzo}}}
$$

e il valore calibrato:

$$
g_{z,\text{cal}} = g_{z,\text{grezzo}} \cdot \text{bias}
$$

## 4. Procedura sperimentale
1. Appoggiare lo smartphone fermo su una superficie orizzontale stabile.  
2. Aprire **phyphox** e caricare l’esperimento **Gravimetro.phyphox**.
![AppGravimetro](Gravimetro.png)  
3. Avviare la misura, premere **Correzione GPS** e attendere la stabilizzazione dei valori di φ e h.  
4. Registrare almeno 30 s di dati (≈ 14 000 campioni a ~467 Hz).  
5. Annotare la media grezza, la deviazione standard e calcolare l’incertezza tipo:

$$
u_A = \frac{s}{\sqrt{N}}
$$

6. Calcolare **g<sub>teor</sub>** con la formula del punto 3.  
7. Applicare il bias moltiplicativo e ottenere i dati calibrati.  
8. Costruire l’istogramma dei dati calibrati (larghezza bin = 0,01 m/s²).

## 5. Dati sperimentali
| Grandezza                  | Simbolo                  | Valore          | Unità   |
|--------------------------------|--------------------------|-----------------|---------|
| Latitudine (GPS)               | φ                        | ___________     | °       |
| Altezza (GPS)                  | h                        | ___________     | m       |
| Numero di campioni             | N                        | ___________     | —       |
| Media grezza                   | $\overline{g}_{z,\text{grezzo}}$ | ___________     | m/s²    |
| Deviazione standard grezza     | $s_{\text{grezzo}}$      | ___________     | m/s²    |
| g teorico (formula)            | $g_{\text{teor}}$        | ___________     | m/s²    |
| g tabulare Rovereto (IGSN71)   | $g_{\text{Rovereto}}$    | 9,80614320      | m/s²    |
| Bias moltiplicativo            | bias                     | ___________     | —       |
| Media calibrata                | $\overline{g}_{z,\text{cal}}$    | ___________     | m/s²    |
| Deviazione standard calibrata  | $s_{\text{cal}}$         | ___________     | m/s²    |
| Incertezza tipo (A)            | $u_A$                    | ___________     | m/s²    |

## 6. Risultati
Valore finale della misura (esempio tipico ottenuto):

$$
g = (9{,}8061 \pm 0{,}0005)~\text{m/s}^2 \quad (k=1)
$$

Scarto percentuale rispetto al valore teorico:

$$
E\% = \left| \frac{\overline{g}_{z,\text{cal}} - g_{\text{teor}}}{g_{\text{teor}}} \right| \cdot 100 = \underline{\hspace{3cm}}~\%
$$

## 7. Osservazioni e commenti
- L’istogramma dei dati calibrati appare gaussiano e centrato sul valore teorico.  
- L’incertezza è dominata dal rumore del sensore (deviazione standard ≈ $\underline{\hspace{1cm}}$ m/s²).  
- Il bias moltiplicativo ha corretto uno scarto sistematico tipico di −1÷−2 %.

## 8. Domande di verifica

1. **Perché il valore grezzo è sistematicamente inferiore al teorico?**  
   Gli accelerometri MEMS presentano un offset di zero e un fattore di scala leggermente diverso dal valore nominale (tipicamente ±1-2 %). La taratura di fabbrica è ottimizzata per range dinamici ampi (±2 g o ±4 g) e non per misure assolute di precisione metrologica. La calibrazione moltiplicativa corregge efficacemente entrambi gli errori.

2. **Qual è la differenza tra calibrazione additiva e moltiplicativa?**  
   Una correzione additiva rimuove solo l’offset, lasciando invariato l’errore di scala. Una calibrazione moltiplicativa corregge il prodotto “gain × offset”, rendendo il sensore accurato anche in luoghi con valori di g diversi (es. variazioni di altitudine o latitudine).

3. **Calcolare g teorico al livello del mare a latitudine 45° N.**  
   $$
   \sin 45^\circ = \frac{\sqrt{2}}{2} \quad \Rightarrow \quad \sin^2 45^\circ = 0{,}5, \quad \sin^2 90^\circ = 1
   $$
   $$
   g_{\text{teor}} = 9{,}780\,318\,4 \left(1 + 0{,}005\,302\,4 \cdot 0{,}5 - 0{,}000\,005\,9 \cdot 1 \right) = 9{,}780\,318\,4 \times 1{,}002\,645\,3 \approx 9{,}806\,21~\text{m/s}^2
   $$

4. **Qual è la principale fonte di incertezza nella misura?**  
   La deviazione standard del segnale (rumore del sensore), non la risoluzione.  
   $$
   u_A = \frac{s}{\sqrt{N}} \approx \frac{0{,}08}{\sqrt{12000}} \approx 7{,}3 \times 10^{-4}~\text{m/s}^2
   $$
   L’incertezza diminuisce proporzionalmente a $1/\sqrt{N}$.

5. **Come migliorare ulteriormente la precisione?**  
   - Aumentare il tempo di acquisizione (60–120 s).  
   - Effettuare più run indipendenti e mediare i risultati.  
   - Ridurre le vibrazioni meccaniche (tappetino antivibrazioni).  


## 9. Conclusione
L’esperimento ha permesso di misurare **g** con accuratezza relativa migliore dello 0,01 % dopo calibrazione GPS, dimostrando l’efficacia della correzione moltiplicativa per rimuovere gli errori sistematici dell’accelerometro MEMS. Il risultato è in ottimo accordo con il valore teorico e con la misura assoluta di riferimento IGSN71 di Rovereto (9,80614320 m/s²).

## 10. Allegati
- Screenshot istogramma dei dati calibrati e no  
- Screenshot phyphox con valori GPS e statistiche