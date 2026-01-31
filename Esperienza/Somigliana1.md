### Come si ottiene la formula di g(φ, h)

La formula che usiamo per la calibrazione GPS

$$
g_{\text{teor}} = 9{,}780\,318\,4 \cdot \bigl(1 + 0{,}005\,302\,4 \sin^2φ - 0{,}000\,005\,9 \sin^2 2φ\bigr) - 0{,}000\,003\,086 \cdot h
$$

**non** si ricava direttamente dalla sola legge di gravitazione di Newton  
$F = G M / r²$, perché quest'ultima vale per un corpo sferico **non rotante**.

Per ottenere la dipendenza da [**latitudine**](FattoreLatitudine.md) e **altezza** con strumenti di livello liceale dobbiamo aggiungere tre ingredienti elementari, sempre dentro la meccanica newtoniana.

---

1. **Forza di gravità vera** (Newton)  
   su una massa m alla distanza $r = R_T + h$

   $$
   F_{\text{grav}} = G \frac{M_T m}{r^2} \approx m g_0 \Bigl(1 - 2 \frac{h}{R_T}\Bigr)
   \qquad \text{con} \quad g_0 = \frac{G M_T}{R_T^2}
   $$

   (sviluppo al prim'ordine per $h ≪ R_T$)

2. **Forza centrifuga** (motivata da Galilei, formalizzata da Newton stesso)  
   Il punto solidale con la Terra compie un moto circolare uniforme di raggio

   $$
   r_\perp = (R_T + h) \cos φ
   $$

   con velocità angolare $ω = 2π / T$ (T = 86164 s, giorno siderale).  
   La forza centrifuga agente su m è

   $$
   F_{\text{cf}} = m \omega^2 r_\perp = m \omega^2 (R_T + h) \cos φ
   $$ 

   diretta **perpendicolamente all'asse di rotazione**.

3. **Composizione vettoriale semplificata**  
   L'accelerometro misura la **risultante** fra gravità e centrifuga, proiettata lungo la verticale locale (direzione del filo a piombo).  
   Basta decomporre $F_{cf}$ lungo la verticale e radiale:

   - componente **verticale**: $−F_{cf} \cdot cos φ$  
   - componente **orizzontale**: $−F_{cf}\cdot  sin φ$ (non contribuisce a g misurata)

   Quindi l'accelerazione **efficace** percepita è

   $$
   g(\varphi, h) = \frac{G M_T}{(R_T + h)^2} - \omega^2 (R_T + h) \cos^2 φ
   $$

   Sostituendo i valori noti ($G, M_T, R_T, ω$) e sviluppando al prim'ordine in h si ottiene

   $$
   g(\varphi, h) \approx g_{\text{eq}} \Bigl[1 + \Bigl(\frac{5}{2} \frac{\omega^2 R_T}{g_{\text{eq}}}\Bigr) \sin^2 φ \Bigr] - 2 \frac{g_{\text{eq}}}{R_T} h
   $$

   dove $g_{eq}$ è il valore all'equatore ($φ = 0$, $h = 0$).

4. **Aggiustamento empirico**  
   Il coefficiente teorico $5/2 · ω²R_T/g_{eq} ≈ 0,00346$ è **inferiore** a quello misurato (0,00530) perché la Terra **non** è una sfera omogenea: è schiacciata ai poli (ellitticità f ≈ 1/298).  
   L'ellitticità aumenta ulteriormente la variazione con φ; i geodeti calibrano quindi i coefficienti su misure di pendolo e gravimetri in **molti punti della Terra**.  
   Il termine in sin²2φ tiene conto delle **asimmetrie di massa** di ordine superiore.

5. **Forma finale "scuola"**  
   Raccogliendo i coefficienti numerici si arriva alla formula di **Somigliana (1929)** riportata nel file:

   $$
   g_{\text{teor}} = 9{,}780\,318\,4 \cdot \bigl(1 + 0{,}005\,302\,4 \sin^2φ - 0{,}000\,005\,9 \sin^2 2φ\bigr) - 0{,}000\,003\,086 \cdot h
   $$

   - Il primo addendo è la **forma di Clairaut** (gravità su ellissoide rotante).  
   - Il coefficiente −0,000 003 086 m/s² per metro di quota è la **gradiente verticale** di g prevista dal punto 1.

---

In sintesi:  
partiamo da **F = G M / r²**, aggiungiamo la **forza centrifuga** (sempre dentro la meccanica newtoniana) e correggiamo i coefficienti con i dati reali della Terra.