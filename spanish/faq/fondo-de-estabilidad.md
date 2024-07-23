# Fondo de Estabilidad

### ¿Qué es el Fondo de Estabilidad?

El Fondo de Estabilidad es la primera línea de defensa en el mantenimiento de la solvencia del sistema. Lo logra al actuar como fuente de liquidez para pagar la deuda de Troves liquidados, asegurando que el suministro total de LUSD siempre permanezca respaldado.

Cuando se liquida cualquier Trove, se quema una cantidad de LUSD correspondiente a la deuda restante del Trove del saldo del Fondo de Estabilidad para pagar su deuda. A cambio, toda la garantía del Trove se transfiere al Fondo de Estabilidad.

El Fondo de Estabilidad está financiado por los usuarios que le transfieren LUSD (llamados proveedores de estabilidad). Con el tiempo, los proveedores de estabilidad pierden una parte prorrateada de sus depósitos LUSD, mientras ganan una parte prorrateada de la garantía liquidada. Sin embargo, debido a que es probable que Troves se liquide con índices de garantía justo por debajo del 110%, se espera que los proveedores de estabilidad reciban un mayor valor en dólares de garantía en relación con la deuda que pagan.

### ¿Por qué debería depositar LUSD en el Fondo de Estabilidad?

Los proveedores de estabilidad obtendrán ganancias de liquidación (ver a continuación) y recibirán recompensas de adopción temprana en forma de tokens LQTY.

### ¿Qué son las liquidaciones?

Para garantizar que todo el suministro de monedas estables permanezca totalmente respaldado por garantías, se cerrarán (liquidarán) los Troves que se encuentren por debajo del índice mínimo de garantías del 110 %.

La deuda del Trove es cancelada y absorbida por el Fondo de Estabilidad y su garantía se distribuye entre los Proveedores de Estabilidad.

El propietario del Trove aún conserva la cantidad total de LUSD prestada, pero pierde \~10 % del valor general, por lo que es fundamental mantener siempre la proporción por encima del 110 %, idealmente por encima del 150 %.

### ¿Quién puede liquidar Troves?

Cualquiera puede liquidar un tesoro tan pronto como caiga por debajo de la relación mínima de garantía del 110 %. El iniciador recibe una compensación de gas (200 LUSD + 0,5% de la garantía de Trove) como recompensa por este servicio.

### ¿Cómo me compensan por liquidar un Trove?

La liquidación de Troves está relacionada con ciertos costos de gas que el iniciador debe cubrir. El costo por Trove se redujo mediante la implementación de liquidaciones por lotes de hasta 160 - 185 Troves, pero con el objetivo de garantizar que las liquidaciones sigan siendo rentables incluso en tiempos de aumento de los precios del gas, el protocolo ofrece una compensación de gas dada por la siguiente fórmula:

compensación de gas = 200 LUSD + 0,5% de la garantía de Trove (ETH)

Los 200 LUSD están financiados por una Reserva de Liquidación, mientras que la parte variable del 0,5 % (en ETH) proviene de la garantía liquidada, lo que reduce ligeramente la ganancia de liquidación para los Proveedores de Estabilidad.

### ¿Cómo me beneficio como Proveedor de Estabilidad de las liquidaciones?

Como las liquidaciones ocurren justo por debajo de una relación de garantía del 110%, lo más probable es que experimente una ganancia neta cada vez que se liquide un Trove.

Digamos que hay un total de 1 000 000 LUSD en el fondo de estabilidad y su depósito es de 100.000 LUSD.

Ahora, un Trove con una deuda de 200 000 LUSD y una garantía de 400 ETH se liquida a un precio de Ether de $545 y, por lo tanto, a una relación de garantía del 109 % (= 100 % \* (400 \* 545) / 200 000). Dado que su participación en el fondo es del 10 %, su depósito se reducirá en un 10 % de la deuda liquidada (20.000 LUSD), es decir, de 100.000 a 80.000 LUSD. A cambio, obtendrá el 10 % de la garantía liquidada, es decir, 40 ETH, que actualmente tiene un valor de $21 800. Su ganancia neta de la liquidación es de $1,800.

