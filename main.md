# Laplace

# Inverselaplace

# Faltning

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

## Bra satser

- $e^{At} = \Sigma^{\infty}_{k=0} \frac{A^k*t^k}{k!}$
- Ortogonal matris $A \equiv$ $A$ Inverterbar med $A^{-1}=A^T$, $AA^T=A^TA=I$, # TODO: är del två sann?

# System

## Vad menas med

- **Linjärt**: $S(\alpha w_1 + \beta w_2) = \alpha S w_1 + \beta S w_2$
- **Tidsinvariant**: Om $S w(t) = y(t)$ så är $S*w(t-a) =  (t-a)$
- **Stabilt**: Varje begränsad insignal w(t) ger upphov till en begränas utsignal y(t).

  - Om ett LTI system $S$ har impulssvaret $h(t)$ så är $S$ stabilt om och endast om integralen $\int_{-\infty}^{\infty} |h(t) dt$ konvergerar

  - Om $H(s) = \frac{Q(s)}{P(s)}$ så är Systemet S stabilt om och endast om $deg Q(s) \leq deg P(s)$ och För varje pol $s_j$ gäller $Re s_j \le 0$.
  - Exempel på icke stabilt system är ett system som deriverar, insignal $\cos (t^2)$ stämmer ej

- **Kausalt**: Om $S w(t) = y(t)$ och $w(t) = 0$ för $t < t_0$ så gäller att $y(t) = 0$ för $ t < t_0$
  - Ett LTI system är kausalt om och endast om impulssvaret $h(t)$ är en kausal funktion.

## Bra satser

- System kan beskrivas som faltningar med en fix funktion $h(x)$.
- Impulssvaret är derivatan av stegsvaret: $h(t) = (S\theta(t))'$
- Överföringsfunktionen: $H(s) = \frac{Se^{st}}{e^{st}}$
- Frekvensfunktion $H(t)$ ger oss följande:
- $S sin(w t) = A(w) sin(wt+ \phi(w))$ med amplitudfunktionen $A(w) = |H(iw)|$ och fasfunktionen $\phi(w) = arg(H(iw))$
- För LTI system så är $\mathcal{L} h(t) = H(s)$
- $S(e^{st}) = H(s)e^{st}$

# Kontrollera efter uppgift

- Diff ekvation
  - Testa begynnelse vilkor
  -
