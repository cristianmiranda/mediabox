![](https://i.imgur.com/NHvoGC1.jpg)

## Docker stack

![](https://i.imgur.com/ni19vKz.png)

## HDD structure

```bash
$ tree $HDD_PATH -d -L 2

2tb
├── bazarr
│   └── config
├── jackett
│   └── config
├── plex
│   └── config
├── radarr
│   └── config
├── sonarr
│   └── config
├── deluge
|   ├── config
|   └── downloads
├── tv
└── movies

15 directories
```

## Setup

Replace all paths in `.env` with whatever makes sense for you (follow the comments above each property).
It might be a good idea to clone this repo inside the external disk if you plan to use it on different machines/architectures.

## Starting

```bash
docker-compose up -d
```

## Stopping

```bash
docker-compose down
```

## Updating

```bash
docker-compose down
docker-compose pull
docker-compose up -d
```

## Services

_(Use your own local IP address)_

* Muximux: http://192.168.50.244:80
* Plex: http://192.168.50.244:32400/web/index.html
* Sonarr: http://192.168.50.244:8989
* Radarr: http://192.168.50.244:7878
* Bazarr: http://192.168.50.244:6767
* Deluge: http://192.168.50.244:8112
* Jackett: http://192.168.50.244:9117

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

### Transmission
![](https://imgur.com/Rib2L9E.png)

## Docker images

* https://hub.docker.com/r/linuxserver/plex
* https://hub.docker.com/r/linuxserver/sonarr
* https://hub.docker.com/r/linuxserver/deluge
* https://hub.docker.com/r/linuxserver/jackett
* https://hub.docker.com/r/linuxserver/bazarr
* https://hub.docker.com/r/linuxserver/radarr
* https://hub.docker.com/r/linuxserver/muximux

## Docs

* https://www.tecmint.com/create-new-ext4-file-system-partition-in-linux/
* https://www.techrepublic.com/article/how-to-properly-automount-a-drive-in-ubuntu-linux/
* https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/
* https://support.plex.tv/articles/202485658-restore-a-database-backed-up-via-scheduled-tasks/
