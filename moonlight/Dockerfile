FROM debian:13

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends wget ca-certificates \
    libx11-6 libgl1 libegl1 libxfixes3 libfontconfig1 libopengl0 libharfbuzz0b libcom-err2 libgpg-error0 libsm6 && \
    rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/moonlight-stream/moonlight-qt/releases/download/v6.2.0/Moonlight-6.2.0-x86_64.AppImage && \
    chmod +x Moonlight-6.2.0-x86_64.AppImage && /Moonlight-6.2.0-x86_64.AppImage --appimage-extract && chmod -R a+rx /squashfs-root && \
    rm /Moonlight-6.2.0-x86_64.AppImage

CMD ["/squashfs-root/AppRun"]
