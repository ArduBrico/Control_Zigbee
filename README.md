🆕 Versión 1.0.0 – Configuración completa vía WiFiManager.

Esta versión marca un gran salto en flexibilidad, ya que permite configurar el dispositivo sin modificar el código fuente, directamente desde un portal web alojado en el propio ESP8266.

🚀 Novedades principales

🔧 Portal de configuración WiFiManager:

Selección de red WiFi y contraseña.

Introducción de la IP y puerto del servidor MQTT (Home Assistant).

Configuración de nombre y umbral de potencia para cada uno de los 3 enchufes Zigbee.

💾 Persistencia de configuración:

Todos los datos se guardan en la memoria interna (LittleFS), incluso tras reinicios o actualizaciones OTA.

🔌 Control de enchufes Zigbee:

El ESP se suscribe a los estados y potencia de cada enchufe.

Puedes encender/apagar desde un botón físico o desde Home Assistant.

Si el enchufe está encendido y supera un umbral de potencia, el LED parpadea.

📡 Actualización OTA desde Home Assistant:

Publicación automática de una entidad update usando MQTT Discovery.

Descarga segura desde GitHub del nuevo firmware.

🛠 Configuración inicial
Enciende el dispositivo se abrirá automáticamente.

Conéctate a la red WiFi creada por el ESP (Control Zigbee XXXXX) y accede al portal web.

Si no se abre el potal, mantén pulsado el botón del primer enchufe durante 10 segundos para abrir el portal de configuración.

Un vez abierto el portal introduce:

Red WiFi y contraseña.

IP y puerto del broker MQTT.

Nombre y umbral (en W) de cada enchufe.

Guarda y reinicia. El dispositivo quedará conectado y funcional.

Configuración de los pines:

| Modelo       | Enchufe  | Pin Pulsador GPIO | Pin Pulsador D | Pin LED GPIO | Pin LED D |
| ------------ | -------- | ----------------- | -------------- | ------------ | --------- |
| **ESP8266**  | Enchufe1 | GPIO 4            | D2             | GPIO 13      | D7        |
|              | Enchufe2 | GPIO 5            | D1             | GPIO 12      | D6        |
|              | Enchufe3 | GPIO 0            | D3             | GPIO 15      | D8        |
|              |          |                   |                |              |           | 
| **ESP32**    | Enchufe1 | GPIO 23           | D23            | GPIO 22      | D22       |
|              | Enchufe2 | GPIO 21           | D21            | GPIO 19      | D19       |
|              | Enchufe3 | GPIO 18           | D18            | GPIO 5       | D5        |
|              |          |                   |                |              |           | 
| **ESP32-C3** | Enchufe1 | GPIO 2            | D2             | GPIO 3       | D3        |
| SuperMini    | Enchufe2 | GPIO 4            | D4             | GPIO 5       | D5        |
|              | Enchufe3 | GPIO 6            | D6             | GPIO 7       | D7        |

