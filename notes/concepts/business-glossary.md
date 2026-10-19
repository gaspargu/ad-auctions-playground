# Terminología del negocio

Apuntes personales en elaboración. Las definiciones deben contrastarse con las fuentes.

> **Advertencia de lectura:** la entrada sobre GSP conservada abajo requiere revisión: en general, GSP no induce ofertas veraces; con múltiples posiciones y factores de calidad, su pago no se reduce simplemente a la segunda oferta. Ver sección 6.3.3 del paper.

- **Auction**: Subasta. En este contexto lo que se subasta es el espacio para poner publicidad. Los anunciantes serían los postores/oferentes que buscan poner su publicidad en ese espacio. Y el vendedor de la subasta sería el advertising publisher (el Retail mismo o en este caso el intermediario que gestiona eso como AndesML).
- **Bid**: Puja en una subasta.
- **Scalar Bid**: Se limita a los oferentes de la subasta a hacer una puja por un valor fijo, o sea que no pueden proponer un valor condicional (o sea arreglo o matriz de valores) que sea dependiente del segmento según sus preferencias. 
- **GSP (Generalized Second Price)**: En este tipo de subastas las plataformas restringen a los anunciantes a enviar una sola cifra por cada oportunidad de impresión o grupo de segmentos revelado. Aquí el ganador se lleva el espacio publicitario, pero **paga el precio ofertado por el segundo lugar** (más una fracción mínima). Incentiva a los anunciantes a ofertar lo que realmente valoran sin temor a pagar de más.
- **Full Disclosure**: El Publisher revela totalmente cuál es el segmento de compradores al que estaría accediendo el Advertiser a mostrar su publicidad. 

- **Advertisers**: Los anunciantes que quieren que sus productos sean vendidos. Ejemplo: El Retail puede ser CruzVerde y un anunciante puede ser crema Vichy.
- **Inventario publicitario (** **Ad Inventory** **):** Es el conjunto total de espacios publicitarios que una plataforma o _publisher_ pone a disposición de los anunciantes. Abarca las distintas oportunidades de ubicación en motores de búsqueda, plataformas de _retail media_ o sitios de anuncios _display_, incluyendo diversos formatos de anuncios (como pancartas o banners, torres, etc.) y posiciones dentro de la página.
- **Advertising Publisher** (o editor de publicidad digital) es la entidad o plataforma que vende inventario publicitario e impresiones a los anunciantes en entornos como sitios web, motores de búsqueda o plataformas de _retail media_. En los mecanismos de subastas de publicidad digital, el _publisher_ desempeña un rol central caracterizado por:
	- **Gestión del inventario e información de segmentación:** Es quien ofrece las oportunidades de impresión y observa de forma privada los atributos contextuales y de la audiencia (como datos demográficos, historial de navegación o compras previas del consumidor).
	- **Diseño del mecanismo de venta:** Determina la regla de asignación de espacios e impresiones y el esquema de precios o cobros, ya sea mediante subastas tradicionales (como las de primer precio o de segundo precio generalizado, GSP) o mediante mecanismos avanzados de empaquetado de información.
	- **Manejo del balance entre precisión y competencia:** Debe gestionar el dilema entre revelar información detallada de segmentación (que incrementa la relevancia del anuncio para los anunciantes) y preservar la masa crítica de competidores en la subasta para no reducir sus ingresos.


- **Impression**: Cuando la publicidad aparece en la pantalla del usuario final sin importar si hace click o no.
- **Market Thickness**: es un concepto de la economía y el diseño de mercados que mide la cantidad y la frecuencia de los participantes (compradores y vendedores, o la oferta y la demanda) disponibles en un mercado en un momento dado.
  Densidad o liquidez del mercado, se refiere a mantener una masa crítica de oferentes (anunciantes) compitiendo activamente juntos en la subasta.
- **Market thinning**: Cuando un _publisher_ revela información de segmentación demasiado específica antes de la puja, la demanda se fragmenta porque los anunciantes solo participan en las subastas de los micro-segmentos que les interesan[1][2]. Esto reduce drásticamente el número de competidores directos en cada subasta individual, lo que debilita la presión competitiva y disminuye los ingresos del _publisher_.
 - **Allocation Rate**: (tasa de asignación, también llamada tasa de liquidación o _sell-through rate_) representa el **porcentaje de impresiones u oportunidades publicitarias disponibles que efectivamente se adjudican y venden** a un anunciante en las subastas.
