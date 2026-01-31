# Che cos'è l'incertezza tipo A: \( $u_A = \frac{s}{\sqrt{N}}$ \)

L’**incertezza tipo A** (indicata spesso come \( $u_A$ \)) è una stima dell’incertezza di una misura ottenuta **analizzando statisticamente i dati sperimentali raccolti**, ovvero da una serie di misurazioni ripetute della stessa grandezza.

### Come si calcola
Quando si effettuano **N misurazioni indipendenti** dello stesso valore (es. migliaia di letture dell’accelerometro):

1. Si calcola la **media** \( $\overline{x}$ \) dei valori.
2. Si calcola la **deviazione standard sperimentale** \( s \) della serie:

   $$
   s = \sqrt{\frac{1}{N-1} \sum_{i=1}^{N} (x_i - \overline{x})^2}
   $$

   \( s \) quantifica la **dispersione** (rumore o ripetibilità) delle singole misure intorno alla media.

3. L’**incertezza tipo A** sulla **media** è:

   $$
   u_A = \frac{s}{\sqrt{N}}
   $$

   Questa è anche chiamata **errore standard della media** (standard error of the mean).

### Perché si divide per \( $\sqrt{N} $\)?
- Ogni singola misura ha un’incertezza casuale approssimativamente pari a \( s \).
- Quando si calcola la **media di N misure indipendenti**, gli errori casuali tendono a compensarsi parzialmente.
- L’incertezza sulla media **diminuisce** proporzionalmente a \( $1/\sqrt{N}$ \): più dati si raccolgono, più la stima della media diventa precisa.

### Esempio pratico (esperimento con phyphox)
- Numero di campioni: \( N = 12000 \)
- Deviazione standard: \( $s \approx 0{,}08 \, \text{m/s}^2$ \) (tipico rumore MEMS)
- Incertezza tipo A:

  $$
  u_A = \frac{0{,}08}{\sqrt{12000}} \approx \frac{0{,}08}{109{,}54} \approx 7{,}3 \times 10^{-4} \, \text{m/s}^2 \approx 0{,}00073 \, \text{m/s}^2
  $$

  La media \( $\overline{g}$ \) ha quindi un’incertezza casuale di circa **0,0007 m/s²**, corrispondente a una precisione relativa di circa **0,007 %** — eccellente per uno smartphone!

### Classificazione secondo il GUM  
*(Guide to the Expression of Uncertainty in Measurement)*

- **Tipo A**: valutata con metodi statistici dai dati sperimentali (\( $s/\sqrt{N}$ \)).
- **Tipo B**: valutata con altri metodi (specifiche del costruttore, risoluzione, calibrazioni, ecc.).

Nell’esperimento di misura di g con phyphox, l’incertezza tipo A è solitamente la componente dominante, perché il rumore del sensore è molto maggiore della risoluzione dello strumento.

### In sintesi
\( $u_A = \frac{s}{\sqrt{N}}$ \) rappresenta l’**incertezza casuale sulla media** dovuta alla dispersione dei dati.  
Raccogliere un gran numero di campioni (come le decine di migliaia fornite da phyphox) è fondamentale per ridurre drasticamente questa incertezza e ottenere una stima molto precisa di g.