<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
  </head>
  <header>
 <table border="0">
  <tr>
    <td style="border: hidden"><h1>PIXYCAM: Sensor de vision 2D</h1></td>
   <td style="border: hidden"><img src="https://cdn-tienda.bricogeek.com/4345-thickbox_default/camara-pixy-cmucam5.jpg" width="400" height="350"></td>
  </tr>  
 </table>
</header>
<body>
 <br>
 <h2>INTRODUCCIÓN</h2>
 <h2>DELIMINTACIÓN DEL PROBLEMA</h2>
 <h2>OBJETIVOS</h2>
 <h2>MARCO TEÓRICO</h2>
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
<h3>Especificaciones técnicas</h3>
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
<img src="https://github.com/GiezyMartinez/Proyecto-Final-PixyCam/blob/master/imagenes/especificaciones.jpg">
<br>
<h3>Firmeware</h3>
<h3>¿Como se utiliza?</h3>
<h2>Ejemplo</h2>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
  </body>
<footer>https://www.mouser.mx/Search/Refine?N=4294013638&Keyword=LPC4330&FS=True&Tb=datasheets</footer>
</html>

