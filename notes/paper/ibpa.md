# Apuntes sobre IBPA

Apuntes personales en elaboración; las interpretaciones todavía deben contrastarse con el paper. La formulación del modelo y las demostraciones se organizarán en [model.md](model.md) y [proofs.md](proofs.md).

En papers antiguos se mantenía el mecanismo de scalar-bid pero se agrupaban los segmentos. Esos grupos son los que se presentan a los Advertisers.

# Apuntes: Bosquejo del Modelo IBPA

| Tipo                    | Momento                  | ¿En qué se basa?                               | Ejemplo                                                                                        |
| ----------------------- | ------------------------ | ---------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Probabilidad Normal** | Siempre (antes de tirar) | Reglas matemáticas puras.                      | "Hay 50% de probabilidad de que salga cara al lanzar la moneda".                               |
| **Análisis Ex-Ante**    | Antes del evento         | Datos del momento, pronósticos y suposiciones. | "Estimamos un 80% de probabilidad de que el banco central baje las tasas de interés este mes". |
| **Análisis Ex-Post**    | Después del evento       | Hechos reales y datos duros históricos.        | "Mirando los datos del mes pasado, el banco central efectivamente bajó las tasas".             |
- **Ex-ante probability of allocation**: Probabilidad de que el Advertiser se le asigne la impresión. Promediada sobre la distribución de valoraciones del Advertiser y los posibles segmentos (categorías de público que ve la publicidad).  
  

- $M(q)$ mecanismo que decide si asignar la impresión dependiendo del valor que ofrece el Advertiser para cada segmento y mezcla de segmentos (Mixed-bundle).  El valor por lo tanto es multidimensional (un vector). Este mecanismo consiste en fijar los precios a los cuales se está dispuesto a vender el producto. Por lo tanto cada mecanismo induce un probabilidad de asignación $q$ ex ante: ¿Qué significa esto? que dado los precios de entrada, como no se sabe cuánto valor tiene para el Advertiser cada segmento pero si que sigue cierto tipo de distribución (uniforme por ejemplo) con esa distribución se puede calcular la probabilidad esa probabilidad.
- Ejemplo. Consideremos cuatro mecanismos:

| Mecanismo | Precio mínimo | Probabilidad de asignación |
| --------- | ------------- | -------------------------- |
| $M(0.1)$  | 0.90          | 10%                        |
| $M(0.2)$  | 0.80          | 20%                        |
| $M(0.35)$ | 0.65          | 35%                        |
| $M(0.5)$  | 0.50          | 50%                        |

¿Por qué $M(0.35)$ asigna el 35% de las veces? Porque $P(v_A \geq 0.65) = 0.35$ Es una probabilidad calculada antes de conocer la valoración concreta.

- $R(q) =  \text{máximo ingreso esperado}$ sujeto a $P(asignación)\leq q$   
- ¿Por qué se elije el $q$ mínimo al cual el mecanismo $M(q)$ asigna el recurso? Porque mientras menor sea el $q$, más selectivo es el mecanismo que todavía está dispuesto a asignarle la impresión al anunciante, dadas sus valoraciones para todos los segmentos. (Tiene que pagar más).
- Mecanismo hipotético $M(0.3)$ que establece:
	- Si aparece A, asignar cuando $v_A\geq0.8$
	- Si aparece B, asignar cuando $v_B\geq0.6$
- $Q_t(v) = \inf \{q : v \in \Omega_t(q) \}$ donde $\Omega_t(q)$ es la región donde se acepta el vector si aparece el segmento $t$. Cada mecanismo determina una región del plano $(v_A,v_B)$ cuyos anunciantes recibirían la impresión.

- Una vez se elije el Advertiser ganador según el que tenga mejor ganancia marginal (menor $q$ al ser esta curva cóncava). El pago sigue una regla análoga al GSP: se elije el mecanismo de cobro $M(q^{crit})$. Donde $q^{crit}$ es el $q$ máximo dentro del cual el Advertiser le gana a los otros postores.

# Formalización del Modelo IBPA
- **Priors**: Distribuciones de probabilidad a priori, o sea es la creencia que tiene el Publisher sobre la distribución de probabilidad que siguen las valorizaciones de los Advertisers.
- El Publisher se compromete con un mecanismo -> Se obtiene un segmento -> Advertiser elaboran sus vectores de valores -> El mecanismo selecciona al mejor postor.
- **Ex-ante:** Ex-ante se refiere al estado antes de que el segmento y las valuaciones del advertiser se muestren.
- ¿Por qué el valor esperado ($E$) se calcula "solo sobre los otros anunciantes $b_{-a}$?
  En el momento de enviar su oferta, existe una asimetría de información entre lo que el anunciante $a$ sabe y lo que ignora:
	- **Lo que el anunciante** $a$ **conoce (no es aleatorio para él):** Conoce su propio valor real $v_a$ y la puja $b_a$ que él decide enviar. Para el anunciante $a$, $b_a$ es una variable fija elegida por él mismo.
	- **Lo que el anunciante** $a$ **desconoce (es aleatorio para él):** No sabe exactamente qué vectores de oferta enviarán los demás anunciantes $b_{-a} = (b_1, \dots, b_{a-1}, b_{a+1}, \dots, b_A)$.
	Por eso, cuando el anunciante $a$ calcula su utilidad esperada al elegir una puja $b_a$, debe **promediar (calcular la esperanza** $E_{b_{-a}}$**) sobre todas las posibles pujas que sus rivales podrían enviar** según las distribuciones a priori que él atribuye a sus competidores.
