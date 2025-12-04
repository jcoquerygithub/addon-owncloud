# ownCloud - Home Assistant Community Add-ons
This addon allows running a very simple owncloud server design to be access on local network only

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]

## Concept
ownCloud server installation requires a lot of assets making it very difficult to recreate a docker image based on home-assistant/addons image
The goal was the opposite, taking the official owncloud server image and creating a new one with home-assistant assets
Not much customization is added, only basic one like port and initial password

## Version
Base ownCloud Docker image : [owncloud/server:10.16.0](https://hub.docker.com/layers/owncloud/server/10.16.0/images/sha256-456033f563e550c6cf87841d260f1718d0f90ab1d15ecd0f1d38c771fad99c70)
Addon home-assistant [docker-base ubuntu 22.04](https://github.com/home-assistant/docker-base/blob/master/ubuntu/Dockerfile)

## Addon configuration
This addon takes the following options
```yaml
options:
  owncloud_domain: "homeassistant.local:8080" #ownCloud domain name and port 
  owncloud_admin_password: "changeme" #initial admin password for the first startup. Has no effect after first start
  owncloud_log_level: 3 #log level
  disable_accesslog: true #disable apache access log to be print on stdout flooding HA logs 
```


[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
