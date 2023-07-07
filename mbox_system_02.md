## Mobox System Design

### **Bases**

#### *Uber-Base (User base)*

The Uber-Base station provides a simple visualisation of the conversational chracteristic by subscribing different topics from corresponding MQTT broker.
Maybe could send feeback to instructor's uber-base.

| Tech           | Features          |
| -------------- | ----------------- |
| Linux Box      | WIFI              |
| Display        | BLE               |
| Keyboard Mouse | Ethernet          |
| Web Page       | Visualization     |
|                | Graphing          |
|                | MQTT Client       |

#### *Vision-Base*

Line of sight vision base, designed for capturing the April Tags, can work with wide-angle cameras and the Owl Meeting Lab. Also 360 like cameras.
| Tech         | Features                         |
| ------------ | -------------------------------- |
| Raspberry-Pi | Camera Wide angle or OWL meeting |
|              | Wifi                             |
|              | MQTT Broker/Client               |
|              | InfluxDB Client                  |
|              | Ethernet                         |

#### *Audio-Base simple and deluxe*

This simple base station handles the Audio tags or runs the Jabra for collecting and processing audio data from sensors and badges. 

The deluxe model captures the streams from the Voice-Badge deluxe and perform VAD and SD.

| Tech                   | Features           |
| ---------------------- | ------------------ |
| Nvidia Jetson (deluxe) | RFID Hat           |
| Unix Box (deluxe)      | BLE                |
| Raspberry-Pi (simple)  | Wifi               |
|                        | MQTT Broker/Client |
|                        | InfluxDB Client    |
|                        | MongoDB Client     |
|                        | Jabra              |
|                        | Ethernet           |

#### *Location-Base*

This base is designed to track location with BLE or RFID and provide proximity information. BLE logging to determine via triangulation the badges close by. Or using RFID (medium power) to capture the badges nearby.

| Tech          | Features           |
| ------------- | ------------------ |
| Raspberry-Pi  | RFID Shield / Hat  |
| Arduino H7/H8 | BLE                |
|               | Wifi               |
|               | MQTT Broker/Client |
|               | InfluxDB Client    |
|               | Ethernet           |

### **Badges**

#### *Vision-Badge*

This badge uses April Tags and Arduino Nicla Vision board to capture proximity location. Plus audio and vibration data.

| Tech                 | Features            |
| -------------------- | ------------------- |
| Arduino Nicla Vision | Vision              |
| April Tag            | MQTT Client         |
| Battery              | Audio and Vibration |

#### *Voice-Badge Deluxe*

These badge uses April Tags and Arduino H7/Camera Module to stream audio data vibration data to the Voice-Base Deluxe, so the base station can perform audio processing. 

| Tech                               | Features            |
| ---------------------------------- | ------------------- |
| Arduino Nicla Vision / H7 + Camera | Vision              |
| April Tag                          | MQTT Client         |
| Battery                            | Audio and Vibration |

#### *Voice-Badge Simple*

These badge uses April Tags and Arduino Nicla Voice to capture audio data vibration data. Keyword and simple

| Tech                               | Features            |
| ---------------------------------- | ------------------- |
| Arduino Nicla Vision / H7 + Camera | Vision              |
| April Tag                          | MQTT Client         |
| Battery                            | Audio and Vibration |

#### *Regular-Badge*

The plain badge with an April Tag and RFID badge. 

| Tech      | Features             |
| --------- | -------------------- |
| April-Tag | ID from base station |
| RFID      | Proximity detection  |

### **Database Server**
#### *Influx DB*
Influx DB stores some time series charactersistics (e.g. speakers by time, graph links by time)
| Tech      | Features             |
| --------- | -------------------- |
| Linux box | InfluxDB server      |

#### *Mongo DB*
Mongo DB stores text charactersistics (e.g. transcription by speaker)
| Tech      | Features             |
| --------- | -------------------- |
| Linux box | MongoDB server       |

### **Other Devices (Inputs)**

##### *Voice Device | Jabra*

Group work VAD and SD

##### *Owl Lab Meeting*

360 Video

Audion



### **LOOK at TRELLO**

H7 Audio

Base-Station Influx/Graphena

