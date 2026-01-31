### Spiegazione della formula  
$$ g(\varphi) \approx g_e \left[1 + (f^* + f) \sin^2 \varphi - \frac{7}{4} f^2 \sin^2 2\varphi \right] $$

Questa è una **approssimazione teorica** della variazione dell’accelerazione di gravità effettiva **g(φ)** con la latitudine φ su un ellissoide rotante in equilibrio idrostatico, derivata dal **teorema di Clairaut**.

#### Significato dei parametri

- **f** (flattening geometrico o appiattimento):  
  È la misura dello schiacciamento della Terra:  
  $$
  f = \frac{a - b}{a}
  $$  
  dove **a** è il raggio equatoriale (semi-asse maggiore) e **b** il raggio polare (semi-asse minore).  
  Valore per la Terra: **f ≈ 1/298.257 ≈ 0.003353**.

- **f*** (gravity flattening o appiattimento gravitazionale):  
  È un parametro che quantifica la variazione relativa di gravità tra poli ed equatore, principalmente dovuta all’effetto centrifugo e alla forma ellissoidale.  
  Nella teoria di Clairaut per un ellissoide in equilibrio idrostatico si ha approssimativamente:  
  $$
  f^* \approx \frac{5}{2} m - f
  $$  
  dove **m** è il rapporto tra l’accelerazione centrifuga massima (all’equatore) e la gravità all’equatore:  
  $$
  m = \frac{\omega^2 a}{g_e} \approx 0.003467
  $$  
  Quindi **f* ≈ 0.00529** (valore teorico molto vicino a quello osservato).

#### Spiegazione dei termini

- **(f* + f) sin²φ**:  
  È il termine principale che descrive la variazione lineare di g con la latitudine.  
  - **f sin²φ**: contributo **geometrico** dovuto all’appiattimento (ai poli si è più vicini al centro → gravità maggiore per 1/r²).  
  - **f* sin²φ**: contributo dovuto all’**effetto centrifugo diretto** e alla correzione indiretta dall’equilibrio idrostatico (la deformazione modifica la distribuzione di massa).  
  In totale: **(f* + f) ≈ 0.00530**, che corrisponde al coefficiente principale nella formula empirica di Somigliana (0.0053024).

  Questo spiega perché il coefficiente osservato (≈0.0053) è maggiore del valore centrifugo puro per una sfera (≈0.00346): l’appiattimento aggiunge un contributo positivo extra.

- **− (7/4) f² sin² 2φ**:  
  È una **correzione di ordine superiore** (quadratica in f, che è piccolo).  
  Tiene conto di effetti più sottili nella forma ellissoidale e nella distribuzione di massa (termini in armoniche superiori, come J₄).  
  Il termine sin² 2φ = 4 sin²φ cos²φ varia più rapidamente con la latitudine (massimo a 45°).  
  Nella formula di Somigliana il termine equivalente è molto piccolo (−0.0000059 per sin² 2φ).

#### Riassunto fisico

La formula deriva dal **teorema di Clairaut** (1743): su un ellissoide rotante in equilibrio idrostatico, la gravità superficiale dipende in modo semplice dalla latitudine.

- Senza rotazione (ω=0) → f=0, f*=0 → g costante.  
- Con rotazione ma sfera rigida → solo effetto centrifugo → coefficiente ≈ m ≈ 0.00346.  
- Con rotazione + deformazione ellissoidale → coefficiente (f* + f) ≈ 0.0053 (valore teorico molto vicino al misurato).

Questa è una versione **teorica pura** per un ellissoide idrostatico; le formule empiriche come quella di Somigliana aggiungono piccoli aggiustamenti per adattarsi meglio alle misure reali (distribuzione di massa non perfettamente uniforme).