## HDD structure

```bash
$ tree 2tb -d -L 2

2tb
├── jackett
│   └── config
├── plex
│   ├── config
│   ├── movies
│   └── tv
├── rutorrent
│   ├── config
│   └── downloads
└── sonarr
    └── config

11 directories
```

## Setup

```bash
docker-compose -d plex sonarr rutorrent jackett
```

## Links

* https://hub.docker.com/r/linuxserver/plex
* https://hub.docker.com/r/linuxserver/sonarr
* https://hub.docker.com/r/linuxserver/rutorrent
* https://hub.docker.com/r/linuxserver/jackett

