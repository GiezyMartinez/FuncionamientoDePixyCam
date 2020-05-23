<header>
 <h1>PIXYCAM: Sensor de vision 2D</h1>
</header>
<body>
  <h2>¿Qué es Pixycam?</h2>
  <p>Si desea que su robot realice una tarea como recoger un objeto, perseguir una pelota, ubicar una estación de carga, etc., y desea un solo sensor para ayudar a realizar todas estas tareas, entonces la visión es su sensor. Los sensores de visión (imagen) son útiles porque son muy flexibles. Con el algoritmo correcto, un sensor de imagen puede detectar o detectar prácticamente cualquier cosa. Pero hay dos inconvenientes con los sensores de imagen: 1) producen muchos datos, docenas de megabytes por segundo y 2) procesar esta cantidad de datos puede abrumar a muchos procesadores. Y si el procesador puede mantenerse al día con los datos, gran parte de su potencia de procesamiento no estará disponible para otras tareas.

Pixy aborda estos problemas combinando un potente procesador dedicado con el sensor de imagen. Pixy procesa imágenes desde el sensor de imagen y solo envía la información útil a su microcontrolador. Y lo hace a velocidad de cuadro (50 Hz). La información está disponible a través de una de varias interfaces: serie UART, SPI, I2C, USB o salida digital / analógica. Por lo tanto, su Arduino u otro microcontrolador puede hablar fácilmente con Pixy y aún tener un montón de CPU disponible para otras tareas.

Es posible conectar múltiples Pixys a su microcontrolador, por ejemplo, un robot con 4 Pixys y 360 grados de detección. O use Pixy sin un microcontrolador y use las salidas digitales o analógicas para activar eventos, interruptores, servos, etc.</p>
</body>

