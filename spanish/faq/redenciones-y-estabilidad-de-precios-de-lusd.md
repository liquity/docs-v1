# Redenciones y estabilidad de precios de LUSD

### ¿Cómo sigue LUSD de cerca el precio del USD?

La capacidad de canjear LUSD por ETH al valor nominal (es decir, 1 LUSD por $1 de ETH) y la relación de garantía mínima del 110 % crean un precio mínimo y un precio máximo (respectivamente) a través de oportunidades de arbitraje. Los llamamos "mecanismos de vinculación dura" ya que se basan en procesos directos.

LUSD también se beneficia de mecanismos menos directos para la paridad del USD, llamados "mecanismos de vinculación blanda". Uno de estos mecanismos es la paridad como punto de Schelling. Dado que Liquity trata a LUSD como equivalente a USD, la paridad entre los dos es un estado de equilibrio implícito del protocolo. Otro de estos mecanismos es la comisión de endeudamiento de las nuevas deudas. A medida que aumentan los reembolsos (lo que implica que LUSD está por debajo de $1), también lo hace la tasa base, lo que hace que los préstamos sean menos atractivos, lo que evita que nuevos LUSD lleguen al mercado y lleven el precio por debajo de $1.

Lea más sobre la estabilidad de precios de LUSD [aquí](https://www.liquity.org/blog/on-price-stability-of-liquity).

### ¿Qué son los canjes?

Un canje es el proceso de intercambiar LUSD por ETH al valor nominal, como si 1 LUSD valiera exactamente $1. Es decir, por x LUSD obtienes x dólares en ETH a cambio.

Los usuarios pueden canjear sus LUSD por ETH en cualquier momento sin limitaciones. Sin embargo, es posible que se cobre una tarifa de canje sobre el monto canjeado.

Por ejemplo, si la tarifa de canje actual es del 1 %, el precio de ETH es de $500 y canjeas 100 LUSD, obtendrás 0,198 ETH (0,2 ETH menos una tarifa de canje de 0,002 ETH).

Tenga en cuenta que la cantidad canjeada se tiene en cuenta para calcular la tasa base y puede tener un impacto en la tarifa de redención, especialmente si la cantidad es grande.

### ¿Es lo mismo un rescate que el pago de mi deuda?

No, los canjes son un mecanismo completamente separado. Todo lo que uno tiene que hacer para pagar su deuda es ajustar la deuda y la garantía de Trove.

### ¿Cómo se calcula la tarifa de rescate?

Bajo operación normal, la tarifa de redención viene dada por la fórmula (tasa base + 0.5%) \* ETH retirado

### ¿Cómo se calcula la tasa base?

Las tarifas de redención se basan en la variable de estado baseRate en Liquity, que se actualiza de forma dinámica. La tasa base aumenta con cada canje y disminuye según el tiempo transcurrido desde el último evento de tarifa, es decir, el último canje o emisión de LUSD.

En cada redención:

* La tasa base se reduce en función del tiempo transcurrido desde el último evento de tarifa
* La tasa base se incrementa en una cantidad proporcional a la fracción del suministro total de LUSD que se canjeó
* La tarifa de canje está dada por (tasa base + 0.5%) \* ETH retirado

### Como prestatario, ¿pierdo dinero si me canjean?

Si se canjea su Trove, no incurre en una pérdida neta. Sin embargo, perderá parte de su exposición a ETH. La relación de garantía de su Trove también mejorará después de un canje.

### ¿Cómo puedo evitar que me rediman?

La mejor manera de evitar ser redimido es manteniendo una alta proporción de garantías en relación con el resto de los Trove en el sistema. Recuerde: los Troves más riesgosos (es decir, los Troves con menor garantía) son los primeros en la fila cuando se lleva a cabo un canje.

\