Tenga en cuenta que los depositantes pueden retirar inmediatamente la garantía recibida de las liquidaciones y venderla para reducir su exposición a ETH, si se espera que el valor en USD de ETH disminuya (para ver una excepción, consulte [¿Puedo retirar mi depósito cuando lo desee?](https://liquity.gitbook.io/spanish/faq/fondo-de-estabilidad#puedo-retirar-mi-deposito-cuando-quiera)).

### ¿Cómo me beneficio como proveedor de estabilidad de las recompensas de los primeros usuarios?

Primero debe abrir un Trove, pedir prestado LUSD y depositarlo en el Stability Pool. Después de realizar su depósito, comenzará a acumular una recompensa (en LQTY) proporcional al tamaño de su depósito de forma continua. La recompensa se calcula de acuerdo con el cronograma de recompensas y la tasa de soborno del front-end que utilizó para realizar el depósito. Las recompensas serán las más altas para los primeros usuarios del sistema.

En cualquier momento, puede retirar sus recompensas pendientes a su dirección de Ethereum.

### ¿Puedo retirar mi depósito cuando quiera?

Como regla general, se puede retirar el depósito realizado en el Fondo de Estabilidad en cualquier momento. No hay una duración mínima de bloqueo. Sin embargo, los retiros se suspenden temporalmente siempre que haya Troves liquidables con un índice de garantía inferior al 110% que aún no hayan sido liquidados.

### ¿Qué oráculo está utilizando para determinar el precio de ETH?

El protocolo utiliza el feed de precios [ETH:USD de Chainlink](https://feeds.chain.link/eth-usd), recurriendo al oráculo ETH:USD de [Tellor](https://www.tellor.io) en las siguientes condiciones (extremas):

* El precio de Chainlink no se ha actualizado durante más de 4 horas
* La llamada de respuesta de Chainlink se revierte, devuelve un precio no válido o una marca de tiempo no válida
* El cambio de precio entre dos actualizaciones consecutivas de precios de Chainlink es> 50%.

### ¿Puedo perder dinero al depositar fondos en el Fondo de Estabilidad?

Si bien las liquidaciones se producirán con una proporción de garantía muy por encima del 100 % la mayor parte del tiempo, es teóricamente posible que un Trove se liquide por debajo del 100 % en un colapso repentino o debido a una falla del oráculo. En tal caso, puede experimentar una pérdida ya que la ganancia colateral será menor que la reducción de su depósito.

Si LUSD cotiza por encima de $1, las liquidaciones pueden dejar de ser rentables para los proveedores de estabilidad, incluso con índices de garantía superiores al 100 %. Sin embargo, esta pérdida es hipotética ya que se espera que LUSD regrese a la paridad, por lo que la "pérdida" solo se materializa si retiró su depósito y vendió LUSD a un precio superior a $1.

Tenga en cuenta que aunque el sistema se audita diligentemente, nunca se puede excluir por completo un ataque o un error que resulte en pérdidas para los usuarios.

### ¿Qué sucede si el Fondo de Estabilidad está vacío cuando se producen las liquidaciones?

Si el Fondo de Estabilidad está vacío, el sistema utiliza un mecanismo de liquidación secundario llamado redistribución. En tal caso, el sistema redistribuye la deuda y la garantía de Troves liquidados a todos los demás Troves existentes. La redistribución de la deuda y la garantía se realiza en proporción al monto de la garantía del receptor Trove.

Aquí hay un ejemplo de nuestro [whitepaper](https://docsend.com/view/bwiczmy).

<table data-header-hidden><thead><tr><th width="91"></th><th width="87"></th><th width="97"></th><th width="79"></th><th width="93"></th><th width="85"></th><th width="85"></th><th width="99"></th><th width="84"></th><th width="108"></th></tr></thead><tbody><tr><td>Trove</td><td>Deuda</td><td>ETH en Garantia</td><td>Indice</td><td>Incremento de Deuda</td><td>Increment de Garantia</td><td>Nueva Deuda</td><td>Nueva Garantia</td><td>Nuevo Indice</td><td>Ganancia neta en USD</td></tr><tr><td>A</td><td>2000</td><td>1.5</td><td>150%</td><td>960</td><td>0.52</td><td>2960</td><td>2.02</td><td>136%</td><td>72</td></tr><tr><td>B</td><td>4000</td><td>4</td><td>200%</td><td>2560</td><td>1.38</td><td>6560</td><td>5.38</td><td>164%</td><td>192</td></tr><tr><td>C</td><td>6000</td><td>7</td><td>233%</td><td>4480</td><td>2.41</td><td>10480</td><td>9.41</td><td>180%</td><td>336</td></tr><tr><td>D</td><td>8000</td><td>4.3</td><td>108%</td><td>-8000</td><td>-4.30</td><td>0</td><td>0</td><td>n/a</td><td>-600</td></tr><tr><td>Total</td><td>20000</td><td>16.8</td><td>168%</td><td>0</td><td>0</td><td>20000</td><td>16.8</td><td>168%</td><td>0</td></tr></tbody></table>

\
