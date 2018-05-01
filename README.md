# Introduction

This container provides base X11 packages for hosting X11 applications.
This container uses XPRA as graphic device.
To keep such X11-based containers slim, tools for accessing this container like RDP server, VNC server and SSH server are intended to be hosted by another (sepcialized and centralized) container.
Both containers interact via XPRA mirroring.
So the first container can focus on the spefic X11 application and the second container (with RDP/VNC server) focusses on providing access to users.

# Extending this container

Of course, you can use this image as base image of your new custom images, and extending it by installing new RPM packages and so on.

You can integrate the invocation of your X11 application in the existing automatism in two ways:
- Setting the environment variable STARTUP with the command to launch, e.g. in the Dockerfile via
    ```ENV STARTUP=xclock```
- Placing a shell script in the container under following location:
    ```/usr/scripts/client_startup.sh```
    
# Download image
```docker pull cubeearth/headless-desktop```
    
# References
- [This image on Docker hub](https://hub.docker.com/r/cubeearth/headless-desktop/)
- [Container providing RDP/VNC server to access other containers via XPRA mirroring](https://github.com/Cube-Earth/container-remote-desktop)
