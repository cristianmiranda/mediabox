# Mediabox

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
* [Deluge](https://deluge-torrent.org/)
* [Calibre](https://calibre-ebook.com/)
* [Portainer](https://www.portainer.io/)
* [Watchtower](https://github.com/containrrr/watchtower)
* [Organizr](https://github.com/causefx/Organizr)

### Security
* [OpenVPN](https://github.com/dperson/openvpn-client)
* [Traefik](https://containo.us/traefik/)
* [Let's Encrypt Automatic SSL certificates](https://letsencrypt.org/)
* [Duplicati](https://www.duplicati.com/)

## Setup
* Replace all paths in `.env` with whatever makes sense for you (follow the comments above each property).
* It might be a good idea to clone this repo inside the external disk if you plan to use it on different machines/architectures.

## Starting
```bash
# Main stack + Unprotected Torrenting
docker-compose -f docker-compose.yml -f docker-compose.torrents.yml up -d

# Main stack + VPN Protected Torrenting
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml up -d

# Main stack + VPN Protected Torrenting + Extra disk volumes
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml -f docker-compose.volumes.yml up -d

# Main stack + VPN Protected Torrenting + Extra disk volumes + Plex HW Transcoding
docker-compose -f docker-compose.yml -f docker-compose.torrents-on-vpn.yml -f docker-compose.volumes.yml -f docker-compose.plex-hw.yml up -d
```

## Stopping
Use `docker-compose down` adding `-f` flag with the same compose files you used for starting the stack.

## Updating
Watchtower automatically updates all apps (if docker image update is available) at 4 AM every day.

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

## Architecture
<p align="center">
  <img src="https://imgur.com/nsEsoKw.png" />
</p>
