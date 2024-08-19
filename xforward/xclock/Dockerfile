# Use an official Ubuntu base image
FROM ubuntu:22.04

# Install necessary packages
RUN apt-get update && apt-get install -y \
    x11-apps \
    xauth \
    x11-xserver-utils \
    && rm -rf /var/lib/apt/lists/*

# Set environment variables
ENV DISPLAY=:0
ENV QT_X11_NO_MITSHM=1

# Add a non-root user (optional)
RUN useradd -m guiuser
USER guiuser
WORKDIR /home/guiuser

# Copy the GUI application binary or script (if you have one)
# COPY my-gui-app /home/guiuser/my-gui-app

# Entrypoint command to run the GUI application
CMD ["xclock"]
