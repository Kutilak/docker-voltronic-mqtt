# MQTT interface for Voltronic (aka MPPSolar, Axpert, Powland, EASun, etc) solar inverters.

Supports protocols PI30 and PI41 devices.

### Exposed sensors:
- Inverter status
- grid_voltage (V)
- grid_frequency (Hz)
- AC output voltage (V)
- AC output frequency (Hz)
- AC output apparent power (VA)
- output_load_watt (W)
- output_load_percent (%)
- bus_voltage (V)
- battery_voltage (V)
- battery_charge_current (A)
- battery_capacity (%)
- heatsink_temperature (°C)
- PV input current (A)
- pv_input_voltage (V)
- PV input watt (W)
- Warnings
### How to run
Change credentials to your MQTT server and USB port in the command below and run it.
```bash
git clone https://github.com/Kutilak/docker-voltronic-mqtt.git
cd docker-voltronic-mqtt
docker build -t voltronic-mqtt .
docker run -d --privileged \
  --restart=always \
  -v /dev:/dev \
  --name voltronic-mqtt \
  -e MQTT_PASSWORD='your_password' \
  -e MQTT_SERVER='your_MQTT_address' \
  -e MQTT_USER='your_username' \
  -e SERIAL_PORT='/dev/ttyUSB0' \
  voltronic-mqtt
```

### Home Assistant users
Copy the content of 'ha-sensors.yaml' to your 'configuration.yaml' file. Edit as needed.

### Aditional protocols and sensors
Please check [this discussion](https://github.com/lavron/docker-voltronic-mqtt/discussions/5).

### Source
https://github.com/lavron/docker-voltronic-mqtt

