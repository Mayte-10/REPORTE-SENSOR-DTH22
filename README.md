# REPORTE-SENSOR-DTH22
## USO DEL SENSOR DTH22
### Reporte: Sensor DHT22 con Tarjeta ESP32

- Introducción

El sensor DHT22 es un dispositivo digital utilizado para medir temperatura y humedad relativa. Su combinación con la tarjeta ESP32 permite el monitoreo ambiental mediante transmisión y procesamiento de datos en tiempo real.

- Materiales Utilizados

  1. Sensor DHT22
  2. Tarjeta ESP32
  3. WOKWI SIMULATOR (https://wokwi.com) 

- PROCEDIMIENTO 

- Ingresar a  WOKWI SIMULATOR y seleccionar el microcontrolador ESP32

  ![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2021.14.00%20(1).jpeg)
  ![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.50.01.jpeg)

  
- Colocar el siguiente código

  
´´´#include "DHTesp.h"

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}´´´



- Seleccionar las bibliotecas correspondientes para el funcionamiento del código 
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.30.41.jpeg)


- Seleccionar el sensor DHT22 con el que se trabajará
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.31.10.jpeg)
- Conexión del DHT22 al ESP32 de acuerpo a pines, alimentacion y terminal de señal 
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.34.16.jpeg).
  
- Funcionamiento, se debe iniciar simulación

![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.32.59.jpeg).

El DHT22 envía datos digitales.
El ESP32 lee estas señales y las procesa para obtener valores de temperatura (°C) y humedad (%).



- Conclusión

El sensor DHT22 combinado con la ESP32 permite obtener mediciones precisas y estables de temperatura y humedad, siendo este un ejemplo de un sistema de adquisición de datos.


