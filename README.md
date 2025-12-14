# Plataforma Stack M5 - Cardputer

![m5stack-cardputer](https://github.com/user-attachments/assets/842b5b2f-7e1a-4a76-b80d-76f2789bbaed)

La placa Cardputer de Stack M5 es un producto propio para estudiantes, ingenieros o cualquier entusiasta de la computacion. Esta es una computadora de bolsillo de arquitectura abierta siendo una opción perfecta para desarrollo de esta plataforma. El corazón de esta computadora es un microprocesador M5StampS3, mediante una mini tarjeta basada en chip ESP32-S3,  las características de esta computadora completa la convierten a una poderosa herramienta de doble núcleo, soporta Wi-Fi e integra varios periféricos capaces de manejar funciones rápidas.
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

# Inicio en Cardputer
El desarrollo de la programacion es flexible, puede ser en difentes formas:

* A traves del IDE de Arduino,
  
<img width="721" height="322" alt="m5cardputer_arduino" src="https://github.com/user-attachments/assets/b06583c2-ba9a-4538-98eb-05d4f45c775e" />

Se recomienda instalar la version 2.3.6 o alguna receciente para instalar las librerias de M5Cardputer

<img width="894" height="497" alt="M5Cardputer" src="https://github.com/user-attachments/assets/a2ebdeba-39e6-4fb5-bbe6-b52a826a5f61" />
<img width="895" height="502" alt="M5Cardputer2" src="https://github.com/user-attachments/assets/5878086d-8b47-4499-965c-79d90ca0162d" />
<img width="891" height="502" alt="M5Cardputer3" src="https://github.com/user-attachments/assets/4597fc96-b6ca-46f0-b350-69ed2f05c604" />

Una vez instaladas las librerias, se pueden compilar algunos ejemplos provistos en la plataforma de M5Stack.

![20251207_110827](https://github.com/user-attachments/assets/6f9b276f-c9b4-4e0f-9f1c-292bc4d62752)


* A traves de PlatformIO se puede programar tambien, lo principal es instalar la extensión en VS Code, crear un nuevo proyecto seleccionando la placa de StampS3 y framework de la familia de M5Stack  escribir tu código en src/main.cpp, compilarlo (✓), y luego subirlo (flecha) a tu dispositivo.
Igual que en las librerias de Aduino, para PlatforIO se reqieren tambien las librerias: M5Cardputer, M5GFX y M5Unified.

<img width="1365" height="718" alt="Cardputer_platforIO_lib" src="https://github.com/user-attachments/assets/fbab8454-4e57-4296-bbb6-03616c20a488" />

Una vez instalado PlatforIO, se compila el codigo de M5Stack.
<img width="976" height="644" alt="Cardputer_platforIO" src="https://github.com/user-attachments/assets/a2c8eb8d-0adb-4d1d-af63-15df13a14015" />

 * A traves de  UIFLOW se tiene una intefaz grafica para programar de una manera amigable, para ello se requiere cargar el software para registrarse:

   <img width="735" height="462" alt="Cardputer_uiFlow" src="https://github.com/user-attachments/assets/e8ee0f2f-edf0-4af1-9665-cefb3a831606" />   
   <img width="769" height="632" alt="Cardputer_uiFlow2" src="https://github.com/user-attachments/assets/eafa3f80-2f92-4ef0-ae90-e7477d8b704b" />
   <img width="1294" height="928" alt="Cardputer_uiFlow3" src="https://github.com/user-attachments/assets/733e575e-f44c-46e6-90e0-f7461dc24f85" />

* A traves de Python puede programar con este lenguaje, para ello hay que instalar el software por medio de la propia tarjeta del dispositivo.
<img width="605" height="450" alt="M5stack" src="https://github.com/user-attachments/assets/28a0d5da-b6ae-436f-9226-ed159871147d" />

en este link es posible descargar el software necesario
<img width="1299" height="605" alt="python01" src="https://github.com/user-attachments/assets/32a38267-a7cf-42a8-b71a-4046a4006df3" />
  El .UF2 que instala la unidad en la PC al abrir el instalador:
  <img width="654" height="398" alt="python02" src="https://github.com/user-attachments/assets/3c01fff7-aef3-48ad-b3b2-791ffb2cef30" />

es importante indicar que el boton  "GO" de lado izquierdo junto al interruptor debe ser presionado unos segundos antes de conectar el cable USB considerando que esta apagada antes del proceso de la Cardputer como lo muestra la imagen:
<img width="1800" height="1059" alt="python03" src="https://github.com/user-attachments/assets/512955b1-e980-4aff-beac-ea1e0e601c2e" />

una vez cargado el software en la unidad UF2 se muestra un icono que representa a la Cardputer ya instalada:
<img width="517" height="436" alt="python05" src="https://github.com/user-attachments/assets/e51f6f0c-75ad-4972-ac37-dd1138db90af" />

Y el software esta listo para programar en Python.

A nivel codigo fuente, los ejemplos representativos en Arduino/PlatformIO se comparten aqui; tomar en cuenta que el fuente de Arduino solo requieren la extesion *.INO. mientras en PlatformIO el modulo principal es main.cpp, ademas de proyecto de PlatformIO dentro de Visual Studio debe tener las estructuras src/ y include/ para compilar el proyecto.

* Reproductor MP3 
[cardputer_mp3.zip](https://github.com/user-attachments/files/24147898/cardputer_mp3.zip)
![img](https://github.com/user-attachments/assets/d6fa1b63-72c4-4c3f-bb44-6297fe434962)

* Display
[Cardputer_Display.zip](https://github.com/user-attachments/files/24152319/Cardputer_Display.zip)
![display](https://github.com/user-attachments/assets/4e086f8f-b62a-4d13-a2b0-a2b64bb4dabf)


  
