# Kap 1

$p_{\Delta}(t) = \frac{1}{\Delta}$ då $0 \< t \< \Delta$ annars 0
$\int^{\infty}_{-\infty} p_{\Delta}(t) dt = 1$

Om $f$ är deriverbar utom i punkterna $a_1, \ldots, a_n$ där den har språng av höjder $b_1,\ldots,b_n$ så är

$$
f'(t) = f'\_p(t) + b_1\delta(t-a_1)+\ldots+b_n(t-a_n)
$$

där $f'_p$ är derivatan som vi kan läsa av från graf med heavside funktion

# Laplace

# Inverselaplace

# Faltning

> Faltning: $f \ast g(t) = \int_{-\infty}^{\infty} f(t-\tau)*g(\tau) d\tau$

$$
f \ast \delta^{(n)} = f^{(n)}
$$

# Matriser

$$
p(D) = diag(p(\lambda_1),\ldots,p(\lambda_n))
$$

p är vårt polynom, t.ex om vi har $e^A$ så blir det, $p(x) = e^x$

> Det finns diagonaliserbara matriser med flera av samma egenvärden, t.ex $A = I$ har egenvärden $\lambda_1 = \lambda_2 = 1$ och är diagonal.

> Resolventmatrisen har formen $\frac{P(s)}{Q(s)}$

> Varje element i $e^{At}$ är summan av termer av formen $C t^k e^{\lambda_j} t$ där $\lambda_j$ är ett egenvärde, och k är strikt mindre än multipliciteten av
> $\lambda_j$ i karaktetiska polynomet $p_A(\lambda)$. Om $A$ är diagonaliserbar är alltid $k=0$.

> $\cos$ och $\sin$ kan skrivas om med eulers formel.
<img width="196" alt="image" src="https://user-images.githubusercontent.com/47189713/224545247-72a60f60-f702-4455-97e0-f2d5a66b9580.png">

## Vad kan man säga från ett element i $e^{At}$?

- Om t finns i elementet så är den ej diagonaliserbar
- Om elementet har en term som är konstant så är den ej inverterbar då konstanten är $C*e^{0t}$ så $0$ är ett egenvärde. ($det(A)=0$)

## Sylvester sats

I varje diagonalisering är antalet positiva element på diagonalen alltid lika. Detsamma gäller antalet negativa element och element lika med 0.

Vi kan hitta antal positiva och negativa element genom gaus och få fram $d_i$.

Vi kan få fram antal element som är större än $c$, genom att applicera ovan metod på matrisen $A-cI$.

## Bra satser

- $e^{At} = \Sigma^{\infty}_{k=0} \frac{A^k*t^k}{k!}$
- Ortogonal matris $A \equiv$ $A$ Inverterbar med $A^{-1}=A^T$, $AA^T=A^TA=I$, # TODO: är del två sann?
- $tr A = \lambda_1 + \ldots + \lambda_n$ då A är kvadratisk
- $det A = \lambda_1 * \ldots *\lambda_n$ # TODO: Improve
- $p(A) = Sp(D)S^{-1}$

# Kvadratisk form

Låt A vara en symmetrisk matris med egenvärden $\lambda_1, \ldots, \lambda_n$, det gäller då att A är:

- Positivt definit - Om alla egenvärden är positiva ($>$)
- Positivt semidefinit - Om alla egenvärden är icke negativa ($\leq$)
- Negativt definit - Om alla egenvärden är negativa($<$)
- Negativt semidefinit - Om alla egenvärden är icke positiva($\geq$)
- indefinit - Om det finns både positiva och negativa egenvärden

Man kan också också fram ta värden d, genom att strick gauseliminering där våra pivå element är värden vi sätter in i formlen ovan.

## Choleskyfaktorisering

Man kan använda resultat från Strickt gausselimnering för att diagonalisera en matris. Med följande sats

$$
K = R^TDR
$$

Där D är en matris med diagonalen av våra pivåelement från Strickt gauss. Och R är vår triangelmatris med $1$ på diagonalen.

Choleskyfaktorisering är $K = LL^T$ där $L = R'^T$ och $R' = D_{1/2}R$ (OBS: Fungerar bara om A är positivt semidefinit)

