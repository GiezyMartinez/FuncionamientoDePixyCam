<header>
 <h1>PIXYCAM: Sensor de vision 2D</h1>
</header>
<body>
  <h2>¿Qué es Pixycam?</h2>
  <p>Si desea que su robot realice una tarea como recoger un objeto, perseguir una pelota, ubicar una estación de carga, etc., y desea un solo sensor para ayudar a realizar todas estas tareas, entonces la visión es su sensor. Los sensores de visión (imagen) son útiles porque son muy flexibles. Con el algoritmo correcto, un sensor de imagen puede detectar o detectar prácticamente cualquier cosa. Pero hay dos inconvenientes con los sensores de imagen: 1) producen muchos datos, docenas de megabytes por segundo y 2) procesar esta cantidad de datos puede abrumar a muchos procesadores. Y si el procesador puede mantenerse al día con los datos, gran parte de su potencia de procesamiento no estará disponible para otras tareas.

Pixy aborda estos problemas combinando un potente procesador dedicado con el sensor de imagen. Pixy procesa imágenes desde el sensor de imagen y solo envía la información útil a su microcontrolador. Y lo hace a velocidad de cuadro (50 Hz). La información está disponible a través de una de varias interfaces: serie UART, SPI, I2C, USB o salida digital / analógica. Por lo tanto, su Arduino u otro microcontrolador puede hablar fácilmente con Pixy y aún tener un montón de CPU disponible para otras tareas.

Es posible conectar múltiples Pixys a su microcontrolador, por ejemplo, un robot con 4 Pixys y 360 grados de detección. O use Pixy sin un microcontrolador y use las salidas digitales o analógicas para activar eventos, interruptores, servos, etc.</p>
<br>
<h2>MCU</h2>
<p>
Procesador NXP LPC4330, es un microcontrolador basado en ARM Cortex-M4 para embebidos
aplicaciones que incluyen un coprocesador ARM Cortex-M0, hasta 264 kB de SRAM,
periféricos configurables avanzados como el temporizador configurable por estado / PWM
(SCTimer / PWM) y la interfaz Serial General-Purpose I / O (SGPIO), dos de alta velocidad
Controladores USB, Ethernet, LCD, un controlador de memoria externo y múltiples digitales y
periféricos analógicos El LPC4350 / 30/20/10 funciona a frecuencias de CPU de hasta 204
Megahercio.
 
El ARM Cortex-M4 es un núcleo de 32 bits que ofrece mejoras del sistema, como la baja potencia.
consumo, funciones de depuración mejoradas y un alto nivel de integración de bloques de soporte. los
La CPU ARM Cortex-M4 incorpora una tubería de 3 etapas, utiliza una arquitectura Harvard con
instrucción local separada y buses de datos, así como un tercer bus para periféricos, y
incluye una unidad interna de captación previa que admite ramificación especulativa. El brazo
Cortex-M4 admite procesamiento de señal digital de ciclo único e instrucciones SIMD. UNA
El procesador de punto flotante de hardware está integrado en el núcleo.

El coprocesador ARM Cortex-M0 es un núcleo de 32 bits energéticamente eficiente y fácil de usar que
es compatible con códigos y herramientas con el núcleo Cortex-M4. El coprocesador Cortex-M0 ofrece
Rendimiento de hasta 204 MHz con un conjunto de instrucciones simple y un tamaño de código reducido. En
LPC43x0, el multiplicador de hardware del coprocesador Cortex-M0 se implementa como un ciclo de 32
multiplicador iterativo.
</p>
<h2>Especificaciones técnicas</h2>
<ul>
 <li>Image sensor: Omnivision OV9715, 1/4“, 1280×800</li>
 <li>Lens field-of-view: 75 degrees horizontal, 47 degrees vertical</li>
 <li>Lens type: standard M12 (several different types available)</li>
 <li>Power consumption: 140 mA typical</li>
 <li>Power consumption: 140 mA typical</li>
 <li>Power consumption: 140 mA typical</li>
 <li>Power input: USB input (5V) or unregulated input (6V to 10V)</li>
 <li>RAM: 264K bytes</li>
 <li>Flash: 1M bytes</li>
 <li>Available data outputs: UART serial, SPI, I2C, USB, digital, analog</li>
 <li>Dimensions: 2.1” x 2.0“ x 1.4</li>
 <li>Weight: 27 grams</li>
</ul>
<br>
![Imagen1](https://docs.pixycam.com/wiki/lib/exe/fetch.php?cache=&media=wiki:img:pixy_back.jpg)
<br>
</body>
<footer>https://www.mouser.mx/Search/Refine?N=4294013638&Keyword=LPC4330&FS=True&Tb=datasheets</footer>

