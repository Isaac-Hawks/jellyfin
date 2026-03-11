# Jellyfin Docker Container
This is a template for a jellyfin server that runs in a docker container
These instructions are tailored for Ubuntu/Debian

## Download:
```bash
git clone https://github.com/Isaac-Hawks/jellyfin && 
cd jellyfin
```
## Setup/Deployment
For this to work, you need docker + docker-compose on the device that will be hosting your Jellyfin server

If you do not already have these installed. run this command:
```bash
sudo apt-update && sudo apt-get install docker.io docker-compose -y

```
* If you ever want to wdit the docker-compose.yml file, run `docker-compose down` from inside the jellyfin directory to remove the container and network
* If you ever want to stop the docker container, run `docker stop jellyfin`; This is for when you don't want docker using up all your resources, and you're not editing any configuration files like
  the docker-compose.yml

After you have docker installed, you have to start the container in the jellyfin directory:
` sudo docker-compose up -d `
Note: If this is your first time doing this, docker will need to download the jellyfin image.

## Accessing your server
If you are accessing your server from your host machine, then you will need to navigate to http://127.0.0.1:8096.  
Otherwise, if you are accessing your server from a different device, go to http://server-ip:8096
* To find your server ip address, run `hostname -I | awk '{print $1}'` on the machine hosting your Jellyfin server

# Folder Structure:
```
/jellyfin
  ├── /cache
  │   └── .gitkeep
  ├── /config
  │   └── .gitkeep
  ├── /media
  │   └── README.md
  ├── docker-compose.yml
  └── README.md
```
# GUI Setup

## Note:
* When you pull clone this repository, the cache and config folders will be empty.
* When you 
* When you scan a library for the first time, Jellyfin pulls metadata from sources like TVDB/TMDB and drops it into the cache folder.
