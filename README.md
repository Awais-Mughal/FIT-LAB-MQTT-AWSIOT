<div align="center">
<h1 align="center">
<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/ec559a9f6bfd399b82bb44393651661b08aaf7ba/icons/folder-markdown-open.svg" width="100" />
<br>FIT-LAB-MQTT-AWSIOT</h1>
<h3>◦ Developed with the software and tools below.</h3>
<h3>◦ ► FIT-IoT testbed, RIOT, AWS cloud, Mosquitto MQTT, NodeRed, Influxdb, Grafana</h3>
<p align="center">
<img src="https://img.shields.io/badge/C-A8B9CC.svg?style=for-the-badge&logo=C&logoColor=black" alt="C" />
<img src="https://img.shields.io/badge/JSON-000000.svg?style=for-the-badge&logo=JSON&logoColor=white" alt="JSON" />
</p>
<img src="https://img.shields.io/github/license/Awais-Mughal/FIT-LAB-MQTT-AWSIOT?style=for-the-badge&color=5D6D7E" alt="GitHub license" />
<img src="https://img.shields.io/github/last-commit/Awais-Mughal/FIT-LAB-MQTT-AWSIOT?style=for-the-badge&color=5D6D7E" alt="git-last-commit" />
<img src="https://img.shields.io/github/commit-activity/m/Awais-Mughal/FIT-LAB-MQTT-AWSIOT?style=for-the-badge&color=5D6D7E" alt="GitHub commit activity" />
<img src="https://img.shields.io/github/languages/top/Awais-Mughal/FIT-LAB-MQTT-AWSIOT?style=for-the-badge&color=5D6D7E" alt="GitHub top language" />
</div>

---

