## How to access:
---
- Portainer: http://localhost:9000
- OpenHab: http://localhost:8082
- Grafana: http://localhost:3000
- Influxdb: 
    ```yml
        ports:
        - "8083:8083"
        - "8086:8086"
        - "8090:8090"
        - "25826:25826/udp"
        - "2003:2003"
    ```

- mosquitto-mqtt: 
    ```yml
        ports:
        - "1883:1883"
        - "9001:9001"
    ```

--------------------------------------------------
## Create SDCard for Unipi Neuron S103

- Download this file : [here](https://kb.unipi.technology/_media/files:software:os-images:neuron-mervis-os_image-2.4.0.10.zip)

- Use BalenaEtcher to create the boot on the SDCard
  > https://www.balena.io/etcher/

- To connect into SSH with Unipi :

   > **1.** enter into *boot* partition 
   > **2.** create empty file _ssh.txt_ or _ssh_
   > **3.** SSH :
     - `login : unipi` 
     - ` password: unipi.technology` 

-----------------------------------------------------

### Install Docker on the Unipi 

```
sudo curl -sSL https://get.docker.com | sh
```
### Add user Unipi in docker group :

```
 sudo usermod -aG docker unipi
 sudo gpasswd -a unipi docker
 sudo reboot now
```

-----------------------------------------------------

### start docker stack

```
git clone https://github.com/badouuuuuu/openhab-influxdb-grafana-mqtt-portainer.git
```

```
cd openhab-influxdb-grafana-mqtt-portainer
```

```
docker-compose up
```

-----------------------------------------------------


