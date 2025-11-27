# REPORTE-SENSOR-DTH22
## USO DEL SENSOR DTH22
### Reporte: Sensor DHT22 con Tarjeta ESP32

## 1. Introducción

El sensor DHT22 es un dispositivo digital utilizado para medir temperatura y humedad relativa. Su combinación con la tarjeta ESP32 permite el monitoreo ambiental mediante transmisión y procesamiento de datos en tiempo real.

2. Materiales Utilizados

- Sensor DHT22

- Tarjeta ESP32

- WOKWI SIMULATOR (https://wokwi.com) 

# 2. PROCEDIMIENTO 

- Ingresar a  WOKWI SIMULATOR y seleccionar el microcontrolador ESP32

  ![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2021.14.00%20(1).jpeg)
  ![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.50.01.jpeg)

  
## 3. Colocar el siguiente código 

```#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

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
}```.


## 4. Seleccionar las bibliotecas correspondientes
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.30.41.jpeg)


## 5. Seleccionar el sensor DHT22
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.31.10.jpeg)
## 6. Conexión del DHT22 al ESP32
![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.34.16.jpeg).
  
## 7. Funcionamiento, se debe iniciar simulación

![](https://github.com/Mayte-10/REPORTE-SENSOR-DTH22/blob/main/WhatsApp%20Image%202025-11-23%20at%2020.32.59.jpeg).

El DHT22 envía datos digitales.
El ESP32 lee estas señales y las procesa para obtener valores de temperatura (°C) y humedad (%).



## 8. Conclusión

El sensor DHT22 combinado con la ESP32 permite obtener mediciones precisas y estables de temperatura y humedad, siendo este un ejemplo de un sistema de adquisición de datos.
