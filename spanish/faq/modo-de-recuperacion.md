# Modo de recuperación

### ¿Qué es el Modo Recuperación?

El modo de recuperación se activa cuando el Índice de Garantía Total (IGT) del sistema cae por debajo del 150 %.

### Durante el modo de recuperación, se pueden liquidar Troves con una relación de garantía inferior al 150 %.

Además, el sistema bloquea las transacciones de los prestatarios que disminuirían aún más el IGT. Solo se pueden emitir nuevos LUSD ajustando los Troves existentes de una manera que mejore su índice de garantía, o abriendo un nuevo Trove con un índice de garantía> = 150%. En general, si el ajuste de un Trove existente reduce su índice de garantía, la transacción solo se ejecuta si el TCR resultante es superior al 150%.

### ¿Cuál es el Índice de Garantía Total?

El Índice de Garantía Total o IGT es la relación entre el valor en dólares de la garantía del sistema completo al precio actual de ETH:USD, a la deuda del sistema completo. En otras palabras, es la suma de la garantía de todos los Troves expresada en USD, dividida por la deuda de todos los Troves expresada en LUSD.

### ¿Cuál es el propósito del modo de recuperación?

El objetivo del modo de recuperación es incentivar a los prestatarios a comportarse de manera que eleven rápidamente el IGT por encima del 150 % e incentivar a los titulares de LUSD a reponer el fondo de estabilidad.

Económicamente, el modo de recuperación está diseñado para fomentar la recarga de garantías y el pago de deudas, y también actúa como un elemento disuasorio de autonegación: la posibilidad de que ocurra en realidad aleja al sistema de alcanzarlo. El modo de recuperación no es un estado deseable para el sistema.

### ¿Cuáles son las tarifas durante el modo de recuperación?

Si bien el Modo de recuperación no tiene impacto en la tarifa de reembolso, la tarifa de préstamo se establece en 0% para alentar al máximo el préstamo (dentro de los límites descritos anteriormente).

### ¿Cómo puedo hacer que mi Trove sea seguro en modo de recuperación?

Al aumentar su índice de garantía al 150% o más, su Trove estará protegido contra la liquidación. Esto se puede hacer agregando garantías, pagando la deuda o ambos.\


### ¿Puedo ser liquidado si mi índice de garantía es inferior al 150 % en el modo de recuperación?

Sí, se le puede liquidar por debajo del 150 % si el índice de garantía de su Trove es inferior al 150 %. Para evitar la liquidación en Modo Normal y Modo de Recuperación, un usuario debe mantener su índice de garantía por encima del 150%.\


### ¿Cómo funcionan las liquidaciones en Modo Recuperación?

* IGI= Índice de Garantía Individual
* IMG= Índice Mínimo de Garantía
* IGT= Índice de Garantia Total
* FE= Fondo de Estabilidad

<table data-header-hidden><thead><tr><th width="374"></th><th></th></tr></thead><tbody><tr><td>Condición</td><td>Comportamiento al Liquidar</td></tr><tr><td>IGT&#x3C;=100%</td><td>Redistribuye todas las deudas y garantías (menos la compensación de gas) a Troves activos.</td></tr><tr><td>100% &#x3C; IGI &#x3C; IMG &#x26; FE LUSD > Deuda</td><td>LUSD en el Fondo de Estabilidad igual a la deuda de Trove se compensa con la deuda de Trove. La garantía ETH de Trove (menos la compensación de gas ETH) se comparte entre los depositantes.</td></tr><tr><td>100% &#x3C; IGI &#x3C; IMG &#x26; FE LUSD &#x3C; Deuda</td><td>El LUSD del Fondo de Estabilidad total se compensa con una cantidad igual de deuda del Trove. Una fracción de la garantía de Trove (igual a la relación entre su deuda compensada y su deuda total) se comparte entre los depositantes. La deuda restante y la garantía (menos la compensación de gas ETH) se redistribuyen a Troves activos.</td></tr><tr><td>IMG &#x3C;= IGI &#x3C; 150% &#x26; FE LUSD >= Deuda</td><td>El LUSD del Fondo de Estabilidad se compensa con una cantidad igual de deuda del Trove. Una fracción de la garantía de ETH con un valor en dólares igual a 1,1 * deuda se comparte entre los depositantes. Nada se redistribuye a otros tesoros activos. Dado que su IGI fue > 1,1, el Trove tiene un remanente de garantía, que se envía a CollSurplusPool y es reclamable por el prestatario. El Trove está cerrado.</td></tr><tr><td>IMG &#x3C;= ICR &#x3C; 150% &#x26; FE LUSD &#x3C; Deuda</td><td>No es necesaria ninguna acción</td></tr><tr><td>IMG >= 150%</td><td>No es necesaria ninguna acción</td></tr></tbody></table>

### ¿Cuánto de una garantía de Troves se puede liquidar en modo de recuperación?

En el modo de recuperación, la pérdida por liquidación tiene un tope del 110 % de la garantía de Trove. Cualquier remanente, es decir, la garantía por encima del 110 % (y por debajo del IGT), puede ser reclamado por el prestatario liquidado mediante la interfaz web estándar.

Esto significa que un prestatario se enfrentará a la misma "penalización" de liquidación (10 %) en el modo de recuperación que en el modo normal si su Trove se liquida.\
