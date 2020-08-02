## HDD structure

```bash
$ tree 2tb -d -L 2

2tb
├── bazarr
│   └── config
├── jackett
│   └── config
├── plex
│   ├── config
│   ├── movies
│   └── tv
├── rutorrent
│   ├── config
│   └── downloads
├── sonarr
│   └── config
└── transmission
    ├── config
    ├── downloads
    └── watch

17 directories
```

## Setup

```bash
docker-compose up -d
```

## Teardown

```bash
docker-compose down
```

## Links

* https://hub.docker.com/r/linuxserver/plex
* https://hub.docker.com/r/linuxserver/sonarr
* https://hub.docker.com/r/linuxserver/rutorrent
* https://hub.docker.com/r/linuxserver/transmission
* https://hub.docker.com/r/linuxserver/jackett
* https://hub.docker.com/r/linuxserver/bazarr
* https://hub.docker.com/r/linuxserver/radarr
