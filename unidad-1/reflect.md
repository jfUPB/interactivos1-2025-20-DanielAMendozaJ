# Unidad 1

## 🤔 Fase: Reflect

### Actividad 7

#### Parte 1: recuperación de conocimiento (Retrieval Practice)

Basándote en los ejemplos que vimos de sistemas físicos interactivos al iniciar el curso, describe las tres características que definen a un sistema físico interactivo.

*Retomando los primeros ejemplos de SFI, tales como: trabajos de nuestros compañeros del semestre pasado, conciertos músicales y de audiovisuales y demás sistemas; las principales características y partes de un sistema físico interactivo son:*

1. Inputs: Son aquellas interacciónes que envian la información a la maquina para ser procesada
2. Procesamiento: Es el metodo de recopilación e interpretación de la información enviada desde los inputs, traducida y lista para ser "mostrada"
3. Outputs: Son el feedback que resulta de la interacción, en una pantalla sería lo que vemos, en un concierto lo que escuchamos, o en un programa serían el movimiento de una bola al rededor del mapa.

*Explica el modelo input-process-output de Patrick Hübner usando como ejemplo el sistema que construiste con micro:bit y p5.js en la Actividad 06. ¿Cuál fue el input, cuál fue el proceso y cuál fue el output?*

Input: La información se envia por medio del microbit (Botones "A" y "B") con los cuales se manejaba el cambio de color o el cambio de lugar, todo esto con la ayuda del código implementado al micro:bit
Proceso: EL proceso sería el código, puesto que es el que interpreta la llegada de los inputs y los transforma en acciones respectivas que permiten la visualización de los outputs; tambien los programas respectivos pues tambien permiten la comunicación entre los componentes de estos sistemas físicos interactivos.
Output: La visualización se representa por medio de la pantalla, en especifico la pantalla del programa P5js y los leds del micro:bit que permitían asegurarnos de que el programa funcionaba correctamente.

*¿Cuál es la función de la línea uart.write('A') en el código del micro:bit y qué función en p5.js se encarga de “escuchar” ese mensaje?*

uart.write('A') permite que al presiónar un botón dentro del micro:bit este sea leído e interpretado y reescrito como un variable que posteriormente se puede usar como valor por ejemplo en el caso de la bola para definir a que lado se movera según el botón apretado. Por otro lado la función encargada de esta linea de código es la función "Draw" que con lineas de código lee ese valor interpretado del port, de tal manera dando paso al resto del código y la interacción en general.

*¿Cuál es la diferencia fundamental entre el arte/diseño tradicional y el arte/diseño generativo?*

La principal diferencia es que el arte generativo al contrario que el modelo tradicional es capaz de ser "realizado" o "desarrollado" en sí en presencia y en vivo, esto pues a diferencia del estático arte tradicional que busca ser lo más parecido a la realidad, buscando copiar la vida misma; el arte generativo permite acercarnos más a interacciónes cambiantes acordes a sentimientos, emociones o fenómenos reales (en tiempo real)

*Imagina que quieres que un círculo en p5.js cambie a un color aleatorio cada vez que sacudes el micro:bit. Describe qué tendrías que programar en el micro:bit y qué tendrías que programar en p5.js para lograrlo.*

Tendría que en primer lugar darle un valor a esta "sacudida" que dentro del código del micro:bit me permita envíar la información al programa P5js
luego dentro de P5js debería conectar el port del micro:bit para recibir esa información. 
(debo añadir que tambien es necesario crear el círculo y el canvas donde se apreciará este hipotético círculo cambia color)
La información se interpreta, pero debemos buscar un condicional que nos permita especificar qué hará nuestro programa después de que la información llegue y sea descifrada. 


#### Parte 2: reflexión sobre tu proceso (Metacognición)

*¿Qué fue más desafiante para ti en esta unidad: la parte conceptual (entender qué es un sistema físico interactivo) o la parte técnica (hacer que el micro:bit y p5.js se comunicaran)? ¿Por qué?*

Considero que no hubo mucho problema con la retención de los conceptos, aún así la parte de comprender el código es un poco interesante pues requiere completa y total atención respecto al contexto total del desarrollo del programa, tanto por parte del programa de desarrollo (o Output) y el programa que envía la información (o Input) del resto de la actividad es bastante comprensible.

*Describe el momento “¡Aha!” que tuviste cuando lograste que una acción en el micro:bit (presionar un botón, sacudirlo) tuviera un efecto visible en el canvas de p5.js por primera vez. ¿Qué fue lo que entendiste en ese instante?*

El momento "¡Aha!" que tuve fue cuando mande el código al micro:bit, pues se me había olvidado que para que el programa funcione correctamente debería implementar todo el código del Micro:bit a parte del de P5js, entonces descubrí que el mayor inconveniente al momento de desarrollar este tipo de experiencias no son problemas técnicos, sino la falta de concentración total en cada parte individual de la experiencia.

