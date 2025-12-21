FROM archlinux:latest

RUN pacman -Syu --noconfirm && \
    pacman -S --noconfirm plasma-desktop konsole dolphin xorg-server-xvfb x11vnc python-numpy

RUN pacman -S --noconfirm novnc

echo "#!/bin/bash\nXvfb :1 -screen 0 1920x1080x24 &\nexport DISPLAY=:1\nstartplasma-x11 &\nx11vnc -display :1 -nopw -forever -shared &\n/usr/share/novnc/utils/novnc_proxy --vnc localhost:5900 --listen 6080" > /usr/local/bin/start-kde.sh
RUN chmod +x /usr/local/bin/start-kde.sh