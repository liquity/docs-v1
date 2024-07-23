# General

### ¿Qué es Liquity?

Liquity es una plataforma descentralizada que permite tomar un préstamo libre de interés usando Ethereum como garantía. Los préstamos se toman en LUSD (una moneda estable vinculada al USD) y tienen que mantener una relación mínima de garantía de 110%.

Además de la garantía, los préstamos están asegurados por el Fondo de Estabilidad que contiene LUSD y por los otros prestatarios que colectivamente funcionan como garantes de última instancia. Se puede aprender más sobre estos mecanismos en nuestros documentos.

Liquity es un protocolo sin custodia, inmutable y no tiene gobernanza.

### ¿Cúal es la motivación detrás de Liquity?

Los activos con valor estable (Stable Coins) son la base fundacional y esencial para las aplicaciones del ecosistema Ethereum y han crecido para representar miles de billones de dólares en valor.

Sin embargo, la gran mayoría de este valor está representado por monedas estables colateralizadas por fiat, como pueden ser Tether o USDC. Estables descentralizar como DAI o sUSD representan una porción menor de todo el universo de estables, lo que significa que la gran mayoría de las monedas estables son centralizadas.

Liquity aborda esto al crear una manera más eficiente y más amigable al usuario de tomar un préstamo denominado en una moneda estable. Además, Liquitiy no tiene gobernanza, asegurando que el protocolo se mantiene descentralizado.

### ¿Cuáles son los beneficios de Liquity?

Los beneficios de Liquity son:

* Tasa de interés de 0% - como tomador, no hay necesidad de preocuparse por una deuda creciente
* Relación mínima de garantía de 110% - uso más eficiente para ETH
* Sin gobernanza - todas las operación de Liquity son definidas por los contratos inteligentes y totalmente automatizadas, no pudiendo cambiarse ningun parametro
* Directamente Redimible - LUSD puede ser redimido por su valor nominal contra la garantía base en cualquier momento
* Totalmente descentralizado - Los contratos de Liquity no tienen ninguna llave de administración y son accesibles desde diferentes interfaces mantenidas por los Operadores de Frontend, convirtiéndose en resistente a la censura

### ¿Puede Liquity cambiarse?

No. Liquity no tiene ninguna llave de administración, y nadie puede cambiar las reglas seteadas en los contratos. Son inmutables.

### ¿Cómo puedo usar Liquity?

