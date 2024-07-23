# Préstamo

### ¿Por qué usaría Liquity para pedir prestado?

El protocolo de liquidez ofrece préstamos sin intereses y es más eficiente en términos de capital que otros sistemas de préstamo (es decir, se necesita menos garantía para el mismo préstamo). En lugar de vender Ether para tener fondos líquidos, puede usar el protocolo para bloquear su Ether, pedir prestado contra la garantía para retirar LUSD y luego pagar su préstamo en una fecha futura.

Por ejemplo: los prestatarios que especulan sobre futuros aumentos de precios de Ether pueden usar el protocolo para aprovechar sus posiciones de Ether hasta 11 veces, aumentando su exposición a los cambios de precios. Esto es posible porque LUSD puede tomarse prestado contra Ether, venderse en el mercado abierto para comprar más Ether.

Nota: Esta no es una recomendación sobre cómo usar Liquity. El apalancamiento puede ser arriesgado y debe ser utilizado sólo por personas con experiencia.

### ¿A qué te refieres con garantía?

La garantía es cualquier activo que un prestatario debe proporcionar para obtener un préstamo, actuando como garantía de la deuda. Actualmente, Liquity solo admite ETH como garantía.

### ¿Es Ether (ETH) la única garantía aceptada por Liquity?

Sí, ETH es el único tipo de garantía aceptado por Liquity.

### ¿Cómo puede el protocolo ofrecer préstamos sin intereses?

El protocolo cobra tarifas únicas de préstamo y canje que se ajustan algorítmicamente en función del último tiempo de canje. Por ejemplo: si se realizan más canjes (lo que significa que es probable que LUSD se negocie a menos de 1 USD), la tarifa de préstamo continuaría aumentando, lo que desalentaría los préstamos.

Otros sistemas (por ejemplo, MakerDAO) requieren tasas de interés variables para que los préstamos sean más o menos favorables, pero lo hacen implícitamente ya que los prestatarios no sentirán el impacto por adelantado. Dado que esto también debe gestionarse a través de la gobernanza, Liquity opta por un mecanismo de retroalimentación directa y totalmente descentralizado a través de tarifas únicas.

### ¿Cómo puedo pedir prestado con Liquity?

Para pedir prestado, debe abrir un Trove y depositar una cierta cantidad de garantía (ETH) en él. Entonces puede retirar LUSD hasta una proporción de garantía del 110%. Se requiere una deuda mínima de 2000 LUSD.

### ¿Que es un Trove?

Un Trove es donde saca y mantiene su préstamo. Cada Trove está vinculado a una dirección de Ethereum y cada dirección puede tener solo un Trove. Si está familiarizado con Vaults o CDP de otras plataformas, Troves tiene un concepto similar.

Troves mantiene dos saldos: uno es un activo (ETH) que actúa como garantía y el otro es una deuda denominada en LUSD. Puede cambiar la cantidad de cada uno agregando garantías o pagando la deuda. A medida que realiza estos cambios de saldo, la relación de garantía de su Trove cambia en consecuencia.

Puede cerrar su Trove en cualquier momento pagando completamente su deuda.(Se editó)

### ¿Tengo que pagar cuotas como prestatario?

