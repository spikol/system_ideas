# Mobox System Design

## System Diagram

Below is a diagram that represents the different components of the system and their interactions:

![Mobox System Design](https://kroki.io/graphviz/svg/eNptUcFqhDAQve9XBE-7h4W212JBK_SiF0UvSymJGdzQ1NiJKQvFf2-iNirryTHvzXtvZrhokHZX8kZ-DwRp-8kFhmn-fCCt4kAu-ko7CJm6vdunklwkZSDDoGSA55hqIMdXKaDtT4EjaMMmuVoa3QN-PDjZuSehPWWupQD8ASTH6XsKbGOtpMIQgds6KbyNayFFr5A2MBpkC5aJGpW2EqIGPYLDToDHVQCXVy9uTBqwP5VXrIQWqh3HGvUij0SGC7UAqQdSVdN-07QX4mkTgjfrFA0CtC5GfJ-Dz1NXcbKAys47YSQBaW7_lGKXUoivTk6UfHHIoTGS4spicNc9v6yXX0DLNcnh24Dupw1b1HLKO4o2csNYnSmS0u0I9Hh2f6ts5FW-inyVTsuYUTf6DLsR5zKPZ-bwB-M72Mg=)


The Mobox system is designed to analyze the collaboration level within a group using different modality data. The system is composed of several modules: User client, Bases, Badges, and a Database Server. 

## Uber-Base (Frontend)

The Uber-Base is the dashboard of the system. It communicates with the Data Server to send requests and receive results. It also provides a real-time visualization of the conversational characteristics by subscribing to different topics from the corresponding MQTT broker, and a post-time visualization of the whole session.

| Tech               | Features                          |
| ------------------ | --------------------------------- |
| Web Browser        | Wi-Fi                             |
|                    | Graphing                          |
|                    | MQTT Clinet                       |
|                    | Visualization                     |

## Bases

The Bases are responsible for data collection and processing. They include:

### Vision-Base

The Vision-Base is designed to capture April Tags using wide-angle cameras or the Owl Meeting Lab. 

| Tech         | Features                         |
| ------------ | -------------------------------- |
| Raspberry-Pi | Wi-Fi                            |
| Camera Wide angle or OWL meeting | MQTT Broker  |
|              | InfluxDB Client                  |
|              | Ethernet                         |
|              | Flask Server                     |




### Audio-Base

The Audio-Base handles the Audio tags and processes audio data collected from jabra, sensors and badges. 

| Tech                   | Features           |
| ---------------------- | ------------------ |
| Nvidia Jetson (deluxe) | RFID Hat           |
| Unix Box (deluxe)      | BLE                |
| Raspberry-Pi (simple)  | Wi-Fi              |
|                        | MQTT Broker        |
|                        | InfluxDB Client    |
|                        | MongoDB Client     |
|                        | Jabra              |
|                        | Ethernet           |
|                        | Flask Server       |

### Location-Base

The Location-Base tracks location with BLE or RFID and provides proximity information. 

| Tech          | Features           |
| ------------- | ------------------ |
| Raspberry-Pi  | RFID Shield / Hat  |
| Arduino H7/H8 | BLE                |
|               | Wi-Fi              |
|               | MQTT Broker        |
|               | InfluxDB Client    |
|               | Ethernet           |
|               | Flask Server       |

## Badges

The Badges are responsible for data collection. They include:

### Vision-Badge

The Vision-Badge uses April Tags and Arduino Nicla Vision board to capture proximity location, audio, and vibration data.

| Tech                 | Features            |
| -------------------- | ------------------- |
| Arduino Nicla Vision | Vision              |
| April Tag            | Audio and Vibration |
| Battery              |                     |

### Voice-Badge Deluxe

The Voice-Badge Deluxe uses April Tags and Arduino H7/Camera Module to stream audio data vibration data to the Voice-Base Deluxe for audio processing.

| Tech                                      | Features            |
| ----------------------------------------- | ------------------- |
| Arduino Nicla Vision / H7 + VisionShield  | Vision              |
| April Tag                                 | Audio and Vibration |
| Battery                                   |                     |

### Voice-Badge Simple

The Voice-Badge Simple uses April Tags and Arduino Nicla Voice to capture audio data vibration data.

| Tech                               | Features            |
| ---------------------------------- | ------------------- |
| Arduino Nicla Voice                | Audio and Vibration |
| April Tag                          |                     |
| Battery                            |                     |

### Regular-Badge

The Regular-Badge is a plain badge with an April Tag and RFID badge.

| Tech      | Features             |
| --------- | -------------------- |
| April-Tag | ID from base station |
| RFID      | Proximity detection  |

## Database Server (Backend)

The Database Server is responsible for data storage and API endpoints. It receives requests from the user-base, triggers basestation's service, and sends back results to the user-base.
+ Influx DB stores time series characteristics (e.g. speakers by time, graph links by time).
+ Mongo DB stores text characteristics (e.g. transcription by speaker).

| Tech      | Features             |
| --------- | -------------------- |
| Linux box | InfluxDB server      |
|           | MongoDB server       |
|           | Flask server         |

### **Other Devices (Inputs)**

##### *Voice Device | Jabra*

+ Group work VAD and SD

##### *Owl Lab Meeting*

+ 360 Video

+ Audion



### **LOOK at TRELLO**

+ H7 Audio

+ Base-Station Influx/Graphena



