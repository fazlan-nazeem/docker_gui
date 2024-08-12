# Use the Ubuntu base image
FROM ubuntu:20.04

# Set environment variables to avoid interactive prompts during package installation
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

# Update package list and install required packages
RUN apt-get update && apt-get install -y \
    xfce4 \
    xfce4-terminal \
    tightvncserver \
    xvfb \
    wget \
    gnupg2 \
    software-properties-common \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Sublime Text
RUN wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | apt-key add - \
    && add-apt-repository "deb https://download.sublimetext.com/ apt/stable/" \
    && apt-get update && apt-get install -y sublime-text

# Set environment variables for VNC
ENV USER root
ENV DISPLAY :1

# Create a VNC startup script
RUN mkdir -p ~/.vnc \
    && echo "#!/bin/sh\n\
    xrdb $HOME/.Xresources\n\
    startxfce4 &" > ~/.vnc/xstartup \
    && chmod +x ~/.vnc/xstartup

# Set VNC password
RUN echo "YOUR_VNC_PASSWORD" | vncpasswd -f > /root/.vnc/passwd \
    && chmod 600 /root/.vnc/passwd

# Expose the VNC port
EXPOSE 5901

# Start the VNC server
CMD ["sh", "-c", "vncserver :1 -geometry 1280x800 -depth 24 && tail -F /root/.vnc/*.log"]
