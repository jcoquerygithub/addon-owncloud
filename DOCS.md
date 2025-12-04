# Home Assistant Add-on: ownCloud
This addon allows running a very simple owncloud server design to be access on local network only

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

## Installation
Currently only local add-ons mode is available.
Installation steps
- go to your /usr/share/hassio/addons/local, clone repo
```shell
cd /usr/share/hassio/addons/local
git clone https://github.com/jcoquerygithub/addon-owncloud.git
```
- in HA go to Settings -> Add-on -> Add-on store -> Check for updates(click the 3 dots at top right)
- under Local add-ons there must be the card ownCloud, click on it
- click on install and after on build
- go to the configure tab and make the necessary options adjustment
- go back on info and start