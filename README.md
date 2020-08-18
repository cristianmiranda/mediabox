# Mediabox

![](https://github.com/cristianmiranda/mediabox/workflows/Multimedia%20Stack%20Deployment/badge.svg)

![](https://i.imgur.com/NHvoGC1.jpg)

## Supported apps
* Plex
* Sonarr
* Radarr
* Bazarr
* Jackett
* Deluge
* Calibre
* Portainer
* Watchtower
* Organizr

## Setup
* Replace all paths in `.env` with whatever makes sense for you (follow the comments above each property).
* Use `docker-compose.override.yml` for adding additional media libraries.
* It might be a good idea to clone this repo inside the external disk if you plan to use it on different machines/architectures.

## Starting
```bash
docker-compose up -d
```

## Stopping
```bash
docker-compose down
```

## Updating
Watchtower automatically updates all apps (if docker image update is available) at 4 AM every day.

## Services ports
_(Use your own local IP address)_

* Organizr: 9983
* Plex: 32400
* Sonarr: 8989
* Radarr: 7878
* Bazarr: 6767
* Deluge: 8112
* Jackett: 9117
* Portainer: 9000
* Calibre: 9080

## Configuration
### Plex
![](https://imgur.com/tTZM8Xr.png)
![](https://imgur.com/24rtdJv.png)

### Sonarr / Radarr
![](https://imgur.com/DpIkOwh.png)
![](https://imgur.com/3Urh1mb.png)

### Deluge
![](https://i.imgur.com/iymyOIM.png)
![](https://i.imgur.com/LCyPZrW.png)

## Docs
* https://www.tecmint.com/create-new-ext4-file-system-partition-in-linux/
* https://www.techrepublic.com/article/how-to-properly-automount-a-drive-in-ubuntu-linux/
* https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/
* https://support.plex.tv/articles/202485658-restore-a-database-backed-up-via-scheduled-tasks/
* https://dev.to/rohansawant/installing-docker-and-docker-compose-on-the-raspberry-pi-in-5-simple-steps-3mgl
