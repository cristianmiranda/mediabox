## HDD structure

```bash
$ tree 2tb -d -L 2

2tb
├── plex
│   ├── config
│   ├── movies
│   └── tv
├── rutorrent
│   ├── config
│   └── downloads
└── sonarr
    └── config

9 directories
```

## Setup

```bash
docker-compose -d plex sonarr rutorrent
```