Cada vez que retira LUSD de su Trove, se cobra una tarifa de préstamo única sobre el monto retirado y se agrega a su deuda. Tenga en cuenta que la tarifa de préstamo es variable (y determinada algorítmicamente) y tiene un valor mínimo de 0,5% en condiciones normales de operación. La tarifa es de 0 % durante el [Modo de Recuperación](https://liquity.gitbook.io/spanish/faq/modo-de-recuperacion). También se aplicará un cargo de reserva de liquidación de 200 LUSD, pero se le devolverá al pagar la deuda.

Otra consideración es el precio de LUSD en el momento del reembolso. Si en el momento en que desea pagar su préstamo, LUSD se cotiza a $1.02 en el mercado y necesita comprarlo, incurre en una 'comisión' del 2%. Puede evitar esto al tener sus fondos prestados fácilmente disponibles o al poder esperar a que LUSD regrese a la paridad.

### ¿Cómo se calcula la comisión de un préstamo?

La tarifa de préstamo se agrega a la deuda del Trove y se determina mediante una tasa base. La tasa de la comisión se limita a un rango entre 0,5% y 5% y se multiplica por la cantidad de liquidez utilizada por el prestatario.

Por ejemplo: la tarifa del préstamo es del 0,5 % y el prestatario quiere recibir 4000 LUSD en su monedero. Al cobrarle una tarifa de préstamo de 20 LUSD, el prestatario incurrirá en una deuda de 4220 LUSD después de agregar la Reserva de liquidación y la tarifa de emisión.

### ¿Cuándo debo devolver mi préstamo?

Los préstamos emitidos por el protocolo no tienen vencimiento. Puede dejar su Trove abierto y pagar su deuda en cualquier momento, siempre que mantenga una relación de garantía de al menos el 110 %.

### ¿Cuál es la relación de garantía?

Esta es la relación entre el valor en dólares de la garantía en su Trove y su deuda en LUSD. La relación colateral de su Trove fluctúa con el tiempo a medida que cambia el precio de Ether. Puede influir en la proporción ajustando la garantía y/o la deuda de su Trove, es decir, agregando más garantía ETH o pagando parte de su deuda.

Por ejemplo: Digamos que el precio actual de ETH es de $3000 y decides depositar 10 ETH. Si pide prestados 10.000 LUSD, la relación de garantía de su Trove sería del 300%.

![](https://lh6.googleusercontent.com/LfiLDDSCpftfaG6EkErYDnDs0OyI6qseScifxRQx3AAFnsZmMg80WmkiI4PoVIwxmMCSStoQ9ZZ-g8cOeFZfibX\_Or-jaw6iy3PAcxQsywz1uko8uy2P6tvcpThxdeeaGkrBZOIT0An-Lnu-bWNnLv16ZHJjDs9oJq25O-YM529mmSucQmpE3adLOEe3RA)

Si, en cambio, sacara 25 000 LUSD, su proporción sería del 120 %.

### ¿Cuál es la relación mínima de garantía (RMG) y el relación de garantía "recomendada"?

La relación mínima de garantía (o RMGpara abreviar) es la relación más baja de deuda a garantía que no desencadenará una liquidación en operaciones normales (también conocido como Modo Normal). Este es un parámetro de protocolo que se establece en 110%. Entonces, si su Trove tiene una deuda de 10,000 LUSD, necesitaría al menos $11,000 en Ether como garantía para evitar ser liquidado.

Para evitar la liquidación durante el modo de recuperación, se recomienda mantener la relación cómodamente por encima del 150 % (por ejemplo, 200 % o mejor 250 %).

### ¿Qué sucede si se liquida mi Trove?

Pierde su garantía a medida que su deuda se paga mediante la liquidación, es decir, ya no podrá recuperar su garantía al pagar su deuda. Por lo tanto, una liquidación da como resultado una pérdida neta del 9,09 % (= 100 % \* 10/110) del valor en dólares de su garantía.

### ¿Qué es la Reserva de Liquidación?

Cuando se abre un Trove y obtiene un préstamo, se reservan 200 LUSD como una forma de compensar los costos de gas para el remitente de la transacción en caso de que se liquide su Trove. La Reserva de liquidación es totalmente reembolsable si su Trove no se liquida y se le devuelve cuando cierra su Trove pagando su deuda. La Reserva de liquidación cuenta como deuda y se tiene en cuenta para el cálculo de garantía del Trove, lo que aumenta ligeramente los requisitos reales de garantía.

### ¿Qué sucede si se redime contra mi Trove?

Cuando se canjea LUSD, el ETH proporcionado al canjeador se asigna de los Trove(s) con el índice de garantía más bajo (incluso si está por encima del 110%). Si en el momento del rescate tiene el Trove con la proporción más baja, renunciará a parte de su garantía, pero su deuda se reducirá en consecuencia.

El valor en USD por el que se reduce su garantía ETH corresponde al monto nominal en LUSD por el que se reduce la deuda de su Trove. Puede pensar en los rescates como si alguien más estuviera pagando su deuda y recuperando una cantidad equivalente de su garantía. Como efecto secundario positivo, los canjes mejoran la relación colateral de los Troves afectados, haciéndolos menos riesgosos.

Los canjes que no reducen su deuda a 0 se denominan canjes parciales, mientras que los canjes que pagan por completo la deuda de Trove se denominan canjes completos. En tal caso, su Trove está cerrado y puede reclamar su excedente colateral y la Reserva de Liquidación en cualquier momento.

Supongamos que posee un Trove con 2 ETH garantizados y una deuda de 3200 LUSD. El precio actual de ETH es de $ 2,000. Esto pone su índice de garantía (CR) en 125% (= 100% \* (2 \* 2,000) / 3,200). Imaginemos que este es el CR más bajo en el sistema Liquity y veamos dos ejemplos de un rescate parcial y un rescate completo:

Ejemplo de redención parcial

Alguien canjea 1200 LUSD por 0,6 ETH y así paga 1200 LUSD de su deuda, reduciéndola de 3200 LUSD a 2000 LUSD. A cambio, se transfieren 0,6 ETH, por un valor de $1200, de su Trove al redentor. Su garantía baja de 2 a 1,4 ETH, mientras que su índice de garantía aumenta del 125 % al 140 % (= 100 % \* (1,4 \* 2000) / 2000).

Ejemplo de redención completa

Alguien canjea 6000 LUSD por 3 ETH. Dado que el monto redimido es mayor que su deuda menos 200 LUSD (apartados como reserva de liquidación), su deuda de 3200 LUSD se liquida por completo y su garantía se reduce en $3000 de ETH, lo que le deja una garantía de 0,5 ETH ( = 2 - 3000 / 2000).

### ¿Cómo puede ofrecer un índice de garantía tan bajo como 110%?

Al hacer que la liquidación sea instantánea y más eficiente, Liquity necesita menos garantías para proporcionar el mismo nivel de seguridad que protocolos similares que se basan en mecanismos de subasta prolongados para liquidar las garantías en las liquidaciones.

### ¿Cómo puedo aprovechar el apalancamiento?

Puede vender el LUSD prestado en el mercado por ETH y utilizar este último para recargar la garantía de su Trove. Eso le permite sacar y vender más LUSD y, al repetir el proceso, puede alcanzar el índice de apalancamiento deseado.

Suponiendo una estabilidad de precios perfecta (1 LUSD = $1), el índice de apalancamiento máximo alcanzable es 11x. Está dada por la fórmula:

Índice de Apalancamiento Máximo= (RMG/ RMG-100%) donde RMG es la relación mínima de garantía.

### ¿Por qué la garantía y la deuda de mi Trove aumentaron sin mi intervención?

Si se liquidan Troves y el Fondo de Estabilidad está vacío (o se vacía debido a la liquidación), cada prestatario recibirá una parte de la garantía y la deuda liquidada como parte de un proceso de redistribución.

\