##  Table of Contents
- [ Table of Contents](#-table-of-contents)
- [ Overview](#-overview)
- [ Features](#-features)
- [ repository Structure](#-repository-structure)
- [ Modules](#modules)
- [ Getting Started](#-getting-started)
    - [ Installation](#-installation)
    - [ Running FIT-LAB-MQTT-AWSIOT](#-running-FIT-LAB-MQTT-AWSIOT)
    - [ Tests](#-tests)
- [ Roadmap](#-roadmap)
- [ Contributing](#-contributing)
- [ License](#-license)
- [ Acknowledgments](#-acknowledgments)

---


##  Overview

► In this project an IoT (Internet of Things) sensor node is developed using the RIOT operating system. The sensor node is designed to collect environmental data, including temperature and pressure, and transmit this data to an MQTT (Message Queuing Telemetry Transport) broker using secure protocols,The sensor node communicates with an MQTT broker, and the Mosquitto broker bridge is configured to connect to AWS IoT. and visualizes the data through Grafana.

---

##  Features

► INSERT-TEXT

---


##  Repository Structure

```sh
└── FIT-LAB-MQTT-AWSIOT/
    ├── Broker_config/
    │   └── config.conf
    ├── Grafana/
    │   └── Grafana_Dashboard.json
    ├── Mosquitto_Bridge/
    │   └── mosquitto.config
    ├── NodeRed/
    │   └── NodeRed_Flow.json
    └── Sensor_node/
        ├── Makefile.mak
        └── main.c

```

---


##  Modules

<details closed><summary>Broker_config</summary>

| File                                                                                                   | Summary       |
| ---                                                                                                    | ---           |
| [config.conf](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/Broker_config/config.conf) | ► The config.conf file enables MQTT-SN and MQTT connections, with debug tracing and specific listeners. It also establishes a connection named "local_bridge_to_ec2" between local and AWS IoT gateways on respective ports.|

</details>

<details closed><summary>Sensor_node</summary>

| File                                                                                                   | Summary       |
| ---                                                                                                    | ---           |
| [main.c](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/Sensor_node/main.c)             | ► The C program for the IoT sensor node, named "SensorNode," includes MQTT-SN communication, LPS331AP sensor readings, and a command-line interface (CLI). It periodically measures temperature and pressure, publishes the data to an MQTT broker, and provides status reports via the CLI. The program creates threads for MQTT communication and the main measurement loop. |
| [Makefile.mak](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/Sensor_node/Makefile.mak) | ► The Makefile for the SensorNode application in RIOT OS configures a native board, includes necessary modules for sensor and network functionality, sets up MQTT modules for communication, and defines parameters such as server address, port, and MQTT topics.|

</details>

<details closed><summary>Grafana</summary>

| File                                                                                                                   | Summary       |
| ---                                                                                                                    | ---           |
| [Grafana_Dashboard.json](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/Grafana/Grafana_Dashboard.json) | ► It includes panels displaying temperature and pressure information over time, with thresholds for visualization. The dashboard is designed to refresh every 5 seconds.|

</details>

<details closed><summary>Nodered</summary>

| File                                                                                                         | Summary       |
| ---                                                                                                          | ---           |
| [NodeRed_Flow.json](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/NodeRed/NodeRed_Flow.json) | ► The Node-RED flow titled "Flow 1" includes MQTT input for the topic "localgateway_to_awsiot," with subsequent debugging and storage in InfluxDB. It warns about container setup for preserving flow changes in Docker. The MQTT input connects to the broker at 52.204.227.162:1883, and InfluxDB storage uses the database "iot" at 127.0.0.1:8086.|

</details>

<details closed><summary>Mosquitto_bridge</summary>

| File                                                                                                                | Summary       |
| ---                                                                                                                 | ---           |
| [mosquitto.config](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/Mosquitto_Bridge/mosquitto.config) | ► It sets up an MQTT bridge to AWS IoT Core. It includes connection details such as the AWS IoT ATS endpoint, specifies bridged topics for bidirectional communication, sets the MQTT protocol version, enables SSL/TLS with certificate-based authentication, and configures cleanup and logging options. |

</details>

---

##  Getting Started

***Dependencies***

Please ensure you have the following dependencies installed on your system:

`- ℹ️ Dependency 1`

`- ℹ️ Dependency 2`

`- ℹ️ ...`

###  Installation

1. Clone the FIT-LAB-MQTT-AWSIOT repository:
```sh
git clone https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT
```

2. Change to the project directory:
```sh
cd FIT-LAB-MQTT-AWSIOT
```

###  Running FIT-LAB-MQTT-AWSIOT

#### Connect to Grenoble SSH Frontend
```bash
ssh <login>@grenoble.iot-lab.info
```

#### Start Experiment on IoT-Lab Test Bed

Launch an experiment with two M3 nodes and one A8 node
Wait for the experiment to reach the "Running" state
Get the list of nodes

#### Build Border Router Firmware
Source RIOT environment
```sh
source /opt/riot.source
```

Build border router firmware for M3 node with baudrate 500000
Note: Use a different 802.15.4 channel if needed
```sh
make ETHOS_BAUDRATE=500000 DEFAULT_CHANNEL=<channel> BOARD=iotlab-m3 -C examples/gnrc_border_router clean all
```


#### Flash Border Router Firmware
Flash the border router firmware to the first M3 node (m3-1 in this case)
```sh
iotlab-node --flash examples/gnrc_border_router/bin/iotlab-m3/gnrc_border_router.elf -l grenoble,m3,<node-id>
```


#### Configure Border Router Network
Choose an IPv6 prefix for the site (e.g., 2001:660:5307:3100::/64)
Configure the network of the border router on m3-<node-id>
Propagate an IPv6 prefix with ethos_uhcpd.py
```sh
sudo ethos_uhcpd.py m3-<node-id> tap0 2001:660:5307:3100::1/64
```

#### Setup MQTT Broker and Mosquitto Bridge on A8 Node
SSH into the A8 node
```sh
ssh root@node-a8-1
```
Check the global IPv6 address of the A8 node
```sh
ifconfig
```
![Alt text](/images/image.png)

#### Start MQTT Broker
From the A8 shared directory, start the MQTT broker using config.conf
```sh
cd ~/A8
broker_mqtts config.conf
```
![Alt text](/images/image-1.png)

#### Configure and Start Mosquitto Bridge
From another terminal on the A8 node, check for existing mosquitto service and stop it
Modify mosquitto.config with the IPv6 address of the Mosquitto broker (e.g., AWS-EC2 instance)
Start Mosquitto service using the modified configuration file

###  Tests
#### Build and Flash Sensor Node Firmware
SSH into SSH frontend of Grenoble site
Clone the sensor node directory containing Makefile and main.c
Build the firmware for the sensor node using A8 node's IPv6 address and tap-id
```sh
make DEFAULT_CHANNEL=15 SERVER_ADDR=<IPv6 address> EMCUTE_ID=station(tap-id) BOARD=iotlab-m3 -C . clean all
```

#### Flash the sensor node firmware on an M3 node
```sh
iotlab-node --flash ./bin/iotlab-m3/SensorNode.elf -l grenoble,m3,<node-id>
```


#### Connect to Sensor Node
Log into the M3 node
```sh
nc m3-<node-id> 20000
```



---


##  Project Roadmap

> - [X] `ℹ️  Task 1: Implement X`
> - [ ] `ℹ️  Task 2: Implement Y`
> - [ ] `ℹ️ ...`


---

##  Contributing

Contributions are welcome! Here are several ways you can contribute:

- **[Submit Pull Requests](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/blob/main/CONTRIBUTING.md)**: Review open PRs, and submit your own PRs.
- **[Join the Discussions](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/discussions)**: Share your insights, provide feedback, or ask questions.
- **[Report Issues](https://github.com/Awais-Mughal/FIT-LAB-MQTT-AWSIOT/issues)**: Submit bugs found or log feature requests for AWAIS-MUGHAL.

#### *Contributing Guidelines*

<details closed>
<summary>Click to expand</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a Git client.
   ```sh
   git clone <your-forked-repo-url>
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear and concise message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.

Once your PR is reviewed and approved, it will be merged into the main branch.

</details>

---

##  License


This project is protected under the [SELECT-A-LICENSE](https://choosealicense.com/licenses) License. For more details, refer to the [LICENSE](https://choosealicense.com/licenses/) file.

---

##  Acknowledgments

- List any resources, contributors, inspiration, etc. here.

[**Return**](#Top)

---
