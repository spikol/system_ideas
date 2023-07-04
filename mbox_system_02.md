## mbox_system_01

July 4, 2023🇺🇸

### Bases

#### Uber-Base

The Uber-Base station controls the system. Also provides a simple visualisation of what is going on. 

| Tech           | Features          |
| -------------- | ----------------- |
| Linux Box      | WIFI              |
| Display        | BLE               |
| Keyboard Mouse | Ethernet          |
|                | Storage           |
|                | Influx / Graphing |
|                | MQTT Broker?      |

#### Vision-Base

Line of sight vision base, designed for capturing the April Tags, can work with wide angle cameras and the Owl Meeting Lab. Maybe also 360 like cameras.
| Tech         | Features                         |
| ------------ | -------------------------------- |
| Raspberry-Pi | Camera Wide angle or OWL meeting |
|              | Wifi                             |
|              | MQTT Broker/Client               |
|              | Ethernet                         |

#### Audio-Base simple and deluxe

This simple base station handles the Audio tags or runs the Jabra for collecting and processing audio data from sensors and badges. The deluxe model captures the streams from the Voice-Badge deluxe and perform VAD and SD.

| Tech                   | Features           |
| ---------------------- | ------------------ |
| Raspberry-Pi (simple)  | MQTT Client        |
| Nvidia Jetson (deluxe) | RFID Hat           |
| Unix Box (deluxe)      | BLE                |
|                        | Wifi               |
|                        | Jabra              |
|                        | MQTT Broker/Client |
|                        | Ethernet           |

#### Location-Base

This base is designed to track location with BLE or RFID and provide proximity information. BLE logging to deterime via triangulation the badges close by. Or using RFID (medium power) to capture the badges near by.

| Tech          | Features           |
| ------------- | ------------------ |
| Raspberry-Pi  | RFID Shield / Hat  |
| Arduino H7/H8 | BLE                |
|               | Wifi               |
|               | MQTT Broker/Client |
|               | Ethernet           |

### Badges

#### Vision-Badge

This badge uses April Tags and Arduino Nicla Vision board to capture proximity location. Plus audio and vibration data.

| Tech                 | Features            |
| -------------------- | ------------------- |
| Arduino Nicla Vision | Vision              |
| April Tag            | MQTT Client         |
| Battery              | Audio and Vibration |

#### Voice-Badge Deluxe

These badge uses April Tags and Arduino H7/Camera Module to stream audio data vibration data to the Voice-Base Deluxe so the base station can perform audio processing. 

| Tech                               | Features            |
| ---------------------------------- | ------------------- |
| Arduino Nicla Vision / H7 + Camera | Vision              |
| April Tag                          | MQTT Client         |
| Battery                            | Audio and Vibration |

#### Voice-Badge Simple

These badge uses April Tags and Arduino Nicla Voice to capture audio data vibration data.

| Tech                               | Features            |
| ---------------------------------- | ------------------- |
| Arduino Nicla Vision / H7 + Camera | Vision              |
| April Tag                          | MQTT Client         |
| Battery                            | Audio and Vibration |

#### Regular-Badge

The plain badge with an April Tag and RFID badge. 

| Tech      | Features             |
| --------- | -------------------- |
| April-Tag | ID from base station |
| RFID      | Proximity detection  |

### Other Devices (Inputs)

##### Voice Device | Jabra

Group work VAD and SD

##### Owl Lab Meeting

360 Video

Audion



### LOOK at TRELLO

H7 Audio

Base-Station Influx/Graphena

