# REPORTE-SENSOR-DTH22
## USO DEL SENSOR DTH22
### Reporte: Sensor DHT22 con Tarjeta ESP32
1. Introducción

El sensor DHT22 es un dispositivo digital utilizado para medir temperatura y humedad relativa. Su combinación con la tarjeta ESP32 permite el monitoreo ambiental mediante " transmisión y procesamiento de datos " en tiempo real.

2. Materiales Utilizados

Sensor DHT22

Tarjeta ESP32

Resistencias y cables jumper

Software Arduino IDE o equivalente

[Insertar foto del material aquí]

3. Conexión del DHT22 al ESP32

La conexión típica es:

VCC → 3.3V del ESP32

GND → GND

DATA → Pin digital (ej. GPIO 4)
Se recomienda una resistencia de 10kΩ entre DATA y VCC.

[Insertar foto de conexiones aquí]

4. Funcionamiento

El DHT22 envía datos digitales mediante un protocolo de un solo hilo.
El ESP32 lee estas señales y las procesa para obtener valores de temperatura (°C) y humedad (%).

[Insertar foto del montaje o del sensor funcionando]

5.Código 
#include "DHTesp.h"


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
}


6. Conclusión

El sensor DHT22 combinado con la ESP32 permite obtener mediciones precisas y estables de temperatura y humedad, siendo ideal para proyectos de IoT, domótica y monitoreo ambiental.