*Al inicio de la unidad te pregunté: “¿Este curso para qué me sirve?”. Después de experimentar y construir tu primer prototipo, ¿Cómo ha cambiado o se ha vuelto más concreta tu respuesta a esa pregunta?*

Desde el ámbito o camino que pienso seguir este curso me ayuda bastante, pues me permite descubrir muchas formas de "arte" entre código, máquina y usuario, arte que puede mostrarle al mundo sentimientos, historias o experiencias de maneras espectaculares para despertar en las personas esa llama de curiosidad o de gratificación. Aún recuerdo ese programa de nuestra compañera del semestre superior con la canción de AURORA, fue algo maravilloso y sé que este curso me ayudara a implementar técnicamente aquellas emociones que despiertan en mi y enseñarselas a las personas.

*El tutorial de la Actividad 05 te llevó paso a paso. ¿Cómo te sentiste con ese método de aprendizaje? ¿Te dio seguridad o preferirías haberlo intentado por tu cuenta desde el principio?*

Es perfecto. A veces menos es más y en este caso más es mejor, desde mi punto de vista como aprendíz visual y práctico me fue muy conveniente esta metodología ya que aprendí perfectamente a realizar la actividad y no caí en sezgos distintos o interpretaciones que pudieron haberme confundido más. considero que aprender de esta manera influye en un proceso justo para el desarrollo de estas actividades y permite tener contexto para investigar más otras opciones.


### Actividad 8

Coevaluación: [Felipe Gonzales Tovar](https://editor.p5js.org/Feligonto/sketches/Pc9BI6wOb)
El desarrollo de la actividad es similar a la mía, su implementación usa createVector() para manejar la posición del círculo, lo cual es interesante porque permite tener un manejo más estructurado de coordenadas en dos dimensiones. También me parece positivo que haya incluido la lógica de conexión y desconexión del puerto (esto para la conección con los micro:bit), y que actualice el texto del botón según el estado, al igual que yo.

Una diferencia que noté es que en mi código implementé constrain() para evitar que el círculo se salga del canvas, mientras que en el suyo eso no está presente, lo que podría hacer que el círculo desaparezca si se mueve mucho.

Otro punto es que en su código el movimiento es de 1 píxel por entrada, lo cual es muy preciso pero un poco más lento visualmente. En el mío hice que se moviera 10 píxeles para notar mejor el cambio, aún así no noto mucho la diferencia ya que es una actividad, sin embargo puede servir más su modelo por presición si llegamos a estar en algún proyecto que requiera más de esta.

### Actividad 9

Continuar: ¿Qué actividad, video o ejemplo de esta unidad te resultó más inspirador o te ayudó más a entender el potencial de los sistemas físicos interactivos?
La actividad de la compañera del semestre anterior. Simplemente es maravilloso ver lo que puede generar dentro de una persona una experiencia que otra pudo crear y despertó en mi las ganas de seguir aprendiendo de este esplendido mundo.

Dejar de hacer: ¿Hubo alguna parte que te pareció demasiado abstracta, muy rápida o confusa? ¿Hay algo que crees que podríamos cambiar para que sea más claro?
Creo que el tema del "contexto" se debe tomar con mayor prioridad, pues al momento en el que una persona se descuide o pierda el hilo de las explicaciónes puede llegar a confundirse demaciado, sin embargo recalco que el docente puede y ha cumplido con resolver aquellas inquietudes al momento de quedar en blanco.

Empezar a hacer: ¿Qué te genera más curiosidad ahora? ¿Te gustaría explorar más sensores del micro:bit (luz, temperatura), crear visualizaciones más complejas en p5.js o ver más ejemplos de proyectos artísticos?
Me encantaría crear mis propias visualizaciones en P5js, es algo que me llamó mucho la atención y quiero explorar esta herramienta más. tambien debo decir que los videos y proyectos que nos muestran en las clases son motivo de inspiración y gratificación.

Balance inspiración vs. técnica: ¿Cómo sentiste el equilibrio entre ver los videos inspiradores de la Actividad 01 y la parte técnica de conectar las herramientas en las actividades 03-06?
Me sentí como si estuviera haciendo un cursito para llegar a ese nivel. muy principiante pero con mucha emoción pues se siente como aportar un granito de arena hasta por fin poder desarrollar mis propias experiencias; acompañamiento que nos ofrece el docente es algo que se aprecia demaciado, gracias a ello pude seguir la linea de actividades y aprendido correctamente el cómo se hacía cada una de ellas.

Comentario adicional: ¿Hay algo más que quieras compartir sobre tu experiencia en esta unidad introductoria?
Debo decir que también fue muy bueno poder compartir con mis compañeros, poder intercambiar ideas y aprender de cómo cada uno tiene su forma distinta de hacer los mismos procesos, fue bastante bueno compartir esas herramientas y ser evaluados entre nosostros. también aprecio la comprensión del docente, su paciecia, su actitud y emoción a la hora de enseñarnos todo esto. *Muchas gracias!*