# System

## Vad menas med

- **Linjärt**: $S(\alpha w_1 + \beta w_2) = \alpha S w_1 + \beta S w_2$
- **Tidsinvariant**: Om $S w(t) = y(t)$ så är $S*w(t-a) =  (t-a)$
- **Stabilt**: Varje begränsad insignal w(t) ger upphov till en begränas utsignal y(t).

  - Om ett LTI system $S$ har impulssvaret $h(t)$ så är $S$ stabilt om och endast om integralen $\int_{-\infty}^{\infty} |h(t)| dt$ konvergerar

  - Om $H(s) = \frac{Q(s)}{P(s)}$ så är Systemet S stabilt om och endast om $deg Q(s) \leq deg P(s)$ och För varje pol $s_j$ gäller $Re s_j \le 0$.
  - Exempel på icke stabilt system är ett system som deriverar, insignal $\cos (t^2)$ stämmer ej

- **Kausalt**: Om $S w(t) = y(t)$ och $w(t) = 0$ för $t < t_0$ så gäller att $y(t) = 0$ för $ t < t_0$
  - Ett LTI system är kausalt om och endast om impulssvaret $h(t)$ är en kausal funktion.
  - Ett exempel på LTI system som är kausalt är $S(w(t)) = w(t)$, asså multiplikation med 1

## Bra satser

- System kan beskrivas som faltningar med en fix funktion $h(x)$.
- Impulssvaret är derivatan av stegsvaret: $h(t) = (S\theta(t))'$
- Överföringsfunktionen: $H(s) = \frac{Se^{st}}{e^{st}}$
- Frekvensfunktion $H(t)$ ger oss följande:
- $S sin(w t) = A(w) sin(wt+ \phi(w))$ med amplitudfunktionen $A(w) = |H(iw)|$ och fasfunktionen $\phi(w) = arg(H(iw))$
- För LTI system så är $\mathcal{L} h(t) = H(s)$
- $S(e^{st}) = H(s)e^{st}$

### Bestämma utsignal om insignal är $cos(wt)$ eller $sin(wt)$

> Amplitudfunktionen: $A(\omega) = |H(i\omega)|$

$$
  S cos(wt) = Re H(iw) * e^{iwt}
$$

$$
 S sin(wt) = Im H(iw) * e^{iwt}
$$

# Lösa diff ekvationer

## Laplacetransformation

### Ansats till invers transform

| Poler hos $V(s)$                      | Bidrag till $v(t) = \mathcal{L}^{-1} V$                                                                              |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Enkel pol i $s=p$                     | $Ae^{pt} \theta(t)                                                                                                   |
| Pol av ordning $k$ i $s=p$            | $(A*0\* t^0 + \ldots + A*{k-1}\*t^{k-1})e^{pt} \theta(t)                                                             |
| Enkla poler i $s=\sigma \pm i \omega$ | $e^{\sigma t)} (A_0* t^0 + \ldots + A_{k-1}*t^{k-1})e^{pt} \theta(t) = Ce^{\sigma t}cos(\sigma t + \alpha)\theta(t)$ |

## Diagonalisering genom variabelbyte

Om $A$ är en diagonaliserbar matris så har det homogena systemet $\frac{du}{dt} = Au$ den allmänna lösningen

$$
    u=C_1e^{\lambda_1t}s_1+\ldots+C_n*e^{\lambda_nt}s_n
$$

där $\lambda$ är egenvärden till $A$, $s$ är motsvarande egenvektorer och $C$ är godtyckliga konstanter.

## Exponentialmatris

$$
    e^{tA} = Se^{tD}S^{-1} = S diag(e^{\lambda_1t}, \ldots, e^{\lambda_n * T}) S^{-1}
$$

det homogena systemet $\frac{du}{dt}=Au$ har lösningen $u(t)=e^{tA}u(0)$

$$
e^{At} = S * diag(e^{\lambda_1t}+\ldots+e^{\lambda_k t}) S^{-1}
$$

# Kontrollfrågor

# Kontrollera efter uppgift

- Diff ekvation
  - Testa begynnelse vilkor
  -
  
  
  
  
  
