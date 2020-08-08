![](https://i.imgur.com/lRWVysP.jpg)

## Docker stack

![](https://i.imgur.com/fML1jLO.png)

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

Replace `HDD_PATH` with the path of your mass storage drive.
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

## Docs

* https://www.tecmint.com/create-new-ext4-file-system-partition-in-linux/
* https://www.techrepublic.com/article/how-to-properly-automount-a-drive-in-ubuntu-linux/
* https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/
