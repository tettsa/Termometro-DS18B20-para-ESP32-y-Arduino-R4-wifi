
Termómetro con sensor DS18B20 e indicador luminoso con LEDS WS2812 con ESP32 / Arduino UNO R4

Este proyecto está diseñado para crear un termómetro de respuesta inmediata. Transforma las lecturas digitales de temperatura ambiental o de líquidos tomado con el sensor DS18B20 en una barra de luz dinámica con leds neopixel DS18B20 que cambia de color según el calor detectado. Es ideal para tableros industriales, acuarios, servidores o sistemas de domótica.

¿Cómo funciona el código paso a paso?

1. Librerías de Control de Precisión: El sistema utiliza las librerías OneWire y DallasTemperature para comunicarse de manera digital y sin ruido con el sensor DS18B20. Para los efectos de iluminación avanzados, recurre a Adafruit_NeoPixel, permitiendo controlar individualmente cada LED de nuestra tira o aro WS2812B.
2. Matriz de Color Pre-calculada (DEGRADADO_TERMICO): Para garantizar un rendimiento óptimo tanto en placas ESP32 como en Arduino UNO R4 WiFi, el código no calcula los colores en tiempo real (lo cual consume procesador). En su lugar, utiliza una paleta de 24 colores guardados en memoria que van suavemente desde el azul profundo (frío), pasando por el verde (estable), hasta el rojo intenso (peligro).
3. Mapeo Inteligente (map): El programa toma el rango operativo configurado (por defecto de -10°C a 50°C) y lo divide proporcionalmente entre la cantidad de tus LEDs (24). Si el sensor detecta una temperatura baja, encenderá pocos LEDs de color azul; si la temperatura sube, la barra crecerá iluminándose en tiempo real hacia los colores cálidos.
4. Protección constrain: Añadimos un filtro de seguridad industrial. Si la temperatura llega a superar los 50°C o bajar de los -10°C, el software se asegura de no enviar datos erróneos a los LEDs, manteniendo el sistema 100% estable

Diagramas de conexión para realizar un termómetro con el sensor DS18B20, leds Neopixel de 24 bits y una esp32 o un Arduino UNO R4 Wifi. 

Diagrama para ESP32. Nota: Si usas la ESP32 para este proyecto te recomendemos inicialices el monitor serial a 115200 baud.
<img width="1512" height="1512" alt="image" src="https://github.com/user-attachments/assets/9629b05a-ed1d-4a52-ae8d-4c0e6eb87a1b" />
<img width="1512" height="1512" alt="image" src="https://github.com/user-attachments/assets/7b5f24fa-3724-4c4c-b4d6-e57cf99b4b0a" />

Diagrama para Arduino UNO R4 WIFI. Nota: Si usas el Arduino para este proyecto te recomendemos inicialices el monitor serial a 9600 baud.
<img width="1512" height="1512" alt="image" src="https://github.com/user-attachments/assets/7e712822-4d20-443b-bab3-c4ebcb2e8aa9" />
<img width="1512" height="1512" alt="image" src="https://github.com/user-attachments/assets/b8f908ae-6ead-4deb-953f-d65b0a9c8385" />

Listado de piezas para realizar el proyecto:
1 X [ARDUINO® UNO R4 WIFI](https://tienda.tettsa.gt/producto/arduino-uno-r4-wifi/) o 1 X [ESP32 DEVKITC](https://tienda.tettsa.gt/producto/esp32-devkitc-32e-espressif/)

