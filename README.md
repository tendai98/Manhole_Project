# Intrusion Detection in Manholes with ESP8266 NodeMCU 🕵️‍♂️📡

This project focuses on intrusion detection in manholes using an ESP8266 NodeMCU controller and WiFi networking to connect to a control node. The control node monitors access and can disable a single detection node within the system.

## Note
In this case a detection node runs this code, so in a system you can have as many nodes as your network can handle

## Project Structure 🗂️

- **`buzzer.h`:** Manages the control of the buzzer to emit alarms.
- **`http.h`:** Handles HTTP communication and server responses.
- **`Manhole_Project.ino`:** The main code integrating functionalities.
- **`net.h`:** Initializes the data link and WiFi connection.
- **`pir.h`:** Manages the Passive Infrared (PIR) sensor.
- **`reed.h`:** Controls the reed sensor used for detection.
- **`waterlevel.h`:** Manages the water level sensor.

## Code Overview 💻

### `Manhole_Project.ino`

This main code file integrates functionalities from different headers:

- **🛠️ `setup()`:** Initializes sensors, data link, and the server. Functions used: `initSensors()`, `initServer()`.

- **🔄 `loop()`:** Handles server operations, LED blinking, and the intrusion detection process. Functions used: `runServer()`, `blinkLED()`, `runAlertMonitor()`.

### `buzzer.h` (Buzzer Control) 🔊

Manages the control of the buzzer:

- **🔊 `initializeBuzzer()`:** Initializes the buzzer pin.

- **🔊 `runBuzzer()`:** Activates the buzzer for a specified duration.

### `http.h` (HTTP and Server Handling) 🌐

Manages HTTP communications and server responses:

- **🌐 `getTripState()`:** Retrieves the state of the sensor trigger.

- **🌐 `securityAuthentication()`:** Handles security authentication.

- **🌐 `setSecurityPin()`:** Sets the security PIN for authentication.

- **🌐 `armSensor()`:** Arms or disarms the detection node.

### `net.h` (Data Link and WiFi) 📶

Manages the initialization of the data link and WiFi connection:

- **📶 `initDataLink()`:** Initializes the WiFi and data link.

### `pir.h` (Passive Infrared Sensor) 🕵️‍♂️

Manages the Passive Infrared (PIR) sensor:

- **🕵️‍♂️ `initializePIRSensor()`:** Initializes the PIR sensor pin.

- **🕵️‍♂️ `getPIRState()`:** Retrieves the state of the PIR sensor.

### `reed.h` (Reed Sensor Control) 🔒

Controls the reed sensor used for detection:

- **🔒 `initializeReedSensor()`:** Initializes the reed sensor pin.

- **🔒 `getReedSensorState()`:** Retrieves the state of the reed sensor.

### `waterlevel.h` (Water Level Sensor) 💧

Manages the water level sensor:

- **💧 `getWaterLevel()`:** Retrieves the water level reading in the manhole.
