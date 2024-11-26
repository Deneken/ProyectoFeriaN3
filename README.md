# Informe #3 - Feria de Proyectos

### Integrantes
- *Yarenla Venegas*
- *Harold Deneken*
- *Danilo Negrete*

### Materiales y Componentes Utilizados

En este proyecto se utilizaron los siguientes materiales y componentes electrónicos:

- *15 cables normales*: Para realizar las conexiones entre los diferentes componentes.
- *4 cables Hembra/Macho*: Utilizados para realizar conexiones flexibles con los pines de la placa Arduino.
- *5 botones*: Para permitir la interacción del usuario con el sistema.
- *1 buzzer*: Utilizado para emitir sonidos en función de las interacciones.
- *2 Protoboards*: Para realizar las conexiones y montar el circuito de forma rápida y ordenada.
- *Arduino Boy con PLA impreso en 3D*: Placa Arduino personalizada con una carcasa impresa en 3D para mayor comodidad y protección.
- *Pantalla*: Para mostrar información al usuario (p. ej., mensajes, estado del sistema).
- *Arduino Uno*: Placa principal para controlar el sistema.


### Para integrar un módulo WiFi al proyecto de Doom en Arduino necesitamos un módulo WiFi (como el ESP8266) y conectar correctamente las líneas de comunicación con el Arduino

Componentes necesarios:

Arduino UNO
Módulo WiFi: ESP8266
Pantalla: Podría ser una OLED, TFT, o cualquier pantalla compatible.
Resistencias: (si usas ESP8266) divisores de voltaje para adaptar niveles lógicos de 5V a 3.3V.
Fuente de alimentación: Algunas placas ESP necesitan alimentación adicional para evitar fallos.
Cableado jumpers: Para conexiones.

- Esquema de conexión general:

Para ESP8266 (Ejemplo con ESP-01):

VCC (3.3V): Conecta al pin de salida de 3.3V del Arduino o fuente externa.
GND: Conecta al pin GND del Arduino.
CH_PD (Chip Enable): Conecta a 3.3V mediante una resistencia (10 kΩ suele ser suficiente).
TX (Transmisión): Conecta al RX (Recepción) del Arduino.
RX (Recepción): Conecta al TX del Arduino a través de un divisor de voltaje (5V → 3.3V).
GPIO0 y GPIO2: Normalmente no se usan en esta configuración básica, pero deben estar en alto (conectadas a 3.3V mediante resistencias pull-up).

- Pinout sugerido para comunicación:

Conexión por UART (Serial):
Arduino: RX → TX del módulo, TX → RX del módulo.
Velocidad típica de comunicación: 9600 o 115200 baudios.

Conexión I2C (si usas OLED o sensores):
SCL (Reloj): Pin A5 (Arduino UNO)
SDA (Datos): Pin A4 (Arduino UNO)

- Notas importantes:

Alimentación: Si usas un ESP8266, asegúrate de que recibe un suministro estable de 3.3V. Si el Arduino no puede proporcionarlo, usa un regulador externo (como el AMS1117).
Programación: Configura el ESP como cliente HTTP o WebSocket para comunicarte con el Arduino, según el método que uses para Doom (control remoto o conexión directa).
Software:
Usa la biblioteca WiFiClient para conectar el ESP a una red WiFi.



### Funcionamiento Básico:
- *Entrada*: Los botones permiten al usuario interactuar con el sistema.
- *Salida*: La pantalla muestra los resultados de la interacción y el buzzer emite sonidos dependiendo de las acciones del usuario.

## Instrucciones de Uso

Para reproducir este proyecto en tu entorno, sigue estos pasos:

1. *Conectar los componentes*:
   - Conecta los botones y el buzzer a la protoboard.
   - Asegúrate de que los cables Hembra/Macho estén correctamente conectados entre la placa Arduino y los componentes.
   - Conecta la pantalla según las especificaciones del modelo que estés utilizando (por ejemplo, una pantalla LCD o OLED).
   
2. *Subir el código a Arduino*:
   - Abre el archivo proyecto_festa.ino en el IDE de Arduino.
   - Selecciona la placa adecuada (Arduino Uno) y el puerto correcto.
   - Haz clic en el botón "Subir" para cargar el código.

