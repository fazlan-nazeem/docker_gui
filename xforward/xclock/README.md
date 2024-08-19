
```docker build -t xclock .```

### Run the image

```docker run -e DISPLAY=host.docker.internal:0 -v /tmp/.X11-unix:/tmp/.X11-unix xclock```