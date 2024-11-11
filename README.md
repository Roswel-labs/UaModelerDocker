# Ua Modeler Docker

Purpose of this repo is to setup the UA Modeler as a containerized GUI app accessible with VNC.

# Prerequisities

- Docker Desktop (tested with 4.35)

# Setup

## UA Modeler

1) download [UA Modeler](https://www.unified-automation.com/fileadmin/files/development/uamodeler/uamodeler-bin-linux-x86_64-1.6.12-534.AppImage.zip) Linux binary (tested with v1.6.12)
2) place it in the root of this repo
3) rename to `UaModeler.AppImage`
4) `chmod +x UaModeler.AppImage`

## Docker

On mac:
- enable `Docker Desktop > Settings > Use Rosetta for x86_64/amd64 emulation on Apple Silicon`

Then:
- build `docker build --platform linux/amd64 -t ua_modeler .`
- run `docker run --platform linux/amd64 --ulimit nofile=1024:1024 -p 6080:80 -p 5900:5900 -v /dev/shm:/dev/shm ua_modeler`

# Usage

The image contains noVNC client to access the container with browser on `localhost:6080`.

Alternatively, use any VNC client with `localhost:5900`.

The UaModeler is located at Desktop.

__Note:__ The connection is not secure since password is not needed. Do not use as part of the production solution.


