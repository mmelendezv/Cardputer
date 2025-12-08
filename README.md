# Plataforma Stack M5 - Cardputer
![img](https://github.com/user-attachments/assets/66189f7e-0da0-4a03-8068-3cbbdf059fd6)


La placa Cardputer de Stack M5 es un producto propio  para estudiantes, ingenieros o cualquier entusiasta de la computacion. Esta es una computadora de bolsillo de arquitectura abierta siendo una opción perfecta en ingeniería. El corazón de esta computadora es un microprocesador M5StampS3, mediante una mini tarjeta de desarrollo basada en chip ESP32-S3. Las características de esta computadora completa la convierten a una poderosa herramienta de doble núcleo, soporta Wi-Fi e integra varios periféricos capaces de manejar funciones rápidas.

Cuenta con una batería interna de 120mAh y otra batería adicional de 1400mAh de litio (dentro de la base). Durante la carga de la batería interna hay un circuito protector de voltaje y corriente que automáticamente ajusta voltaje y corriente para la batería.
Tiene una bocina integrada, pantalla de 200x135 pixeles, un infrarrojo, una ranura de memoria micro SD para ampliar el almacenamiento; la base de la computadora incorpora un imán que permite montar a superficies de metal, pues la estructura es compatible con orificios de Lego, permitiendo a crear diseños de Lego. Tiene una bocina integrada, pantalla de 200x135 pixeles, un infrarrojo, una ranura de memoria micro SD para ampliar el almacenamiento.

En términos de expansión, hay un puerto Grove integrado, lo que permite la expansión de sensores I2C fácilmente.
 
Aplicaciones:
* Creación de prototipos.
* Verificación funcional. 
* Desarrollo de sistemas embebidos.
* Curva de aprendizaje rápida.
* Propio para comunicación inalámbrica de internet las cosas (IoT).
* Uso de diversas herramientas de programación: UIFlow, IDE de Arduino, MicroPython.
* Vasta gama de sensores I2C

Características principales


Características: 
* Microcontrolador ESP32-S3 de doble núcleo (Xtensa LX7).
* Pantalla: IPS TFT, 1.14 pulgadas, 240 x 135 píxeles.
* Memoria: 16MB Flash, 8MB PSRAM.
* 8 Conectividad Wi-Fi 2.4GHz, Bluetooth 5.0 LE.
* Batería: Internal 120mAh + 1400mAh (en la base).
* Rarura TF-Card (MicroSD).
* Interfaz USB Type-C, puertos Grove, compatibilidad con LEGO (agujeros).
* Teclado: 56 teclas , tipo QWERTY con respuesta  táctil. Botones: Encendido/apagado, reinicio, y otros.
* Sensores/Control: Emisor de infrarrojos (IR).
* Audio Micrófono SPM1423 MEMS digital.
* Sonido: bocina I2S de 8 ohmios a 1W.
* Interface HY2.0-4P para expander sensores I2C.

# Capitulo 1. Inicio en Cardputer
El desarrollo de la programacion es flexible, puede ser en difentes formas:
* A traves del IDE de Arduino, se recomienda instalar la version 2.3.6 o alguna receciente para instalar las librerias de M5Cardputer
<img width="894" height="497" alt="M5Cardputer" src="https://github.com/user-attachments/assets/a2ebdeba-39e6-4fb5-bbe6-b52a826a5f61" />
<img width="895" height="502" alt="M5Cardputer2" src="https://github.com/user-attachments/assets/5878086d-8b47-4499-965c-79d90ca0162d" />
<img width="891" height="502" alt="M5Cardputer3" src="https://github.com/user-attachments/assets/4597fc96-b6ca-46f0-b350-69ed2f05c604" />

Una vez instaladas las librerias, se pueden compilar algunos ejemplos provistos en la plataforma de M5Stack.
![20251207_110827](https://github.com/user-attachments/assets/6f9b276f-c9b4-4e0f-9f1c-292bc4d62752)

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