3. *Ejecutar el Proyecto*:
   - Una vez cargado el código, el sistema debería funcionar automáticamente.
   - Interactúa con los botones para ver los cambios en la pantalla y escuchar los sonidos del buzzer.


### Justificación del Proyecto

El avance de la tecnología y la conectividad nos permite desarrollar proyectos innovadores que combinan hardware y software para ofrecer experiencias únicas. La integración de un módulo WiFi ESP8266 con una placa Arduino para ejecutar el videojuego Doom representando una oportunidad para explorar los límites de los microcontroladores y fomentar la creatividad en el ámbito de la electrónica y la programación.
Relevancia tecnológica.

El ESP8266 es un módulo ampliamente reconocido por su capacidad de conectividad WiFi y su versatilidad en aplicaciones de IoT. Su integración con Arduino permite la creación de proyectos que combinan capacidades de conectividad con control físico, ofreciendo una base para desarrollar aplicaciones innovadoras. En este caso, el proyecto se enfoca en una implementación única: ejecutar Doom, un clásico de los videojuegos, utilizando hardware de bajo costo y accesible.
Motivación educativa

- Este proyecto tiene un alto valor educativo al permitir:

    Comprender protocolos de comunicación: Implementar comunicación serial entre Arduino y el ESP8266.
    Explorar optimización de recursos: Adaptar el código de un videojuego clásico a las limitaciones de hardware.
    Aprender sobre conectividad WiFi: Configurar el ESP8266 para recibir comandos o datos desde una red inalámbrica.
    Fomentar la creatividad: Aplicar conocimientos técnicos en un proyecto lúdico que atraiga tanto a estudiantes como a desarrolladores.

- Impacto social y accesibilidad

La idea de correr un videojuego tan icónico como Doom en un microcontrolador abre un abanico de posibilidades, no solo en el ámbito del entretenimiento, sino también en la democratización del acceso a tecnologías avanzadas. Con un costo reducido, cualquier persona puede replicar y personalizar el proyecto, incentivando la experimentación tecnológica.

- Innovación y versatilidad

Este proyecto no solo revive un clásico del entretenimiento, sino que lo hace con herramientas modernas que no fueron concebidas para este propósito originalmente. Esta reinterpretación del hardware representa un desafío técnico que demuestra las capacidades y la flexibilidad del ESP8266, así como del Arduino, en contextos no tradicionales.

- Conexión con tendencias actuales

En un mundo cada vez más conectado, el proyecto aprovecha tecnologías WiFi para añadir funciones modernas, como la capacidad de interactuar con Doom de forma remota a través de una aplicación móvil o navegador. Esto lo alinea con tendencias como IoT y gamificación.

- Posibles extensiones

- El proyecto no se limita a la ejecución de Doom. La experiencia adquirida puede aplicarse a otras iniciativas, como:

    Sistemas de videojuegos personalizados.
    Plataformas de aprendizaje interactivo.
    Demostraciones tecnológicas para eventos y exposiciones.

## Conclusiones

Este proyecto nos permitió profundizar en el uso de componentes básicos de Arduino y en cómo combinar múltiples entradas y salidas para crear una interacción más rica con el usuario. Además, el diseño y fabricación de una carcasa impresa en 3D proporcionó una solución práctica para proteger y dar un acabado estético a nuestro sistema.

Durante el proceso, aprendimos sobre:
- La importancia de una correcta conexión de los componentes en el protoboard.
- Cómo utilizar las entradas y salidas de Arduino de manera efectiva.
- La versatilidad de las pantallas y los sonidos como métodos de retroalimentación en proyectos interactivos.

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Para más detalles, consulta el archivo [LICENSE](LICENSE).

## Contacto

Si tienes preguntas o comentarios sobre el proyecto, no dudes en ponerte en contacto con nosotros:

- *Yarenla Venegas*: [yaret11@gmail.com]
- *Harold Deneken*: [h.deneken31@gmail.com]
- *Danilo Negrete*: [negrete11tonces@gmail.com]