Lo primero es elegir una interfaz (es decir un Frontend) para acceder al protocolo. El equipo que creó Liquity no opera ningún frontend. En vez de eso, se accede a Liquity desde frontend mantenidos por terceros. La lista de frontend está [aquí](https://www.liquity.org/frontend).

### ¿Cuáles son los casos de uso para Liquity?

* Tomar un préstamo de LUSD contra ETH al abrir un Trove
* Asegurar a Liquity en su conjunto al proveer LUSD al Fondo de Estabilidad a cambio de recompensas
* Stakear LQTY para conseguir ingresos de los prestatarios o por redimir LUSD
* Redimir 1 LUSD a 1 USD de ETH cuando el valor de LUSD baja de $1

### ¿Qué son LUSD y LQTY?

LUSD es una moneda estable vinculada al valor del USD, usada para tomar los préstamos en Liquity. En cualquier momento puede ser usada para redimir la garantia a su valor nominal. Aprendan más sobre el [mecanismo de estabilización](https://liquity.gitbook.io/spanish/faq/lusd-redenciones).&#x20;

LQTY es el token secundario emitido por Liquity. Captura los ingresos que son generados por el protocolo, e incentiva a los primeros en adoptar y a los frontends. El total de LQTY es de 100,000,000 tokens. Para más información de cómo estos tokens fueron colocados y liberados en el tiempo, por favor mirar [Distribución y Colocación de LQTY](https://liquity.gitbook.io/spanish/faq/recompensas-y-distribucion-de-lqty).

### ¿Qué necesito para usar Liquity?

Para pedir prestado LUSD, solo necesitas una billetera (por ejemplo, Metamask) y suficiente Ether para abrir un Trove y pagar el gas.

Para depositar en el Fondo de Estabilidad se requiere LUSD.

Para stakear LQTY, se requieren tokens LQTY.

Se puede tomar prestado LUSD al abrir un Trove y LQTY puede ganarse depositando en el Fondo de Estabilidad. Se pueden usar Uniswap u otro exchange (descentralizado) para comprar los tokens en el mercado.

### ¿Cobra Liquity alguna tarifa?

Hay una tarifa por única vez al pedir prestado LUSD, y cuando el LUSD es redimido:

* Para prestatarios, se paga un gasto por única vez al pedir un préstamo que es un porcentaje del total de LUSD solicitado.
* Para los que redimen, hay una tarifa sobre lo que se paga (en ETH) al intercambiar LUSD a ETH. Esta redención es diferente que repagar tu préstamo, que no tiene costo.

Ambas tarifas dependen del volumen de redención, un incremento en la función significa una tarifa mayor, que va decayendo en el tiempo.La intención es acelerar los grandes rescates con tarifas más altas y acelerar los préstamos directamente después de grandes volúmenes de rescate. La disminución de la tarifa con el tiempo garantiza que la tarifa tanto para los prestatarios como para los canjeadores se "enfriará", mientras que los volúmenes de canje son bajos.

La tarifa no puede ser inferior al 0.5% (excepto en Modo de Recuperación), lo que protege el rescate de ser mal usado para arbitraje al adelantarse a la actualización de precios. La tarifa para pedir préstamo tiene un tope de 5%, manteniendo el sistema atractivo (de alguna manera) para los prestatarios incluso cuando hay muchos rescates. Excepto lo anterior ambas tarifas son idénticas y aparecen como “Fee” en el siguiente gráfico:

<figure><img src="https://lh6.googleusercontent.com/8eBxyfBS7M-ca6cI5hJSbWFgvDMAs788__MXKYpXn2wi3KZ-gAbJvB5CZaBgpY1bmMlq3SRjmQDINr4quT0ay_rWH-DRZCs_BTGzSxj6PpKYrVfEzKS9firkDvpm35mXnkcj_OwkJsePKdRL-JtXzWmdMQX1mJMJO9xbHsjzuHCJjf7yBXQlOJC_lZhYfw" alt=""><figcaption></figcaption></figure>

### ¿Cómo puedo ganar dinero usando Liquity?

Hay dos formas diferentes de generar ingresos usando Liquity:

* Deposite LUSD en el Fondo de Estabilidad y obtenga ganancias de liquidación (en ETH) y recompensas LQTY.
* Stakee LQTY y obtenga ingresos de LUSD y ETH de las tarifas de préstamo y reembolso.

### ¿Puedo perder mis fondos?

Al ser un sistema sin custodia, todos los tokens enviados al protocolo serán retenidos y gestionados algorítmicamente sin la interferencia de ninguna persona física o jurídica. Eso significa que sus fondos sólo estarán sujetos a las reglas establecidas en el código de contrato inteligente, que está siendo auditado dos veces por Trail of Bits y una vez por Coinspect (encuentre sus informes [aquí](https://docs.liquity.org/documentation/resources)).

Hay dos escenarios en los que puede perder una parte de sus fondos:

* Usted es un prestatario (propietario de Trove) y su garantía en ETH fue liquidada. Aún conservará su LUSD prestado, pero su Trove se cerrará y su garantía se utilizará para compensar a los depositantes del Fondo de Estabilidad.
* Usted es un depositante del Fondo de Estabilidad y su LUSD depositado se usa para pagar la deuda de los prestatarios liquidados. Dado que las liquidaciones se activan cada vez que la garantía de los prestatarios cae por debajo del 110%, recibirá más ETH a cambio con una probabilidad muy alta. Sin embargo, si el precio de ETH disminuye y usted mantiene la exposición, puede perder valor en sus depósitos totales del grupo.

Tenga en cuenta que LUSD no está perfectamente vinculado al USD y puede desviarse ligeramente en ambas direcciones bajo ciertas condiciones de mercado. Consulte [Sobre la estabilidad de precios de LUSD](https://www.liquity.org/blog/on-price-stability-of-liquity) para obtener más detalles.

Aunque el sistema se audita diligentemente, nunca se puede descartar por completo un hackeo o un error que resulte en pérdidas para los usuarios (ver [descargo de responsabilidad](https://liquity.org/disclaimer))
