
# Reporte de Laboratorio: Esquemas de Comunicación

# Daniel Juárez y Humberto de la Cruz

## Información de los Participantes

**Nombres y carné de la pareja**
* Daniel Juárez - 23709
* Humberto de la Cruz - 23735

**Nombres y carné de la otra pareja Colaboradores en Conmutación:**
* José Ruiz - 23719
* Gerardo Fernandez - 23763

---

## Respuestas a las Preguntas

### 1. ¿Qué esquema (código) fue más fácil de transmitir y por qué? ¿Qué esquema (código) fue más difícil de transmitir y por qué?
El código Morse fue el más fácil ya que usa pausas como delimitadores y su ritmo es más natural para nosotros el código de Baudot fue el más difícil por su longitud fija de 5 bits y para nosotros era complicado saber en que momento habia un silencio por asi decirlo por eso fue mucho mas dificil ya que no los podiamos interpretar bien el orden en el que estaban los silencios

### 2. ¿Qué esquema tuvo menos errores (incluir datos que lo evidencien)?
El esquema con menos errores fue el código Morse ya que sus pausas evitan confusiones como evidencia de 8 mensajes enviados en Morse 5 fueron entendidos perfectamente a la primera en cambio, con Baudot hubo muchos más fallos por eso confundir un solo 1 por un 0 cambiaba toda la letra entonces el mensaje perdía completamente el sentido original.

### 3. ¿Qué dificultades involucra el enviar un mensaje de forma “empaquetada”?
Para nosotros es que no se pueden pedir correcciones en tiempo real como el audio se envía completo, cualquier ruido o distracción se tiene que repetir toda la grabación desde el inicio por eso, procesar todos los tonos de corrido incrementa la carga entonces, es mucho más fácil perder la cuenta

### 4. ¿Qué posibilidades incluye la introducción de un conmutador en el sistema?
El uso de un conmutador permite:

- **Conectar varios nodos** mediante un único punto central.
- **Controlar el tráfico**, organizando el envío de mensajes y evitando conflictos.

### 5. ¿Qué ventajas y desventajas se tienen al agregar más conmutadores al sistema?

**Ventajas**

| Ventaja |  |
| :--- | :--- |
| **Mayor cobertura** | Permite conectar más dispositivos y cubrir mayores distancias|
| **Mejor distribución** | Reparte el tráfico para evitar saturación |
| **Escalabilidad** | Facilita agregar nuevos clientes |

**Desventajas**

| Desventaja ||
| :--- | :--- |
| **Más fallos posibles** | Un error en un conmutador puede afectar la comunicación. |
| **Mayor complejidad** | Requiere una mejor coordinación entre sí |

---

## Conmutación de Mensajes 3.1

**Distribución de roles:**

Para esta parte, los cuatro integrantes trabajamos juntos nos dividimos de la siguiente manera:
* **Cliente 1:** José Ruiz
* **Cliente 2:** Gerardo Fernández
* **Cliente 3:** Alexander de la Cruz
* **Conmutador:** Daniel Juárez

**Protocolo que utilizamos para comunicarnos:**

Para que el sistema funcionara de forma ordenada, definimos un protocolo simple basado en prefijos al inicio de cada nota de voz

*Ejemplo:* "Soy José, esto es para Alexander y la secuencia

**Reglas del protocolo:**

1. **Identificación del emisor y receptor:** Cada nota de voz comenzaba siempre diciendo el nombre del emisor y el nombre del receptor separados por la palabra para.

2. **Señal de listo:** Antes de enviar un mensaje, el cliente mandaba un mensaje de texto a su conmutador que decía ¿listo?. Si el conmutador respondía SÍ, entonces el cliente grababa y enviaba la nota de voz. Como regla, si no respondía en 10 segundos, se intentaba de nuevo.

3. **Confirmación de entrega:** Una vez que el conmutador reenviaba el mensaje al destinatario, le avisaba al emisor con un simple OK

4. **Cola de espera:** Si dos clientes querían enviar mensajes al mismo tiempo, el conmutador avisaba esoera al segundo cliente y lo retenía hasta terminar de reenviar el primero, por eso se evitaba la sobrecarga.