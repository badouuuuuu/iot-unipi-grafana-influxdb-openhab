
## Create SDCard for Unipi Neuron S103

- Download this file : [here](https://kb.unipi.technology/_media/files:software:os-images:neuron-mervis-os_image-2.4.0.10.zip)

- Extract 
- Use BalenaEtcher to create the boot on the SDCard
> https://www.balena.io/etcher/

- To connect into SSH with Unipi :

> enter into *boot* partition 
> create empty file _ssh.txt_ or _ssh_

SSH default :
*login*: _unipi_
*password*: _unipi.technology_

-----------------------------------------------------

### Install Docker on the Unipi 

```
sudo curl -sSL https://get.docker.com | sh
```
### Add user Unipi in docker group :

```
 sudo gpasswd -a unipi docker
 sudo reboot now
```


### start docker stack

```
git clone ...
```

```
cd ...
```

```
docker-compose up
```

Portainer: http://localhost:9000
Grafana: http://localhost:3000

Influxdb: 

```yml
    ports:
      - "8083:8083"
      - "8086:8086"
      - "8090:8090"
      - "25826:25826/udp"
      - "2003:2003"
```