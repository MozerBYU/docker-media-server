# Introduction

All-in-one, Infrastructure-as-a-Code (IaaC) Docker Compose File for setting up a Plex Media Server infrastructure. Additionally includes the ARR apps for various media requesting and management, integrated with VPNs and torrentors/downloaders and SSO Authentication for easy media management and secure access.

Recently updated as of 9/26/2024 to include Docker Best Security Practices, courtesy of Official Docker Documentation and OWASP.

Security Best Practices Checklist:
✅ Deny access to the Docker Socket API except where absolutely necessary (containers that rely on this permission have been noted in the 'Docker Security' section)
✅ Run Docker process as a separate 'Docker' user (UID 1001 or higher)
✅ Limit container capabilities (only container using cap_add is Transmission)
✅ Prevent in-container privilege escalation (all containers have a set UID and GUID respective to their permission level)
✅ Limit inter-connectivity between containers where possible (hence the separate container networks of frontend, backend, socket)
✅ Use Linux Security Modules such as SecComp, AppArmor and SELinux (not currently enabled in this version, but will be added later)
✅ Limit over resource utilization (not currently enabled in this version, but will be added later)
✅ Set read-only file systems permission where possible (due to the nature of the containers involved in this project, this is not utilized very much)
✅ Ensure official and trusted container respositories are utilized and container scanning for malicious code

See: https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html

### Apps Included (by Alphabetical Order)
- Authelia
- Bazarr
- Docker-GC
- Dozzle
- FileBrowser
- Handbrake
- Homarr
- Lidarr
- Nginx Proxy Manager
- OpenLDAP
- Overseerr
- PGAdmin
- Picard
- Plex
- Postgres
- Portainer
- Prowlarr
- Radarr
- Readarr
- Socket Proxy
- Sonarr
- Tautulii
- Transmission
- WatchTower
- Wrapperr

### Apps Included (by Designation)
Docker Security Apps
- Socket Proxy: https://github.com/Tecnativa/docker-socket-proxy
- WatchTower: https://github.com/containrrr/watchtower

Docker Utility Apps
- Docker-GC: https://github.com/clockworksoul/docker-gc-cron
- Dozzle: https://github.com/amir20/dozzle
- FileBrowser: https://github.com/hurlenko/filebrowser-docker
- Portainer: https://github.com/portainer/portainer

Authentication:
- Authelia: https://hub.docker.com/r/authelia/authelia
- OpenLDAP: https://hub.docker.com/r/bitnami/openldap

FrontEnd:
- Homarr: https://homarr.dev/docs/getting-started/installation/
- Nginx Proxy Manager: https://github.com/NginxProxyManager/nginx-proxy-manager

BackEnd:
- Postgre: https://hub.docker.com/_/postgres
- PGAdmin: https://www.pgadmin.org/download/pgadmin-4-container

Downloaders/Torrentors:
- Transmissin: https://github.com/linuxserver/docker-transmission

Media Tools:
- Bazarr: https://github.com/linuxserver/docker-bazarr
- Lidarr: https://github.com/linuxserver/docker-lidarr
- Overseerr: https://github.com/linuxserver/docker-overseerr
- Prowlarr: https://github.com/linuxserver/docker-prowlarr
- Radarr: https://github.com/linuxserver/docker-radarr
- Readarr: https://github.com/linuxserver/docker-readarr
- Sonarr: https://github.com/linuxserver/docker-sonarr

Media Server Tools:
- Handbrake: https://github.com/jlesage/docker-handbrake 
- Picard: https://github.com/mikenye/docker-picard
- Plex: https://github.com/plexinc/pms-docker
- Tautulli: https://github.com/linuxserver/docker-tautulli
- Wrapperr: https://github.com/aunefyren/wrapperr/releases
