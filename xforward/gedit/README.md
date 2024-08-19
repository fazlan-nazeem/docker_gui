### Build the docker image

```docker build -t gedit .```

### Run the image

```docker run -e DISPLAY=host.docker.internal:0 -v /tmp/.X11-unix:/tmp/.X11-unix gedit```