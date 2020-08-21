# Mediabox

![](https://github.com/cristianmiranda/mediabox/workflows/Multimedia%20Stack%20Deployment/badge.svg)

![](https://i.imgur.com/p8AHjpF.jpg)

## What's in the stack?
* [Plex](https://www.plex.tv/)
* [Sonarr](https://sonarr.tv/)
* [Radarr](https://radarr.video/)
* [Bazarr](https://www.bazarr.media/)
* [Jackett](https://github.com/Jackett/Jackett)
* [NZBHydra2](https://github.com/theotherp/nzbhydra2)
* [SABnzbd](https://sabnzbd.org/)
* [Deluge](https://deluge-torrent.org/)
* [Calibre](https://calibre-ebook.com/)
* [Portainer](https://www.portainer.io/)
* [Watchtower](https://github.com/containrrr/watchtower)
* [Organizr](https://github.com/causefx/Organizr)
* [Duplicati](https://www.duplicati.com/)

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

## Architecture
<p align="center">
  <img src="https://imgur.com/nsEsoKw.png" />
</p>
