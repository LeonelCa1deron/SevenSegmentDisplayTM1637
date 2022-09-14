![](cooltext419192499420428.png)

![](Logo.png)

## Instituto Tecnológico de Tijuana.

## Departamento de Sistemas y Computación.

## Actividad: Presentación del Módulo: Seven Segment Display - TM1637 mediante GitHub Pages.

## Asignatura: Sistemas Programables.

## Unidad: I.

## Docente: M.C. René Solís Reyes.

## Alumno & NoControl: Calderón Gastelum Sergio Leonel - 18212153.

## Grupo: SC7A.

## Fecha: 11/Septiembre/2022

============================================================================================

![](Cool419192750433595.png)

## ¿Qué es el Seven Segment Display TM1637?
Es un driver para display de LED de 7 segmentos y teclado, el cual es sumamente popular debido a su precio económico y muy factible de usar, tanto a nivel electrónico como a nivel de software.
La comunicación con este dispositivo es del tipo serie de dos hilos: una línea para una señal de reloj y otra línea para la información. TM1637 utiliza su propio protocolo TWSI. Al disponer de resistencias pull-up en las líneas de reloj y datos, cuando las comunicaciones se encuentran inactivas el nivel de la señal es alto. Para realizar las pruebas no es crítico pero para el funcionamiento normal sí es relevante considerar que debe establecerse el estado de alta impedancia en los pines de comunicaciones del microcontrolador para enviar un valor 1, y no un nivel alto de salida, ya que serán las resistencias las responsables de subir el nivel en la línea de comunicaciones.

![](TM1637.jpg)

## ¿Cuáles son su Características?
*  Voltaje de alimentación: 3.3 a 5 VDC
*  Consumo de corriente a 5V: 30 mA (nominal) / 80 mA (máxima)
*  Registro de desplazamiento: 74HC595
*  Tamaño del digito: 0.56 inch
*  Color display: Rojo
*  Dimensiones: 42x24x12 mm
*  Temperatura de funcionamiento: -40° C a 80° C

## ¿Cómo funciona?
El módulo funciona por medio de sólo 4 conexiones: dos de energía, una para la señal de reloj y una para datos. Esto reduce considerablemente las conexiones que usualmente tendríamos que hacer para usar cuatro displays de 7 segmentos como estos. Los datos se ingresan al módulo por medio de comunicación serial, de ahí que sólo un pin es necesario para datos, mientras tanto el pin de reloj define el tiempo en que se envían tales datos.
A continuación se describen las conexiones del módulo:
*  VCC = Referencia positiva de 3.3 V a 5V
*  GND = Referencia negativa
*  DIO = Entrada serial de datos
*  CLK = Entrada de  señal de reloj

![](Conexión con Arduino.png)

El envío de los datos al módulo es más bien simple, el fabricante del chip da un instructivo para esto en el data sheet con el fin de que podamos programarlo en un microcontrolador. Para Arduino, el fabricante provee ya una librería con el fin de que podamos mandar datos a nuestro display de la forma más sencilla posible, la librería tiene el nombre de "TM1637.h".

## Diagrama electrónica del TM1637
![](Diagrama.png)

## Referencias Consultadas.
*  https://www.makerelectronico.com/display-tm1637-4-digitos-7-segmentos/#:~:text=El%20TM1637%20es%20un%20driver,como%20a%20nivel%20de%20software.
*  https://www.arcaelectronica.com/blogs/tutoriales/display-de-7-segmentos-tm1637-con-arduino
*  https://www.vistronica.com/display/modulo-tm1637-con-display-4-digitos-7-segmentos-detail.html
*  https://www.puntoflotante.net/TM1637-7-SEGMENT-DISPLAY-FOR-MICROCONTROLLER.htm
