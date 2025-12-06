# Plataforma Stack M5 - Cardputer
![img](https://github.com/user-attachments/assets/66189f7e-0da0-4a03-8068-3cbbdf059fd6)


La placa Cardputer de Stack M5 es un producto propio para estudiantes, ingenieros o cualquier entusiasta de la computacion. Este producto es una microcomputadora portatil impulsada por un ESP32-S3. Destaca por su diseño compacto, teclado QWERTY completo, pantalla TFT a color, conectividad Wi-Fi/Bluetooth, altavoz, micrófono, ranura MicroSD y emisor IR, ideal para proyectos de IoT y desarrollo gracias a su potente procesador de doble núcleo y bajo consumo, con compatibilidad LEGO y puertos de expansión Grove.

Características principales
Procesador: ESP32-S3 de doble núcleo (Xtensa LX7).
Pantalla: LCD TFT de 1.14 pulgadas (135x240).
Teclado: QWERTY de 56 teclas con respuesta táctil.
Memoria: 16MB Flash, 8MB PSRAM.
Conectividad: Wi-Fi 2.4GHz, Bluetooth 5.0 LE.
Audio: Micrófono MEMS digital y altavoz integrado.
Almacenamiento: Ranura para tarjeta MicroSD.
Expansión: Interfaz USB Type-C, puertos Grove, compatibilidad con LEGO (agujeros).
Sensores/Control: Emisor de infrarrojos (IR).
Batería: Batería de litio integrada (varios modelos).
Botones: Encendido/apagado, reinicio, y otros.
Funciones: Incluye apps preinstaladas como escaneo Wi-Fi, toma de notas, control remoto IR. 
Ideal para
Ingenieros y desarrolladores.
Proyectos de Internet de las Cosas (IoT).
Wearables y dispositivos portátiles.
Automatización del hogar (control IR). 

# Capitulo 1. Inicio en Arduino R4.
El primer punto con la tarjeta es instalar el software el IDE de Arduino, se recomienda usar una versión reciente. Al momento es tiene la version 2.3.6 (considerando una instalacion de Windows):

<img width="863" height="582" alt="AcercaDe" src="https://github.com/user-attachments/assets/ab6ff512-6a90-4902-9a30-5873e09a9a49" />

https://www.arduino.cc/en/software

Una vez instalado el software, hay que configurar dos puntos importantes; la placa, en este la placa Arduino UNO R4 WiFi y el puerto conectado en la PC como se muestran en las imagenes.
<img width="954" height="584" alt="boardR4" src="https://github.com/user-attachments/assets/67fcb500-4443-41da-9292-bc6d15f82d3f" />
<img width="948" height="583" alt="PuertoR4" src="https://github.com/user-attachments/assets/2f6de195-a4ea-4b75-a365-3ccc469463d6" />

Posteriormente sera necesario instalar las librerias correspondientes a los elementos a conectar en el circuito de la tarjeta, para ello en el menu indicado encontrar el dispositivo para instalar:
<img width="891" height="501" alt="lib01" src="https://github.com/user-attachments/assets/65a7da02-5637-4138-a778-51c96717b68a" />
<img width="891" height="502" alt="lib02" src="https://github.com/user-attachments/assets/38e297ab-03e1-4f32-b659-7fc339ff6011" />

```
/* ejemplo 01
#include "Arduino_LED_Matrix.h"
#include "01.h"

ArduinoLEDMatrix matrix;

void setup() {
	Serial.begin(115200);
	matrix.loadSequence(animation);
	matrix.begin();
	matrix.play(true);
}

// the loop function runs over and over again until power down or reset
void loop() {

}*/

#include "Arduino_LED_Matrix.h"

ArduinoLEDMatrix matrix;

void setup() {
	Serial.begin(115200);
	matrix.begin();
}

uint8_t frame[8][12] = {
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 },
  { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 }
};

void leftEye() {
	//Left eye
	frame[1][3] = 1;
	frame[1][4] = 1;
	frame[2][3] = 1;
	frame[2][4] = 1;
}

void wink() {
	//Wink with the left eye
	frame[1][3] = 0;
	frame[1][4] = 0;
	frame[2][3] = 1;
	frame[2][4] = 1;
}

void rightEye() {
	//Right eye
	frame[1][8] = 1;
	frame[1][9] = 1;
	frame[2][8] = 1;
	frame[2][9] = 1;
}

void mouth() {
	//Mouth
	frame[5][3] = 1;
	frame[5][9] = 1;
	frame[6][3] = 1;
	frame[6][4] = 1;
	frame[6][5] = 1;
	frame[6][6] = 1;
	frame[6][7] = 1;
	frame[6][8] = 1;
	frame[6][9] = 1;
}

void loop() {
	leftEye();
	rightEye();
	mouth();

	matrix.renderBitmap(frame, 8, 12);

	delay(1000);
	wink();

	matrix.renderBitmap(frame, 8, 12);
	delay(1000);
}
```

Enlaces utiles:

https://docs.arduino.cc/hardware/uno-r4-wifi/ 

https://github.com/arduino/uno-r4-library-compatibility

https://docs.arduino.cc/tutorials/uno-r4-wifi/cheat-sheet/

https://docs.arduino.cc/tutorials/uno-r4-wifi/led-matrix/
