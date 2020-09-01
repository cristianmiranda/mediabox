# :tv: Mediabox

![](https://github.com/cristianmiranda/mediabox/workflows/Multimedia%20Stack%20Deployment/badge.svg)

![](https://i.imgur.com/UZklu5w.jpg)

## What's in the stack?

### Multimedia
* [Plex](https://www.plex.tv/)
* [Sonarr](https://sonarr.tv/)
* [Radarr](https://radarr.video/)
* [Bazarr](https://www.bazarr.media/)
* [Jackett](https://github.com/Jackett/Jackett)
* [NZBHydra2](https://github.com/theotherp/nzbhydra2)
* [SABnzbd](https://sabnzbd.org/)
* [Deluge](https://deluge-torrent.org/) (built-in dark mode)
* [Calibre](https://calibre-ebook.com/)
* [Portainer 2.0](https://www.portainer.io/)
* [Watchtower](https://github.com/containrrr/watchtower)
* [Organizr](https://github.com/causefx/Organizr)

### Security
* [OpenVPN](https://github.com/dperson/openvpn-client)
* [Traefik](https://containo.us/traefik/)
* [Let's Encrypt Automatic SSL certificates](https://letsencrypt.org/)
* [Duplicati](https://www.duplicati.com/)

## Prerequisites
* [Docker](https://www.docker.com/)
* [Docker-Compose](https://docs.docker.com/compose/)

## Setup
1. Copy `.env.template`
```bash
cp .env.template .env
```
2. Replace variables on `.env` with whatever makes sense to you (follow the comments above each property).
3. It might be a good idea to clone this repo inside the external disk if you plan to use it on different machines/architectures.

## Starting
```bash
# Main stack + Unprotected Torrenting
docker-compose -f docker-compose.yml -f docker-compose.torrents.yml up -d

# Main stack + VPN Protected Torrenting
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml up -d

# Main stack + VPN Protected Torrenting + Plex HW Transcoding
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml -f docker-compose.plex-hw.yml up -d

# Main stack + VPN Protected Torrenting + Plex HW Transcoding + Custom domain & SSL certificates
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml -f docker-compose.plex-hw.yml -f docker-compose.traefik.yml up -d
```

## Stopping
Use `docker-compose down` adding `-f` flag with the same compose files you used for starting the stack.

## Updating
Watchtower automatically updates all apps (if docker image update is available) at 4 AM every day.

## Custom domain + Let's Encrypt free certificates
In case you own a domain like `example.com` and you'd like to configure subdomains pointing to your apps like `sonarr.example.com` or `plex.example.com`, do the following:
1. Modify `.env`:
```bash
DOMAIN=example.com
SSL_ACME_EMAIL=you@mail.com
```
2. Forward ports 80 and 443 to your mediabox (you can do that changing your router settings).
3. Include `docker-compose.traefik.yml` when starting the stack
4. Check the logs to verify everything is up and running: `docker logs -f traefik`

## VPN
With OpenVPN you can use any VPN provider following these steps:

1. Download your VPN OpenVPN config files (e.g: [NordVPN TCP/UDP config files](https://nordvpn.com/ovpn/))
2. Download your VPN CA file (e.g: [NordVPN CA & TLS key files](https://downloads.nordcdn.com/configs/archives/certificates/servers.zip))
3. Run the following (using NordVPN Brazil#65 as example)
```bash
# Copy required files
cp ~/Downloads/br65.nordvpn.com.udp.ovpn ${OPENVPN}/vpn.conf
cp ~/Downloads/br65_nordvpn_com_ca.crt ${OPENVPN}/vpn-ca.crt

# Write credentials
cat <<EOT >> ${OPENVPN}/vpn.auth
you@mail.com
YourVPNP4ssw0rD
EOT
```

## Sonarr/Radarr << Deluge/SABnzbd
This setup follows the best practices mentioned on [this reddit post](https://www.reddit.com/r/usenet/wiki/docker#wiki_the_best_docker_setup), therefore you'll have to map Sonarr/Radarr volumes to Deluge's/SABnzbd's to be able to use hardlinks and/or perform atomic "move" operations instead of "copy+delete" (which takes longer and requires more space).

![](https://i.imgur.com/AHOQVXh.png)

## Architecture
<p align="center">
  <img src="https://imgur.com/nsEsoKw.png" />
</p>

```bash
# My disks layout:
#
# data
# ├── 2tb
# │   └── media
# │       ├── movies
# │       └── tv
# ├── 4tb
# │   └── media
# │       ├── movies
# │       └── tv
# └── ssd
#     └── mediabox
#         ├── containers
#         ├── downloads
#         └── repo
```
