<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
  </head>
  <header>
 <table border="0" style="backgroup:blue">
  <tr>
    <td style="border: hidden"><h1>PIXYCAM: Sensor de vision 2D</h1></td>
   <td style="border: hidden"><img src="https://cdn-tienda.bricogeek.com/4345-thickbox_default/camara-pixy-cmucam5.jpg" width="400" height="350"></td>
  </tr>  
 </table>
</header>
<body>
 <br>
 <h2>Introduccion</h2>
  <p>El hecho de poder capturar el mundo en el que vivimos por medio de cámaras de video o fotográficas es increíble, y aún más, es el hecho de poder manipular toda la información que las imágenes pueden transmitir, como colores, formas, tamaños, texturas, etc. Y Pixycam hace eso posible, por esa razón se redacta este documento, para adentrarse al mundo de los sensores de visión, conocer su característica técnicas, descubrir cómo establecer la comunicación con un microcontrolador Arduino y sobre todo cómo codificar programas en el IDE arduino para hacer uso de los recursos que Pixycam provee.</p>
 <h2>Delimitación del problema</h2>
  <p>Se desea conocer qué funciones puede cumplir el módulo para el microcontrolador Arduino Pixycam y sus características técnicas. Además es necesario documentar cómo se realizan las conexiones físicas entre la cámara Pixycam y el microcontrolador. Y por último, se requiere analizar el código que se implementa para hacer uso de los recursos de dicho módulo.</p>
 <h2>Objetivos</h2>
  <p>General.

Comprender el correcto funcionamiento e implementación de la cámara Pixycam para poder implementarlo en proyectos futuros. 

Específicos.
<ul>
  <li>Conocer los alcances y limitaciones de dicho módulo.</li>
  <li>Conocer las características técnicas que tiene Pixycam.</li>
  <li>Comprender el proceso para conectar físicamente el módulo con el microcontrolador.</li>
  <li>Analizar el código fuente que permite la interacción de Pixycam y Arduino.</li>
 </ul> 
</p>
 <h2>Marco teórico</h2>
  <p>Arduino.

Arduino es una plataforma de creación de electrónica de código abierto, la cual está basada en hardware y software libre, flexible y fácil de utilizar para los creadores y desarrolladores. Esta plataforma permite crear diferentes tipos de microordenadores de una sola placa a los que la comunidad de creadores puede darles diferentes tipos de uso.

Para poder entender este concepto, primero vas a tener que entender los conceptos de hardware libre y el software libre. El hardware libre son los dispositivos cuyas 
 
especificaciones y diagramas son de acceso público, de manera que cualquiera puede replicarlos. Esto quiere decir que Arduino ofrece las bases para que cualquier otra persona o empresa pueda crear sus propias placas, pudiendo ser diferentes entre ellas pero igualmente funcionales a partir de la misma base.

El software libre son los programas informáticos cuyo código es accesible por cualquiera para que quien quiera pueda utilizarlo y modificarlo. Arduino ofrece la plataforma Arduino IDE (Entorno de Desarrollo Integrado), que es un entorno de programación con el que cualquiera puede crear aplicaciones para las placas Arduino, de manera que se les puede dar todo tipo de utilidades.

El Arduino es una placa basada en un microcontrolador ATMEL. Los microcontroladores son circuitos integrados en los que se pueden grabar instrucciones, las cuales las escribes con el lenguaje de programación que puedes utilizar en el entorno Arduino IDE. Estas instrucciones permiten crear programas que interactúan con los circuitos de la placa.

El microcontrolador de Arduino posee lo que se llama una interfaz de entrada, que es una conexión en la que podemos conectar en la placa diferentes tipos de periféricos. La información de estos periféricos que conectes se trasladará al microcontrolador, el cual se encargará de procesar los datos que le lleguen a través de ellos.

El tipo de periféricos que puedas utilizar para enviar datos al microcontrolador depende en gran medida de qué uso le estés pensando dar. Pueden ser cámaras para obtener imágenes, teclados para introducir datos, o diferentes tipos de sensores.

También cuenta con una interfaz de salida, que es la que se encarga de llevar la información que se ha procesado en el Arduino a otros periféricos. Estos periféricos pueden ser pantallas o altavoces en los que reproducir los datos procesados, pero también pueden ser otras placas o controladores.

Pixy.

Pixy (CMUcam5) es una asociación entre el Instituto de Robótica Carnegie Mellon y Charmed Labs. Pixy proviene de una larga línea de CMUcams, pero Pixy comenzó realmente como una campaña de Kickstarter . ¡Comenzó a enviarse en marzo de 2014 y desde entonces se ha convertido en el sistema de visión más popular de la historia! Pixy se financia exclusivamente a través de ventas, así que gracias por ayudar a que Pixy sea un. éxito.

Mcu que utiliza Pixycam.

Procesador NXP LPC4330, es un microcontrolador basado en ARM Cortex-M4 para embebidos aplicaciones que incluyen un coprocesador ARM Cortex-M0, hasta 264 kB de SRAM, periféricos configurables avanzados como el temporizador configurable por estado / PWM (SCTimer / PWM) y la interfaz Serial General-Purpose I / O (SGPIO), dos de alta velocidad Controladores USB, Ethernet, LCD, un controlador de memoria externo y múltiples digitales y periféricos analógicos El LPC4350 / 30/20/10 funciona a frecuencias de CPU de hasta 204 Megahercio.

