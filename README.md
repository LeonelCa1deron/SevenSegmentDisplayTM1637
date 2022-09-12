# ¿Qué es el Seven Segment Display TM1637?
Es un driver para display de LED de 7 segmentos y teclado, el cual es sumamente popular debido a su precio económico y muy factible de usar, tanto a nivel electrónico como a nivel de software.

![](TM1637.jpg)

#Ejemplo de Seven Segment Display TM1637 en Wokwi (Simulación).
A continuación se muestra un ejemplo utilizando el driver Seven Segment Display TM1637 para simular un reloj de 24 horas, tanto lo que es la codificación como su resultado; además se muestra el código documentado para analizar el funcionamiento de cada método e instrucciones:

************************************************************ Código ************************************************************

// include the SevenSegmentTM1637 library.
#include "SevenSegmentTM1637.h"
#include "SevenSegmentExtended.h"

/* initialize global TM1637 Display object
   The constructor takes two arguments, the number of the clock pin and the digital output pin:
  SevenSegmentTM1637(byte pinCLK, byte pinDIO);
*/
const byte PIN_CLK = 2;   // define CLK pin (any digital pin)
const byte PIN_DIO = 3;   // define DIO pin (any digital pin)
SevenSegmentExtended      display(PIN_CLK, PIN_DIO);

const unsigned int clockSpeed = 10000;    // speed up clock for demo

// run setup code
void setup() {
  Serial.begin(9600);         // initializes the Serial connection @ 9600 baud
  display.begin();            // initializes the display
  display.setBacklight(100);  // set the brightness to 100 %
  delay(1000);                // wait 1000 ms
};

// run loop (forever)
void loop() {

  byte hours    = 00;                           // initialize hours
  byte minutes  = 00;                           // initialize minutes

  for ( ; hours < 24; hours++) {                // count hours   up to 24
    for ( ; minutes < 60; minutes++) {          // count minutes up to 59
      display.printTime(hours, minutes, true);  // display time
      delay(60000 / clockSpeed);                // clock delay ms
    };
    minutes = 0;                                // reset minutes
  };
};

************************************************************ Pantallas de Resultados ************************************************************

![](Inicio de la Simulación (TM1637).PNG) 
![](Funcionamiento (TM1637).PNG)
