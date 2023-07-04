## 👋 Welcome to radarr 🚀  

radarr README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update radarr
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/radarr/rootfs"
git clone "https://github.com/dockermgr/radarr" "$HOME/.local/share/CasjaysDev/dockermgr/radarr"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/radarr/rootfs/." "$HOME/.local/share/srv/docker/radarr/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-radarr \
--hostname radarr \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-radarr/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-radarr/rootfs/config:/config:z \
-p 80:80 \
casjaysdevdocker/radarr:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/radarr
    container_name: casjaysdevdocker-radarr
    environment:
      - TZ=America/New_York
      - HOSTNAME=radarr
    volumes:
      - $HOME/.local/share/srv/docker/casjaysdevdocker-radarr/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-radarr/rootfs/config:/config:z
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/radarr
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/radarr" "$HOME/Projects/github/casjaysdevdocker/radarr"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/radarr"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
