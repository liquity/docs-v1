# Operadores de front-end

### ¿Por qué debería convertirme en un Operador Frontend?

Los operadores frontend proporcionan una interfaz web al usuario final que les permite interactuar con el protocolo Liquity. Por ese servicio, serán recompensados con una parte de los tokens LQTY que generen sus usuarios.

Las recompensas LQTY se otorgan a los depositantes del Fondo de Estabilidad y luego se comparten proporcionalmente entre los propios usuarios y el Operador Frontend. La cantidad que obtiene cada parte está determinada por la Tasa de Retorno que establece el Operador de frontend y puede oscilar entre 0% y 100%.

Establecer una tasa de retorno alta hará que el operador de frontend sea atractivo para los usuarios, pero ofrecer una interfaz agradable y funcionalidades adicionales podría permitir una tasa de soborno más baja sin dejar de atraer el interés de los usuarios.

Consulte el video [Liquity Runs on Decentralized Frontends](https://youtu.be/ipbNQMiIy1M) para obtener más detalles.

### ¿Cómo puedo hacer funcionar una interfaz?

Puede instalar nuestro [kit](https://github.com/liquity/liquity) de lanzamiento de front-end o integrar nuestro protocolo en su entorno utilizando nuestro [SDK de front-end](https://docs.liquity.org/documentation/sdk).

### ¿Qué tipo de recompensas recibo como frontend?

Las recompensas de frontend se pagan en LQTY. Obtenga más información sobre LQTY [aquí](https://liquity.gitbook.io/spanish/faq/general#que-son-lusd-y-lqty).

### ¿Cómo se calcula el reparto de recompensas de una interfaz?

Las recompensas se calculan en función de los depósitos totales etiquetados por la interfaz. En un evento de recompensa LQTY que genera LQTY\_d por un depósito d realizado a través de una interfaz con tasa de retorno, la interfaz recibe ((1-k)\*LQTY\_d) y el usuario recibe (k \* LQTY\_d).

### ¿De dónde vienen las recompensas de frontend?

Las recompensas de frontend provienen del mismo grupo que las recompensas de usuario. Las interfaces ganan una parte de los 32 000 000 LQTY que se distribuyen a los usuarios en función de la tasa de retorno de la interfaz y las recompensas totales acumuladas por sus usuarios.

### ¿Cómo se pagan las recompensas de frontend?

Cada depósito en el Fondo de Estabilidad está etiquetado por la dirección Ethereum del front-end a través del cual se realizó el depósito. Esta dirección es donde se acumulan las recompensas LQTY de la interfaz.

### ¿Cómo funcionan las etiquetas de frontend?

Se aplica una etiqueta de frontend a un depósito de Stability Pool cuando un usuario llama a provideToSP(uint \_amount, address \_frontEndTag). Esta etiqueta permanecerá adjunta al depósito de un usuario incluso si usa otra interfaz. La etiqueta también puede ser una dirección 0, lo que significa que el usuario recibirá el 100 % de sus recompensas LQTY acumuladas.

Para agregar una nueva etiqueta de interfaz y beneficiarse de una tasa de soborno diferente, un usuario deberá retirar completamente su depósito de Stability Pool y volver a depositar utilizando la nueva interfaz y la nueva etiqueta. Como Operador Frontend, es importante tener en cuenta esta dinámica.

### ¿Las interfaces tienen que ser aprobadas previamente?

No, registrarse con los contratos inteligentes de Liquity como interfaz es un proceso sin intermediarios. Esto se hace llamando a la función registerFrontEnd(uint\_kickbackRate) en el contrato inteligente del Fondo de Estabilidad. La tasa de retorno es un valor entre \[0,1] (por ejemplo, 0,8 = tasa de retorno del 80 %).

### ¿Cómo se agrega una interfaz al registro de liquity.org?

Las interfaces pueden ver el proceso de listado del [registro aquí](https://github.com/liquity/frontend-registry).

### ¿Cuál es la tasa de retorno?

Para garantizar que el protocolo de Liquity esté descentralizado desde el día 1, el equipo de Liquity no alojará ni ejecutará una interfaz para interactuar con los contratos de Liquity. Como tal, corresponde a los miembros de la comunidad de Liquity actuar como operadores de interfaz y ejecutar interfaces para los usuarios.

Para incentivar este comportamiento, cada Operador de Frontend puede establecer una tasa entre 0 y 100% que determina la fracción de LQTY que se pagará como retorno a los Proveedores de Estabilidad que utilizan el frontend. Si una interfaz establece la tasa de soborno en 60 %, sus usuarios recibirán el 60 % de las recompensas obtenidas, mientras que la interfaz recibe el 40 % restante.

### ¿Puede un Operador Frontend cambiar su tasa de sobornos?

Si y no. Una vez que una dirección se registra como frontend con Fondo de Estabilidad y tiene una tasa de soborno específica, no se puede cambiar.

Sin embargo, si un operador de frontend desea cambiar su tasa de retorno, debe registrar una nueva dirección de frontend con una nueva tasa de retorno. Para que los usuarios aprovechen la nueva tasa de retorno, deberán retirar su depósito y volver a depositar con la nueva etiqueta de interfaz.

### ¿Por qué el equipo de Liquidity no ejecuta una interfaz?

No ejecutar nuestra propia interfaz aumenta la resistencia a la censura y la descentralización, pero también nos ayuda a iniciar un ecosistema distribuido.
