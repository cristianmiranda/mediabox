![](https://i.imgur.com/lRWVysP.jpg)

## Docker stack

![](https://i.imgur.com/gvPreHt.png)

## HDD structure

```bash
$ tree $HDD_PATH -d -L 2

2tb
├── bazarr
│   └── config
├── jackett
│   └── config
├── plex
│   ├── config
│   ├── movies
│   └── tv
├── radarr
│   └── config
├── sonarr
│   └── config
└── deluge
    ├── config
    ├── downloads

15 directories
```

## Setup

Replace `HDD_PATH` with the path of your mass storage drive

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
