# docker_gui
This repository is a collection of sample Dockerfiles which can be used to run GUI applications with Docker containers.

Following are different ways a GUI application can be run on containers. 

1. VNC
2. X11 Forwarding

### Note

#### complexity of GUI Forwarding:
Running GUI applications inside a Docker container often requires setting up X11 forwarding or using VNC, which can be complex and cumbersome. X11 is not natively supported by all operating systems, and configuring it correctly inside a Docker container can be challenging.

#### Performance Overhead:
Running a GUI application inside a container can introduce additional performance overhead, especially when dealing with rendering, graphics acceleration, and handling high-resolution displays. 