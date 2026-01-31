# Deduzione della formula di $g(\varphi,h)$  
*(da Newton → geopotenziale → formula di Somigliana)*

---

## 1. Partenza: gravitazione newtoniana
Per un pianella sferica di massa $M$ e raggio $R$ la gravità alla superficie è

$$
g_0=\frac{GM}{R^2}
\qquad\Longrightarrow\qquad
g_0\approx 9{,}8~\text{m s}^{-2}
$$

La Terra **non è una sfera**:
- è un ellissoide di rotazione (semiasse equatoriale $a$, semiasse polare $b=a(1-f)$, $f\approx 1/298{,}26$);
- ruota con velocità angolare $\omega$;
- il potenziale gravitazionale $U$ è la somma di un termine **gravitazionale** e uno **centrifugo**.

---

## 2. Potenziale esterno di un ellissoide rotante
Nel sistema di riferimento solidale con la Terra (coordinate ellissoidali) il potenziale di gravito-centrifuga assume la forma generale

$$
U(r,\theta)=
\frac{GM}{r}\!\left[1-\sum_{n=2}^{\infty}\left(\frac{a}{r}\right)^{\!n}\!
\Bigl(J_n P_n(\cos\theta)\Bigr)\right]
-\frac12\omega^2 r^2\sin^2\theta
$$

dove:
- $\theta$ è la colatitudine ($\theta=90^\circ-\varphi$);
- $J_n$ sono i coefficienti adimensionali del campo gravitazionale (armonici zonalità);
- $P_n$ i polinomi di Legendre.

Per i fini geodetici basta il termine dominante $J_2$ (flattening gravitazionale); troncando a $n=2$:

$$
U(r,\theta)\approx
\frac{GM}{r}\!\left[1-J_2\!\left(\frac{a}{r}\right)^2\!
P_2(\cos\theta)\right]
-\frac12\omega^2 r^2\sin^2\theta
$$

---

## 3. Gravità sulla superficie dell'ellissoide
La gravità **efficace** (cioò misurabile) è il modulo del gradiente del potenziale:

$$
g=-\left.\frac{\partial U}{\partial n}\right|_{\text{ellissoide}}
$$

dove $\partial n$ è la derivata lungo la normale alla superficie.  
Con l'approssimazione di **Clairaut** (1743) si ottiene

$$
g(\varphi)=g_e\!\left(1+\beta\sin^2\varphi-\beta_1\sin^2 2\varphi+\dots\right)
$$

con:
- $g_e$ gravità equatoriale;
- $\beta$ coefficiente di Clairaut legato a $f$ e al rapporto $\omega^2 a/g_e$;
- $\beta_1$ piccolo termine di secondo ordine.

Nel 1930 **Somigliana** integrò esattamente il campo di un ellissoide di riferimento (GRS-67, poi GRS-80) ottenendo la **formula di Somigliana**:

$$
g(\varphi)=
\frac{a g_e\cos^2\varphi+b g_p\sin^2\varphi}
{\sqrt{a^2\cos^2\varphi+b^2\sin^2\varphi}}
$$

Sviluppando in serie di $\sin^2\varphi$ e arrestando al secondo ordine:

$$
g(\varphi)\approx
g_e\!\left[1+(f^*+f)\sin^2\varphi-\frac74f^2\sin^2 2\varphi\right]
\qquad
f^*=\frac{g_p-g_e}{g_e}
$$

I valori adottati per l'ellissoide WGS-84 sono:
- $g_e=9{,}780\,326\,771\,4~\text{m s}^{-2}$
- $g_p=9{,}832\,186\,368\,5~\text{m s}^{-2}$

Sostituendo e riarrangiando si ricava la forma pratica:

$$
g(\varphi)=
9{,}780\,318\,4\Bigl(1+0{,}005\,302\,4\sin^2\varphi-0{,}000\,005\,9\sin^22\varphi\Bigr)
$$

---

## 4. Correzione di altitudine (effetto di "free-air")
Allontanandosi di $h$ metri dal geoide la gravità diminuisce per:
1. diminuzione del contributo Newtoniano $\propto 1/r^2$;
2. aumento (trascurabile) del termine centrifugo.

Linearizzando:

$$
g(h)\approx g(\varphi)-\frac{2g(\varphi)}{R}\,h
\qquad\Longrightarrow\qquad
\Delta g_{\text{FA}}\approx -0{,}000\,003\,086\cdot h~\text{(m s}^{-2})
$$

con $R\approx 6\,378\,137$ m (raggio equatoriale WGS-84).

---

## 5. Formula finale
Componendo i due contributi si ottiene la relazione fornita nell'esperimento:

$$
\boxed{
g_{\text{teor}}(\varphi,h)=
9{,}780\,318\,4\Bigl(1+0{,}005\,302\,4\sin^2\varphi-0{,}000\,005\,9\sin^22\varphi\Bigr)
-0{,}000\,003\,086\cdot h
}
$$

dove:
- $\varphi$ è la latitudine in gradi decimali;
- $h$ è l'altezza ortometrica (o ellissoidica) in metri.

---

## 6. Bibliografia essenziale
- Moritz, H. (1980) *Geodetic Reference System 1980*.  
- Hofmann-Wellenhof & Moritz (2006) *Physical Geodesy*.  
- NIMA (2000) *WGS-84 Development Report*.