El ARM Cortex-M4 es un núcleo de 32 bits que ofrece mejoras del sistema, como la baja potencia. consumo, funciones de depuración mejoradas y un alto nivel de integración de bloques de soporte. los La CPU ARM Cortex-M4 incorpora una tubería de 3 etapas, utiliza una arquitectura Harvard con instrucción local separada y buses de datos, así como un tercer bus para periféricos, y incluye una unidad interna de captación previa que admite ramificación especulativa. El brazo Cortex-M4 admite procesamiento de señal digital de ciclo único e instrucciones SIMD. UNA El procesador de punto flotante de hardware está integrado en el núcleo.

El procesador ARM Cortex-M0 es un núcleo de 32 bits energéticamente eficiente y fácil de usar que es compatible con códigos y herramientas con el núcleo Cortex-M4. El coprocesador Cortex-M0 ofrece Rendimiento de hasta 204 MHz con un conjunto de instrucciones simple y un tamaño de código reducido. En LPC43x0, el multiplicador de hardware del procesador Cortex-M0 se implementa como un ciclo de 32 multiplicador iterativo.
</p>
 <br>
  <h3>¿Qué es Pixycam?</h3>
  <p>Si desea que su robot realice una tarea como recoger un objeto, perseguir una pelota, ubicar una estación de carga, etc., y desea un solo sensor para ayudar a realizar todas estas tareas, entonces la visión es su sensor. Los sensores de visión (imagen) son útiles porque son muy flexibles. Con el algoritmo correcto, un sensor de imagen puede detectar o detectar prácticamente cualquier cosa. Pero hay dos inconvenientes con los sensores de imagen: 1) producen muchos datos, docenas de megabytes por segundo y 2) procesar esta cantidad de datos puede abrumar a muchos procesadores. Y si el procesador puede mantenerse al día con los datos, gran parte de su potencia de procesamiento no estará disponible para otras tareas.

Pixy aborda estos problemas combinando un potente procesador dedicado con el sensor de imagen. Pixy procesa imágenes desde el sensor de imagen y solo envía la información útil a su microcontrolador. Y lo hace a velocidad de cuadro (50 Hz). La información está disponible a través de una de varias interfaces: serie UART, SPI, I2C, USB o salida digital / analógica. Por lo tanto, su Arduino u otro microcontrolador puede hablar fácilmente con Pixy y aún tener un montón de CPU disponible para otras tareas.

Es posible conectar múltiples Pixys a su microcontrolador, por ejemplo, un robot con 4 Pixys y 360 grados de detección. O use Pixy sin un microcontrolador y use las salidas digitales o analógicas para activar eventos, interruptores, servos, etc.</p>
<br>
<h3>MCU</h3>
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
<h3>Análisis</h3>
<p>
¿Qué funciones realiza Pixycam?

Si desea que su robot realice una tarea como recoger un objeto, perseguir una pelota, ubicar una estación de carga, etc., y desea un sólo sensor para ayudar a realizar todas estas tareas, entonces la visión es su sensor. Los sensores de visión (imagen) son útiles porque son muy flexibles. Con el algoritmo correcto, un sensor de imagen puede detectar o detectar prácticamente cualquier cosa. Pero hay dos inconvenientes con los sensores de imagen: 1) producen muchos datos, docenas de megabytes por segundo y 2) procesar esta cantidad de datos puede abrumar a muchos procesadores. Y si el procesador puede mantenerse al día con los datos, gran parte de su potencia de procesamiento no estará disponible para otras tareas.

Pixy aborda estos problemas combinando un potente procesador dedicado con el sensor de imagen. Pixy procesa imágenes desde el sensor de imagen y solo envía la información útil a su microcontrolador. Y lo hace a velocidad de cuadro (50 Hz). La información está disponible a través de una de varias interfaces: serie UART, SPI, I2C, USB o salida digital / analógica. Por lo tanto, su Arduino u otro microcontrolador puede hablar fácilmente con Pixy y aún tener un montón de CPU disponible para otras tareas.

Es posible conectar múltiples Pixys a su microcontrolador, por ejemplo, un robot con 4 Pixys y 360 grados de detección. O use Pixy sin un microcontrolador y use las salidas digitales o analógicas para activar eventos, interruptores, servos, etc.

Especificaciones técnicas
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

Conectar Pixycam con Arduino.

Fuera de la caja, Pixy está listo para hablar con un Arduino. Envía información de bloque a Arduino a 1 Mbits / segundo, lo que significa que Pixy puede enviar más de 6000 objetos detectados por segundo o 135 objetos detectados por fotograma (Pixy puede procesar 50 fotogramas por segundo).

OK, para que Pixy y Arduino hablen entre sí, use el cable Arduino suministrado para conectar Pixy a su Arduino.
<table border="0" style="backgroup:blue">
  <tr>
    <td style="border: hidden"><img src="https://docs.pixycam.com/wiki/lib/exe/fetch.php?cache=&w=900&h=599&tok=70d996&media=wiki:img:ce5166e65a245cce097741efef288fe09b08da8a.jpg" width="400" height="350"></td>
   <td style="border: hidden"><img src="https://docs.pixycam.com/wiki/lib/exe/fetch.php?cache=&w=900&h=599&tok=07257a&media=wiki:img:2b73fb3a56aa3673396578f13e2496ef3ea06616.jpg" width="400" height="350"></td>
  </tr>  
 </table>

</p>
<br>
<img src="https://github.com/GiezyMartinez/Proyecto-Final-PixyCam/blob/master/imagenes/especificaciones.jpg">
  </body>
<footer>https://www.mouser.mx/Search/Refine?N=4294013638&Keyword=LPC4330&FS=True&Tb=datasheets</footer>
</html>

