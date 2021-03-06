# Docker
#!/bin/sh

### INSTALL DOCKER ### 
```
sudo apt update &&
sudo apt install apt-transport-https ca-certificates curl software-properties-common &&
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - &&
```

#Make sure you are about to install from the Docker repo instead of the default Ubuntu repo (sudo apt install docker.io):
```
apt-cache policy docker-ce &&
sudo apt install docker-ce &&

sudo systemctl status docker &&
sudo docker ps // list all containers 
```
## INSTALL DOCKER COMPOSE ##
```
sudo apt install docker-compose -y &&

vim docker-compose.yaml &&
sudo docker-compose up -d 
```

## ENABLE PERMISSIONS ## 

```
sudo chmod 666 /var/run/docker.sock
```

## #INSTALL PORTAINER (ports, name, restart and volumes in CLI docker) ###
```
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```
#Test that docker works with this image:
```
docker run hello-world
```
